# VISIÓN DEL PROYECTO — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. VISIÓN TÉCNICA

Construir una **PWA de confianza comunitaria** para protección infantil que combine:

- **Frontend:** React 19 + Vite + Tailwind CSS, como PWA (Progressive Web App) sin fricción, sin tracking, sin metadata de instalación.
- **Backend:** FastAPI + SQLAlchemy + PostgreSQL 16, con encriptación AES-256-GCM por campo para todos los datos sensibles.
- **Inteligencia Artificial:** Ensemble de Logistic Regression + Random Forest para clasificación de reportes, detección de grooming, scoring de riesgo (0-1), y explicabilidad SHAP.
- **Infraestructura:** Docker + Docker Compose, VPS cloud (DigitalOcean), Nginx + TLS 1.3, Redis para cache y rate limiting, GitHub Actions CI/CD.
- **Privacidad:** Anonimato absoluto (sin IP, sin cookies, sin localStorage, sin metadata), encriptación industrial, sin acusar, sin exponer al reportante, sin alertar al agresor.

---

## 2. VISIÓN DE PRODUCTO

> **"Cada padre, cada colegio, cada comunidad, puede consultar si un contacto es seguro para sus menores — y reportar si no lo es, sin miedo, sin exposición, sin fricción."**

### La Experiencia del Usuario

1. **Consulta:** Un padre recibe un mensaje de un número desconocido pidiendo fotos de su hija. Abre la PWA, ingresa el número, y recibe: 🔴 ROJO — "Este número tiene 7 reportes de contacto inapropiado con menores, desde 4 ciudades. Posible red organizada." Decide bloquear el número y reportar el mensaje.

2. **Reporte:** Un profesor de colegio nota que un alumno recibe mensajes inapropiados de un @usuario de Instagram. Abre la PWA, ingresa el @usuario, describe el incidente, sube una captura de pantalla, y envía. Recibe un hash de confirmación. Nadie sabe quién reportó.

3. **Colegio:** Un colegio suscrito al plan B2B2C recibe un alerta semanal: "3 estudiantes consultaron el mismo identificador esta semana. 1 reporte nuevo. Revisar panel institucional."

### La Experiencia de la Autoridad

1. La Fiscalía recibe un alerta automática: reporte SEVERE, score 0.87, grooming detectado. Recibe JSON estructurado con resumen de IA, perfil del identificador (7 reportes, 4 ciudades), y evidencia multimedia.

2. El ICBF recibe un digest semanal: 23 reportes, 3 severe, 1 red organizada detectada.

3. La Policía consulta el API gateway: "Dame todos los reportes de esta semana con level >= high." Recibe JSON estructurado, validado, sin datos identificables del reportante.

---

## 3. DIFERENCIADORES TÉCNICOS

| Diferenciador | Innovadataco | Competencia Genérica |
|---------------|--------------|---------------------|
| Anonimato | Sin IP, sin cookies, sin metadata, sin tracking | Requiere registro, cookies, metadata |
| Encriptación | AES-256-GCM por campo, incluyendo evidencia multimedia | Encriptación a nivel de BD o sin encriptación |
| PWA | Sin descarga, sin tienda, sin SDKs de tracking | Requiere App Store, metadata de instalación |
| IA de triage | Clasificación automática, detección de grooming, explicabilidad SHAP | Sin IA o IA caja negra sin explicabilidad |
| Semáforo | Visualización clara de riesgo comunitario, sin acusar | Sin buscador preventivo |
| Clustering | Detección de redes organizadas (mismo ID desde ≥3 ciudades) | Sin análisis de patrones geográficos |
| LATAM | Diseñado para español colombiano, infraestructura variable, costos bajos | Diseñado para EE.UU./Europa |
| Legal | Legalmente conservador: nunca acusar, solo "alerta comunitaria" | Puede generar responsabilidad legal |

---

## 4. ARQUITECTURA DE MÓDULOS (Visión Técnica)

```
┌──────────────────────────────────────────────────────────────────────────┐
│                         USUARIO (Navegador Móvil/Web)                     │
│                   Sin login, sin cookies, sin IP guardada                │
└──────────────────────────┬───────────────────────────────────────────────┘
                           │ HTTPS
                           ▼
┌──────────────────────────────────────────────────────────────────────────┐
│  FRONTEND — PWA (React 19 + Vite + Tailwind CSS)                        │
│  ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐             │
│  │ Consulta        │ │ Reporte         │ │ Panel Admin     │             │
│  │ Semáforo        │ │ Anónimo         │ │ (Auth JWT)      │             │
│  │ (Pública)       │ │ (Pública)       │ │ (Protegido)     │             │
│  └─────────────────┘ └─────────────────┘ └─────────────────┘             │
└──────────────────────────┬───────────────────────────────────────────────┘
                           │
                           ▼
┌──────────────────────────────────────────────────────────────────────────┐
│  BACKEND — FastAPI + SQLAlchemy + PostgreSQL                            │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │ MÓDULO 001: Registro Anónimo (COMPLETADO)                         │  │
│  │ POST /api/reportes — Encriptación AES-256-GCM, rate limiting      │  │
│  └────────────────────────────────────────────────────────────────────┘  │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │ MÓDULO 002: Consulta Semáforo (NUEVO)                             │  │
│  │ GET /api/validate/{identifier} — Estadísticas agregadas           │  │
│  └────────────────────────────────────────────────────────────────────┘  │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │ MÓDULO 003: IA Triage (NUEVO)                                   │  │
│  │ NLP para clasificación + detección grooming + scoring + SHAP     │  │
│  └────────────────────────────────────────────────────────────────────┘  │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │ MÓDULO 004: Clustering + Perfil (NUEVO)                          │  │
│  │ Geocodificación + detección red organizada + timeline            │  │
│  └────────────────────────────────────────────────────────────────────┘  │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │ MÓDULO 005: Panel Admin (NUEVO)                                │  │
│  │ Dashboard + auth + desencriptación + audit trail + export        │  │
│  └────────────────────────────────────────────────────────────────────┘  │
│  ┌────────────────────────────────────────────────────────────────────┐  │
│  │ MÓDULO 006: Pasarela Institucional (NUEVO)                      │  │
│  │ API gateway + alertas + digest + NCMEC + formatos estándar      │  │
│  └────────────────────────────────────────────────────────────────────┘  │
└──────────────────────────┬───────────────────────────────────────────────┘
                           │
                           ▼
┌──────────────────────────────────────────────────────────────────────────┐
│  INFRAESTRUCTURA                                                        │
│  • PostgreSQL 16 (datos encriptados)                                    │
│  • Redis (rate limiting + cache + sesiones admin)                       │
│  • Docker + Docker Compose                                              │
│  • GitHub Actions CI/CD                                                 │
│  • VPS Cloud (DigitalOcean)                                             │
│  • Nginx reverse proxy + TLS 1.3 (Let's Encrypt)                        │
└──────────────────────────────────────────────────────────────────────────┘
```

---

## 5. STACK TÉCNICO

| Capa | Tecnología | Versión | Justificación |
|------|------------|---------|---------------|
| Frontend | React 19 | 19.x | Latest, concurrent features, server components |
| Bundler | Vite | 6.x | Rápido, HMR, tree-shaking, PWA support |
| CSS | Tailwind CSS | 4.x | Utility-first, responsive, dark mode, performance |
| PWA | vite-plugin-pwa + Workbox | 7.x | Service worker, precache, offline support |
| Backend | FastAPI | 0.115+ | Async, auto-documentación OpenAPI, Pydantic |
| ORM | SQLAlchemy | 2.0+ | Mature, async support, PostgreSQL optimized |
| Base de datos | PostgreSQL | 16.x | JSONB, GIS, robust, open source |
| Cache | Redis | 7.x | Rate limiting, session store, cache |
| Encriptación | Python cryptography | 43.x | AES-256-GCM, nativo, auditable |
| IA/ML | scikit-learn | 1.5+ | LR + RF, rápido, interpretable, CPU |
| NLP | spaCy + es_core_news_md | 3.7+ | Tokenización, lematización, español |
| Embeddings | transformers (opt) | 4.x | distiluse-base-multilingual (feature adicional) |
| Explicabilidad | SHAP | 0.46+ | SHAP values, interpretable ML |
| Container | Docker + Compose | 27.x | Reproducible, portable, scalable |
| CI/CD | GitHub Actions | — | Tests, lint, build, deploy |
| Deploy | DigitalOcean + Nginx | — | VPS $12-48/mes, Let's Encrypt, LatAm-friendly |
| Tests | pytest + Playwright | — | Unit + integration + E2E |

---

## 6. PRINCIPIOS DE ARQUITECTURA

1. **Privacidad por diseño:** Anonimato absoluto desde el primer día. Sin IP, sin cookies, sin metadata.
2. **Seguridad por capas:** Encriptación a nivel de campo, auth JWT con 2FA, rate limiting, audit trail, TLS 1.3.
3. **Escalabilidad horizontal:** Docker + stateless backend + PostgreSQL + Redis. Load balancer cuando se necesite.
4. **Mantenibilidad:** Código limpio, tests ≥80%, documentación SDD, ADRs, model cards.
5. **Legalmente conservador:** Nunca acusar, nunca exponer al reportante, nunca alertar al agresor. La plataforma es un canal, no un operador judicial.
6. **Bajo costo:** Stack open source, VPS económico, sin dependencias de SaaS costosos. $50-200/mes en producción.
7. **Rápido:** Tiempo de respuesta <500ms para consultas, <2s para reportes, <500ms para inferencia de IA.

---

## 7. CRITERIOS DE ÉXITO TÉCNICO

| Criterio | Métrica | Meta | Fase |
|----------|---------|------|------|
| Tiempo de consulta | 95 percentile | <500ms | 002 |
| Tiempo de reporte | 95 percentile | <2s | 001 |
| Tiempo de inferencia IA | 95 percentile | <500ms | 003 |
| Cobertura de tests | pytest + vitest | ≥80% | Todos |
| Uptime | Monitoreo | 99.5% | Producción |
| Vulnerabilidades críticas | OWASP ZAP | 0 | Producción |
| Alerta severe enviada | Cron job | <15 min | 006 |
| Encriptación | Validación | 100% campos sensibles | 001 |
| Anonimato | Auditoría | 0 metadata identificable | 001 |

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Visión técnica y de producto del Semáforo de Confianza*
