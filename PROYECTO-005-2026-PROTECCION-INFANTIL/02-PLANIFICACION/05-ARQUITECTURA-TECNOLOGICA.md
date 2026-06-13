# ARQUITECTURA TECNOLÓGICA — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. DIAGRAMA DE ARQUITECTURA

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                              USUARIO FINAL                                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐         │
│  │ Padre        │  │ Colegio      │  │ Ciudadano    │  │ Autoridad    │         │
│  │ (Consulta)   │  │ (Panel B2B2C)│  │ (Reporte)    │  │ (API Gateway)│         │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘         │
└─────────┼─────────────────┼─────────────────┼─────────────────┼─────────────────┘
          │                 │                 │                 │
          │ HTTPS           │ HTTPS           │ HTTPS           │ HTTPS + API Key
          ▼                 ▼                 ▼                 ▼
┌─────────────────────────────────────────────────────────────────────────────────┐
│                           Nginx Reverse Proxy                                   │
│  • TLS 1.3 (Let's Encrypt)                                                     │
│  • HTTP/2                                                                      │
│  • Rate limiting (5 req/s por IP)                                              │
│  • access_log off para /api/reportes                                           │
│  • Cache de consultas frecuentes (5 min)                                       │
└─────────────────────────────────────────────────────────────────────────────────┘
          │
          ▼
┌─────────────────────────────────────────────────────────────────────────────────┐
│  FRONTEND — PWA (React 19 + Vite + Tailwind CSS + Workbox)                     │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Página Principal (Consulta Semáforo)                                   │  │
│  │  • Input universal (teléfono, email, @, URL)                            │  │
│  │  • Normalización de identificador                                       │  │
│  │  • Card de resultado (verde/amarillo/rojo/negro)                        │  │
│  │  • Botón "Reportar este identificador"                                  │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Página de Reporte (Formulario Anónimo)                                 │  │
│  │  • 3 campos: identificador, descripción, categoría                        │  │
│  │  • Upload de evidencia (drag & drop)                                    │  │
│  │  • Strip EXIF (client-side)                                             │  │
│  │  • Checkbox de consentimiento de ubicación                              │  │
│  │  • Página de confirmación con hash                                      │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Panel Admin (React Router, Protected Route)                              │  │
│  │  • Login (JWT + 2FA opcional)                                           │  │
│  │  • Dashboard (métricas, gráficos)                                      │  │
│  │  • Lista de reportes (filtros, paginación)                            │  │
│  │  • Detalle de reporte (desencriptar bajo demanda)                       │  │
│  │  • Perfiles y redes (timeline, mapa de ciudades)                        │  │
│  │  • Configuración (umbrales, usuarios, alertas)                          │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  Service Worker: Precache shell, runtime cache API, offline support            │
│  Manifest: icons, theme, start_url, display=standalone                         │
└─────────────────────────────────────────────────────────────────────────────────┘
          │
          ▼
┌─────────────────────────────────────────────────────────────────────────────────┐
│  BACKEND — FastAPI (Python 3.12, Async)                                         │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Módulo 001: Registro Anónimo                                              │  │
│  │  POST /api/v1/reportes → validación Pydantic → encriptación → DB         │  │
│  │  • crypto.py: AES-256-GCM con DEK por campo                              │  │
│  │  • rate_limit.py: Redis INCR + EXPIRE                                    │  │
│  │  • evidence.py: strip EXIF, thumbnail, encriptación filesystem             │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Módulo 002: Consulta Semáforo                                             │  │
│  │  GET /api/v1/validate/{identifier} → normalización → hash → query DB     │  │
│  │  • normalizer.py: E.164, email, @, URL                                   │  │
│  │  • semaforo.py: algoritmo de 4 colores                                   │  │
│  │  • cache.py: Redis cache de consultas (TTL 1h)                           │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Módulo 003: IA Triage                                                   │  │
│  │  POST /api/v1/analyze/{report_id} (async, Celery/Redis queue)            │  │
│  │  • nlp.py: spaCy preprocessing, TF-IDF vectorizer                        │  │
│  │  • model.py: LR + RF ensemble, Platt scaling                           │  │
│  │  • shap_explainer.py: SHAP values para scores >0.7                       │  │
│  │  • fairness.py: audit de disparidad entre subgrupos                      │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Módulo 004: Clustering + Perfil                                         │  │
│  │  GET /api/v1/admin/profiles/{hash} (admin only)                          │  │
│  │  GET /api/v1/admin/networks (admin only)                                 │  │
│  │  • geocode.py: MaxMind GeoLite2 local                                    │  │
│  │  • profile.py: recálculo automático al recibir reporte                   │  │
│  │  • network.py: detección de red organizada (2+ criterios)                │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Módulo 005: Panel Admin                                                 │  │
│  │  POST /api/v1/admin/auth/login → JWT                                     │  │
│  │  GET /api/v1/admin/dashboard → métricas aggregadas                       │  │
│  │  GET /api/v1/admin/reports → filtros + paginación                        │  │
│  │  POST /api/v1/admin/reports/{id}/decrypt → audit trail                   │  │
│  │  PATCH /api/v1/admin/reports/{id}/status → cambio de estado              │  │
│  │  POST /api/v1/admin/export → JSON/PDF async                              │  │
│  │  • auth.py: JWT, bcrypt, 2FA TOTP                                        │  │
│  │  • audit.py: AuditLog middleware                                         │  │
│  │  • export.py: JSON schema, PDF reportlab                                 │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Módulo 006: Pasarela Institucional                                      │  │
│  │  POST /api/v1/admin/alerts/send → manual alert                           │  │
│  │  POST /api/v1/gateway/v1/reports → API key auth                        │  │
│  │  POST /api/v1/gateway/v1/digest → API key auth                         │  │
│  │  POST /api/v1/gateway/v1/confirm → confirmación de recepción           │  │
│  │  • email.py: SMTP async (Celery + Redis)                               │  │
│  │  • digest.py: generación de digest diario/semanal/mensual                │  │
│  │  • ncmec.py: formato XML CyberTipline v2                               │  │
│  │  • retry.py: backoff exponencial (3 intentos)                            │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────────────────┘
          │
          ▼
┌─────────────────────────────────────────────────────────────────────────────────┐
│  INFRAESTRUCTURA                                                                │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  PostgreSQL 16 (Docker)                                                  │  │
│  │  • 10 tablas: reports, analyses, profiles, profile_updates, users,       │  │
│  │    audit_logs, alerts, digests, institutions, config                   │  │
│  │  • Encriptación a nivel de campo (AES-256-GCM)                           │  │
│  │  • Índices: identifier_hash, report_hash, status, level, score            │  │
│  │  • Backups diarios automáticos (pg_dump, gzip, S3)                       │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Redis 7 (Docker)                                                        │  │
│  │  • Rate limiting (IP hash → INCR + EXPIRE)                               │  │
│  │  • Cache de consultas (profile:{hash}, TTL 1h)                           │  │
│  │  • Sesiones admin (JWT blacklist al logout)                              │  │
│  │  • Queue de Celery para alertas y digest async                           │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Filesystem (Docker volume)                                              │  │
│  │  • Evidencia multimedia: UUID aleatorio, encriptado, thumbnail          │  │
│  │  • GeoLite2 database: local, sin API externa                           │  │
│  │  • Modelos de IA: pickle/joblib, versionados en código                   │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Docker Compose (3 servicios)                                            │  │
│  │  • app: FastAPI + Uvicorn (4 workers)                                    │  │
│  │  • db: PostgreSQL 16 (volume persistente)                                │  │
│  │  • cache: Redis 7 (volume persistente)                                   │  │
│  │  • nginx: reverse proxy (volume para certs)                              │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  GitHub Actions (CI/CD)                                                  │  │
│  │  • CI: tests (pytest + vitest), lint (ruff + eslint), build             │  │
│  │  • CD: deploy a staging (push a main), deploy a producción (tag)        │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
│  ┌──────────────────────────────────────────────────────────────────────────┐  │
│  │  Monitoreo (MVP)                                                       │  │
│  │  • Uptime: uptime checker externo (ping cada 5 min)                      │  │
│  │  • Logs: Docker logs, rotación automática                                  │  │
│  │  • Métricas: opcional (prometheus/grafana en futuro)                      │  │
│  └──────────────────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. STACK TÉCNICO DETALLADO

### 2.1 Frontend

| Capa | Tecnología | Versión | Uso |
|------|------------|---------|-----|
| Framework | React | 19.x | UI components, hooks, concurrent features |
| Bundler | Vite | 6.x | Dev server, HMR, production build, PWA plugin |
| CSS | Tailwind CSS | 4.x | Utility-first, responsive, dark mode |
| PWA | vite-plugin-pwa | 1.x | Service worker, manifest, precache, Workbox |
| Routing | React Router | 7.x | SPA routing, protected routes (admin) |
| Forms | React Hook Form | 7.x | Form validation, performance |
| Icons | Lucide React | 0.x | Consistent, lightweight icons |
| Charts | Recharts | 2.x | Dashboard charts (doughnut, line, bar) |
| Testing | Playwright | 1.x | E2E tests, mobile viewport, CI |
| Testing | Vitest | 3.x | Unit tests for utilities |

### 2.2 Backend

| Capa | Tecnología | Versión | Uso |
|------|------------|---------|-----|
| Framework | FastAPI | 0.115+ | Async API, auto OpenAPI, Pydantic |
| ORM | SQLAlchemy | 2.0+ | Async ORM, PostgreSQL optimized |
| Migrations | Alembic | 1.x | Database schema migrations |
| Auth | Python-jose | 3.x | JWT encoding/decoding |
| Passwords | bcrypt | 4.x | Password hashing (12 rounds) |
| 2FA | PyOTP | 2.x | TOTP generation/verification |
| Encriptación | cryptography | 43.x | AES-256-GCM, DEK/KEK |
| Rate Limit | redis-py | 5.x | Redis INCR + EXPIRE |
| Email | Celery + Redis | 5.x + 7.x | Async task queue for alerts/digest |
| SMTP | aiosmtplib | 4.x | Async SMTP client |
| PDF | WeasyPrint | 63.x | HTML → PDF (institutional reports) |
| NLP | spaCy | 3.7+ | Tokenization, lemmatization, Spanish |
| ML | scikit-learn | 1.5+ | LR + RF, TF-IDF, calibration |
| SHAP | shap | 0.46+ | Explainability for ML model |
| Geocoding | geoip2 | 4.x | MaxMind GeoLite2 local database |
| Testing | pytest | 8.x | Unit + integration tests |
| Testing | pytest-asyncio | 0.x | Async test support |
| Testing | HTTPX | 0.x | TestClient for FastAPI |
| Lint | ruff | 0.x | Fast Python linter |
| Type | mypy | 1.x | Static type checking |

### 2.3 Infraestructura

| Capa | Tecnología | Versión | Uso |
|------|------------|---------|-----|
| Container | Docker | 27.x | App containerization |
| Orchestration | Docker Compose | 2.x | Local dev + production |
| Web Server | Nginx | 1.27+ | Reverse proxy, TLS, static files |
| TLS | Let's Encrypt | — | Free certificates, auto-renewal |
| Database | PostgreSQL | 16.x | Primary data store, JSONB, GIS |
| Cache/Queue | Redis | 7.x | Rate limiting, cache, Celery broker |
| OS | Ubuntu | 24.04 LTS | VPS operating system |
| CI/CD | GitHub Actions | — | Automated testing, build, deploy |
| Hosting | DigitalOcean | — | VPS Droplet (2-4GB RAM, 2 vCPUs) |
| Domain | Namecheap/Cloudflare | — | DNS + DDoS protection |
| Backup | pg_dump + S3 | — | Daily encrypted backups |
| Monitoring | Uptime Kuma | — | Self-hosted uptime monitoring |
| Logs | Docker + journald | — | Log rotation and aggregation |

---

## 3. DECISIONES DE ARQUITECTURA (ADRs)

| ADR | Decisión | Justificación | Estado |
|-----|----------|---------------|--------|
| ADR-001 | Encriptación AES-256-GCM con DEK por campo | Autenticación integrada, DEK por campo, KEK en env var | ✅ Aprobado |
| ADR-002 | PWA vs App Store | Anonimato perfecto, sin metadata de instalación, sin tienda, $0 costo | ✅ Aprobado |
| ADR-003 | Modelo NLP: LR + RF ensemble, TF-IDF, SHAP | Rápido (<500ms), interpretable, privado (local), dataset pequeño | ⬜ Pendiente |
| ADR-004 | Geocodificación: MaxMind GeoLite2 local | Gratuito, local, sin API externa, solo ciudad/país | ⬜ Pendiente |
| ADR-005 | Pasarela: email estructurado + API gateway + NCMEC | Universal, controlado, auditable, escalable | ⬜ Pendiente |

---

## 4. DIAGRAMA DE FLUJO DE DATOS

### 4.1 Flujo de Reporte Anónimo

```
Usuario (PWA)
  │
  ├── Ingresa identificador, descripción, categoría, evidencia (opcional)
  ├── Strip EXIF (client-side)
  ├── Consiente ubicación (opcional)
  │
  ▼
POST /api/v1/reportes
  │
  ├── Validación Pydantic
  ├── Rate limiting (Redis: 5/hr)
  ├── Normalización de identificador
  ├── Hash SHA-256 del identificador
  ├── Generación DEK por campo
  ├── Encriptación AES-256-GCM (reported_identifier, description, evidence)
  ├── Almacenamiento en PostgreSQL (reports)
  ├── Almacenamiento de evidencia en filesystem (UUID, encriptada)
  ├── Generación de hash de confirmación
  ├── Trigger: análisis IA async (Celery → Redis queue)
  ├── Trigger: recálculo de perfil (Celery → Redis queue)
  │
  ▼
Response 201: { report_hash, message, warning }
```

### 4.2 Flujo de Consulta Semáforo

```
Usuario (PWA)
  │
  ├── Ingresa identificador
  │
  ▼
GET /api/v1/validate/{identifier}
  │
  ├── Normalización de identificador
  ├── Hash SHA-256
  ├── Rate limiting (Redis: 10/hr)
  ├── Query PostgreSQL: agregación por identifier_hash
  ├── Cache hit? (Redis: profile:{hash}, TTL 1h)
  │   ├── Sí: retorna cache
  │   └── No: query DB, calcular semáforo, almacenar cache
  │
  ├── Cálculo de semáforo:
  │   ├── is_network → negro
  │   ├── report_count >= 3 OR score_max >= 0.8 → rojo
  │   ├── report_count >= 1 OR score_max >= 0.5 → amarillo
  │   └── default → verde
  │
  ▼
Response 200: { semaforo, report_count, score_average, score_max, categories, cities_count, is_network, message }
```

### 4.3 Flujo de Desencriptación Admin

```
Admin (Panel)
  │
  ├── Click "Desencriptar"
  ├── Ingresa razón (mínimo 20 caracteres)
  │
  ▼
POST /api/v1/admin/reports/{id}/decrypt
  │
  ├── Auth JWT (validar, no expirado)
  ├── Autorización (rol >= reviewer)
  ├── Rate limiting (10 desencriptaciones/hr/admin)
  ├── Validar razón (>= 20 chars)
  ├── Recuperar DEK encriptado de PostgreSQL
  ├── Desencriptar DEK con KEK (env var)
  ├── Desencriptar campo con DEK (en memoria, nunca en disco)
  ├── Generar evidence URL temporal (JWT, 5 min)
  ├── Registrar en AuditLog
  │
  ▼
Response 200: { decrypted_at, reported_identifier, description, evidence_url, evidence_type, audit_log_id }
  │
  ▼
Evidence URL (5 min)
  ├── Admin accede a evidence_url
  ├── Validar JWT temporal
  ├── Servir archivo encriptado desde filesystem
  ├── Desencriptar en stream (nunca en disco)
  ├── Retornar al admin
  │
  ▼
URL expirada (5 min) → 410 Gone
```

---

## 5. SEGURIDAD

### 5.1 Capas de Seguridad

| Capa | Medida | Implementación |
|------|--------|----------------|
| Transporte | TLS 1.3 | Nginx + Let's Encrypt |
| Headers | OWASP | HSTS, CSP, X-Frame-Options, X-Content-Type-Options, Referrer-Policy |
| Auth | JWT + 2FA | Python-jose + PyOTP, bcrypt 12 rounds |
| Auth API | API Key | bcrypt, rotación cada 3 meses |
| Encriptación | AES-256-GCM | cryptography library, DEK por campo, KEK en env var |
| Rate Limit | Redis | INCR + EXPIRE, diferentes límites por endpoint |
| Anonimato | Sin metadata | Nginx access_log off, no cookies, no localStorage |
| Audit | AuditLog | PostgreSQL, cada acción sensible registrada |
| Input | Validación | Pydantic, sanitización, tipo de archivo, tamaño |
| Output | Sin datos sensibles | Nunca retornar texto original, identificador real, coordenadas |
| Infra | Docker | Contenedores aislados, solo puertos necesarios expuestos |
| Backup | Cifrado | pg_dump + gzip + GPG + S3 |

### 5.2 Modelo de Amenazas (Threat Model)

| Amenaza | Probabilidad | Impacto | Mitigación |
|---------|-------------|---------|------------|
| Ataque DDoS | Media | Medio | Nginx rate limiting, Cloudflare (opcional), VPS upgrade |
| SQL Injection | Baja | Alto | SQLAlchemy ORM, Pydantic validación, sin raw SQL |
| XSS | Baja | Alto | CSP, React auto-escape, sanitización de input |
| CSRF | Baja | Medio | Sin cookies, sin sesiones, JWT en header |
| Brute force auth | Media | Medio | bcrypt 12 rounds, rate limiting login, bloqueo 15 min |
| JWT comprometido | Baja | Alto | Expiración 1h, refresh 24h, blacklist en Redis al logout |
| KEK comprometida | Baja | Catastrófico | KEK en env var, rotación manual, HSM futuro |
| Fuga de datos en logs | Baja | Catastrófico | Nunca loggear texto desencriptado, IP hasheada, audit trail |
| Insider threat (admin) | Media | Alto | Audit trail, roles, 2FA, desencriptación con razón + límite |
| Evidencia filtrada | Baja | Catastrófico | Encriptación AES-256-GCM, evidence URL temporal, sin acceso directo |

---

## 6. ESCALABILIDAD

### 6.1 MVP (0-1,000 usuarios/día)

- **VPS:** DigitalOcean Droplet 2GB RAM, 2 vCPUs ($24/mes)
- **PostgreSQL:** Docker container, 50GB SSD
- **Redis:** Docker container, 1GB RAM
- **Nginx:** Reverse proxy, TLS 1.3
- **Backup:** Daily pg_dump to S3

### 6.2 Escalado (1,000-10,000 usuarios/día)

- **VPS:** DigitalOcean Droplet 4GB RAM, 4 vCPUs ($48/mes)
- **PostgreSQL:** Managed PostgreSQL (DigitalOcean or AWS RDS) ($15-60/mes)
- **Redis:** Managed Redis (DigitalOcean or AWS ElastiCache) ($15-30/mes)
- **CDN:** Cloudflare (free tier, $0)
- **Load Balancer:** DigitalOcean Load Balancer ($12/mes)
- **Monitoring:** Prometheus + Grafana (self-hosted, $0)

### 6.3 Escalado Avanzado (10,000+ usuarios/día)

- **Kubernetes:** DigitalOcean Kubernetes (DOKS) or AWS EKS
- **PostgreSQL:** AWS RDS Multi-AZ or DigitalOcean Managed DB cluster
- **Redis:** AWS ElastiCache cluster or Redis Cloud
- **CDN:** Cloudflare Pro ($20/mes)
- **Object Storage:** AWS S3 or DigitalOcean Spaces (evidencia multimedia)
- **Queue:** Celery + Redis cluster o AWS SQS
- **Monitoring:** Datadog o New Relic (futuro)

---

## 7. COSTOS DE INFRAESTRUCTURA

| Componente | MVP (mes) | Escalado (mes) | Avanzado (mes) |
|------------|-----------|----------------|----------------|
| VPS | $24 | $48 | $200+ |
| PostgreSQL | $0 (Docker) | $40 | $150+ |
| Redis | $0 (Docker) | $30 | $100+ |
| Nginx | $0 | $12 (LB) | $50+ |
| CDN | $0 | $0 (Cloudflare free) | $20 |
| Backup S3 | $5 | $10 | $50+ |
| Domain | $1 | $1 | $1 |
| TLS | $0 (Let's Encrypt) | $0 | $0 |
| Monitoring | $0 | $0 | $100+ |
| **Total** | **$30/mes** | **$141/mes** | **$671+/mes** |

---

## 8. DIAGRAMAS DE SECUENCIA

### 8.1 Reporte Anónimo

```
Usuario -> PWA: Ingresa identificador, descripción, categoría, evidencia
PWA -> PWA: Strip EXIF, normaliza identificador
PWA -> Nginx: POST /api/v1/reportes
Nginx -> Nginx: Rate limiting (5/hr), access_log off
Nginx -> FastAPI: POST /api/v1/reportes
FastAPI -> Pydantic: Validación
FastAPI -> Redis: Rate limiting check
FastAPI -> crypto.py: Genera DEK, encripta campos
FastAPI -> PostgreSQL: INSERT INTO reports
FastAPI -> Filesystem: Almacena evidencia encriptada (UUID)
FastAPI -> Celery: Trigger analyze_report.delay(report_id)
FastAPI -> Celery: Trigger update_profile.delay(report_id)
FastAPI -> Usuario: Response 201 { report_hash }
Celery -> Redis: Queue task
Celery -> FastAPI: POST /api/v1/analyze/{report_id} (async)
```

### 8.2 Consulta Semáforo

```
Usuario -> PWA: Ingresa identificador
PWA -> PWA: Normaliza identificador
PWA -> Nginx: GET /api/v1/validate/{identifier}
Nginx -> Nginx: Rate limiting (10/hr)
Nginx -> FastAPI: GET /api/v1/validate/{identifier}
FastAPI -> normalizer.py: Normaliza y hashea
FastAPI -> Redis: GET cache:profile:{hash}
alt Cache hit
  FastAPI -> Usuario: Response 200 (cached)
else Cache miss
  FastAPI -> PostgreSQL: SELECT aggregation FROM profiles WHERE identifier_hash = ?
  FastAPI -> semaforo.py: Calcula color
  FastAPI -> Redis: SET cache:profile:{hash} TTL 1h
  FastAPI -> Usuario: Response 200
end
```

### 8.3 Alerta Automática

```
Cron (every 5 min) -> Celery: check_alerts_severe()
Celery -> PostgreSQL: SELECT reports WHERE score >= 0.85 AND status = 'nuevo' AND alert_sent = false
Celery -> PostgreSQL: SELECT institutions WHERE alert_config.severe = true
loop for each institution
  Celery -> email.py: Build email (JSON attachment + HTML)
  Celery -> SMTP: Send email async
  Celery -> PostgreSQL: INSERT INTO alerts (report_id, institution_id, status='pending')
  Celery -> PostgreSQL: UPDATE reports SET alert_sent = true
end
SMTP -> ICBF: Deliver email
ICBF -> FastAPI: POST /api/v1/gateway/v1/confirm (API key)
FastAPI -> PostgreSQL: UPDATE alerts SET status='delivered', delivered_at=NOW()
```

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Arquitectura tecnológica del Semáforo de Confianza*
