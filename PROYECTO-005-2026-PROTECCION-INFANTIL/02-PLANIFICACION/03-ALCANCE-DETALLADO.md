# ALCANCE DETALLADO — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. ALCANCE DEL PRODUCTO

El proyecto construye una **PWA de confianza comunitaria** con 6 módulos funcionales, infraestructura, y modelo de negocio freemium B2C + B2B2C.

### 1.1 Qué INCLUYE (6 Módulos + Infraestructura)

| Módulo | Nombre | Descripción | Estado | Horas |
|--------|--------|-------------|--------|-------|
| 001 | Registro Anónimo | PWA, formulario de reporte, evidencia multimedia, encriptación AES-256-GCM, rate limiting | ✅ Completado | 40h |
| 002 | Consulta Semáforo | Buscador universal de identificadores, normalización, semáforo verde/amarillo/rojo/negro | ⬜ Nuevo | 36h |
| 003 | IA Triage | NLP ensemble (LR+RF), clasificación de reportes, detección de grooming, scoring 0-1, SHAP | ⬜ Nuevo | 48h |
| 004 | Clustering + Perfil | Geocodificación MaxMind GeoLite2, clustering geográfico, perfil de identificador, detección de red organizada | ⬜ Nuevo | 54h |
| 005 | Panel Admin | Auth JWT + 2FA, dashboard, desencriptación bajo demanda, audit trail, cambio de estado, export JSON/PDF | ⬜ Nuevo | 50h |
| 006 | Pasarela Institucional | API gateway, alertas automáticas por severidad, digest diario/semanal/mensual, formatos JSON/PDF/NCMEC | ⬜ Nuevo | 48h |
| Infra | Producción | Deploy VPS, PostgreSQL 16, Redis 7, TLS 1.3, Docker, CI/CD, monitoreo, piloto | ⬜ Nuevo | 78h |
| **Total** | | | | **354h** |

### 1.2 Qué NO INCLUYE

- Investigación judicial (la plataforma genera alertas, no pruebas)
- Atención psicológica a víctimas (no es línea de atención directa)
- Operación 24/7 de respuesta humana (sistema automatizado, autoridades reciben alertas)
- Aplicaciones nativas iOS/Android (PWA en navegador es suficiente para MVP)
- Despliegue en países sin marco legal de protección infantil (requiere análisis legal por país)
- Scoring de pedofilia (número 0-100) — legalmente conservador, nunca acusar
- Evidencia pública — nunca exponer contenido de reportes
- Alertar al agresor — nunca notificar al identificador reportado
- Detección de CSAM (Child Sexual Abuse Material) en evidencia multimedia — riesgo legal y ético, fuera de MVP
- LLM externo (GPT-4, Claude) para procesamiento de reportes — privacidad, costo, latencia

---

## 2. ALCANCE POR MÓDULO

### Módulo 001: Registro Anónimo (COMPLETADO)

**Incluye:**
- PWA con formulario de reporte (3 campos: identificador, descripción, categoría)
- Upload de evidencia multimedia (imagen, video, audio, captura)
- Strip EXIF y metadata antes de encriptar
- Thumbnail para imágenes
- Encriptación AES-256-GCM por campo (identificador, descripción, evidencia)
- Rate limiting 5 reportes/hora/IP
- Hash de confirmación SHA-256 para el usuario
- Health check endpoint
- Tests unitarios + integración (≥80% cobertura)
- Docker + Docker Compose

**No incluye:**
- Auth de usuario (sin login, sin cookies, sin JWT para reportantes)
- Geocodificación (solo si usuario consiente, en Módulo 004)
- IA de clasificación (Módulo 003)
- Panel de admin (Módulo 005)

### Módulo 002: Consulta Semáforo (NUEVO)

**Incluye:**
- Página principal como buscador (no como reporte)
- Input universal: teléfono (E.164), email, @usuario, URL, nombre
- Normalización de identificadores
- Hash SHA-256 para búsqueda sin almacenar identificador en texto plano
- Algoritmo de semáforo: verde/amarillo/rojo/negro
- Respuesta agregada: conteo, score promedio, categorías, ciudades, flag de red
- Botón "Reportar este identificador" → pre-llena formulario de Módulo 001
- Rate limiting 10 consultas/hora/IP
- PWA: página principal como consulta
- Tests unitarios + integración

**No incluye:**
- Detalle de contenido de reportes (nunca se muestra texto del reporte)
- Identificador del reportante (no existe en el sistema)
- Alerta al usuario (no push, email/SMS en Premium)
- Pago en la PWA (Stripe se integra después, en MVP solo gratuito)

### Módulo 003: IA Triage (NUEVO)

**Incluye:**
- Dataset sintético de 1,500 ejemplos en español (colombiano, mexicano, argentino)
- Preprocesamiento NLP (spaCy, es_core_news_md)
- Feature extraction: TF-IDF (n-grams 1-3), embeddings distiluse (opcional), features manuales
- Lexicon de grooming (indicadores de secreción, aislamiento, progresión gradual, etc.)
- Ensemble: Logistic Regression + Random Forest, calibración Platt scaling
- AUC-ROC ≥0.80 en test holdout
- Fairness audit: disparidad <10% entre subgrupos
- Red-teaming: 0 falsos negativos de alto riesgo
- Explicabilidad SHAP para scores >0.7
- Model card (objetivo, dataset, métricas, limitaciones)
- Endpoint POST /api/analyze/{report_id} (async)
- Integración automática al recibir reporte (webhook interno)
- Modelo versionado en código
- Tests unitarios + integración

**No incluye:**
- BERT/RoBERTa (dataset insuficiente, requiere 10,000+ ejemplos)
- LLM externo (GPT-4, Claude) — privacidad, costo, latencia
- Detección de CSAM en evidencia multimedia — riesgo legal, fuera de MVP
- Entrenamiento continuo automático (re-entrenamiento trimestral manual)

### Módulo 004: Clustering + Perfil (NUEVO)

**Incluye:**
- Geocodificación con MaxMind GeoLite2 local (sin API externa)
- Solo ciudad/país aproximado, nunca coordenadas exactas
- IP se hashea y descarta inmediatamente
- Consentimiento explícito del usuario (checkbox no pre-marcado)
- Modelo `Profile`: tabla consolidada por identificador
- Algoritmo de clustering: criterios de red organizada (≥3 ciudades, ≥2 países, ≥5 reportes, score promedio >0.6, ≥3 tipos de evidencia)
- Timeline de reportes por mes/año
- Endpoint GET /api/profile/{identifier_hash} (solo admin)
- Endpoint GET /api/networks (solo admin)
- Cache Redis para perfiles (TTL 1h)
- Audit trail de cambios en perfil (ProfileUpdate)
- Tests unitarios + integración

**No incluye:**
- Mapa con coordenadas exactas (nunca se almacenan)
- Tracking de IP en tiempo real
- Geocodificación sin consentimiento
- Predicción de ubicación futura
- Análisis de red social del agresor (solo datos de reportes en la plataforma)

### Módulo 005: Panel Admin (NUEVO)

**Incluye:**
- Auth JWT (access token 1h, refresh token 24h)
- 2FA TOTP (opcional, setup por admin root)
- Roles: viewer, reviewer, supervisor, admin, root
- Dashboard: métricas de reportes, semáforo, alertas pendientes, tendencias
- Lista de reportes con filtros (fecha, score, nivel, categoría, estado, ciudad) y paginación
- Detalle de reporte: metadata, botón desencriptar
- Desencriptación bajo demanda: razón obligatoria (20 chars), límite 10/hora, evidence URL temporal (5 min)
- Audit trail: cada acción sensible registrada (login, decrypt, status change, export)
- Cambio de estado: Nuevo → En revisión → Escalado → Cerrado
- Export JSON/PDF para autoridades
- Gestión de usuarios (admin+): crear, editar rol, desactivar
- Configuración de umbrales de alerta (supervisor+)
- Tests E2E con Playwright
- Tests unitarios + integración

**No incluye:**
- Acceso al público (solo admin autorizado)
- Desencriptación masiva (solo bajo demanda, por reporte, con razón)
- Edición de contenido de reporte (solo cambio de estado, nunca editar texto)
- Eliminación de reportes (solo cambio de estado a "cerrado")
- Acceso a evidencia sin desencriptación (solo thumbnail)

### Módulo 006: Pasarela Institucional (NUEVO)

**Incluye:**
- Seed de instituciones: ICBF, Fiscalía, Policía, NCMEC
- Modelo `Institution`: API key, contacto, contrato, alert config
- Modelo `Alert`: reporte, institución, formato, estado, reintentos
- Modelo `Digest`: período, fecha, institución, conteos, contenido
- Envío de alerta por email (SMTP, async, Celery/Redis queue)
- Email estructurado: HTML + JSON attachment
- Formatos: JSON estructurado (schema v1.0), PDF institucional (branding), NCMEC CyberTipline v2
- Resumen de IA de 200 caracteres (para export, no texto original)
- Alertas automáticas por severidad (cron: severe inmediato, critical 4h, high 24h)
- Alerta red organizada: siempre inmediato, sin importar score
- Digest diario (08:00), semanal (lunes 08:00), mensual (primer día 08:00)
- Retry con backoff exponencial (3 intentos)
- API gateway con API key (X-API-Key), rate limiting 100/hr/institución
- Endpoints: POST /api/gateway/v1/reports, POST /api/gateway/v1/digest, POST /api/gateway/v1/confirm
- Confirmación de recepción por institución
- Panel admin: envío manual, generación manual de digest, configuración de umbrales y destinatarios, historial de alertas
- Tests de integración con mock servers

**No incluye:**
- Integración directa con sistema de ICBF (requiere proceso formal, 6-12 meses)
- Webhook push a institución (requiere que institución exponga endpoint, raro en gobierno)
- Portal web para institución (panel admin sirve como portal de lectura)
- Llamada telefónica automática (solo email + API gateway)
- Respuesta de institución en tiempo real (confirmación es async)

---

## 3. ALCANCE DE INFRAESTRUCTURA

**Incluye:**
- VPS cloud (DigitalOcean): $12-48/mes (Droplet 2-4GB RAM, 2 vCPUs)
- PostgreSQL 16: Docker container, backups diarios automáticos
- Redis 7: Docker container, cache + rate limiting + sesiones admin
- Nginx: reverse proxy, TLS 1.3 (Let's Encrypt), HTTP/2, rate limiting
- Docker Compose: 3 servicios (app, db, cache)
- GitHub Actions: CI (tests, lint) + CD (deploy staging → production)
- Monitoreo: uptime, logs, métricas (prometheus/grafana opcional, MVP usa uptime checker)
- Domain: semaforo.innovadataco.com (o similar)

**No incluye:**
- Kubernetes (overkill para MVP, Docker Compose es suficiente)
- CDN (Cloudflare puede añadirse después, no requerido para MVP)
- Load balancer (Nginx es suficiente hasta 1,000 req/s)
- HSM (Hardware Security Module) para KEK (futuro, rotación manual por ahora)
- Multi-region deploy (futuro, single region es suficiente para LATAM)

---

## 4. ALCANCE DE MODELO DE NEGOCIO

**Incluye:**
- Freemium B2C: 3 consultas/día gratis, Premium $2.99/mes (ilimitado + alertas + historial)
- B2B2C Colegios: Panel de consulta para padres, reportes ilimitados, alertas institucionales
- B2G Piloto: 1 contrato piloto con ICBF o Fiscalía (gratuito 3 meses, luego contrato)
- Stripe para pagos B2C
- Facturación manual para B2B2C (futuro: Stripe Billing o similar)

**No incluye:**
- App nativa iOS/Android (PWA es suficiente)
- Marketplace de integraciones (futuro)
- API pública para terceros (solo API gateway institucional con contrato)
- Publicidad en la PWA (sin ads, sin tracking)
- Venta de datos (nunca, los datos son encriptados y no se venden)

---

## 5. ALCANCE DE DOCUMENTACIÓN

**Incluye:**
- PM2 completo: 13 documentos en IDC_PROYECTOS
- SDD: 6 specs + 6 plans + 6 tasks + 5 ADRs + gaps + estructura-datos + api-reference
- OpenAPI auto-generado por FastAPI (/docs)
- Model card (Módulo 003)
- Evaluation report (Módulo 003)
- Red-teaming report (Módulo 003)
- Fairness report (Módulo 003)
- Runbook de operación (deploy, monitoreo, respuesta a incidentes)
- Guía de seguridad (encriptación, auth, rate limiting)
- Manual de integración para instituciones (Módulo 006)

**No incluye:**
- Certificación ISO 27001 (futuro, post-piloto)
- Certificación SOC 2 (futuro, post-piloto)
- Auditoría de seguridad externa (planificada para noviembre 2026, no incluida en desarrollo)
- Documentación en inglés (MVP solo español, i18n estructura preparada para futuro)

---

## 6. CRITERIOS DE ACEPTACIÓN POR FASE

### Fase 1: Registro Anónimo (COMPLETADO)
- [x] Formulario funciona en móvil (320px+)
- [x] POST /api/reportes retorna hash único de 64 caracteres
- [x] Encriptación AES-256-GCM validada
- [x] Rate limiting funciona (6to reporte = 429)
- [x] Evidencia multimedia se encripta y almacena
- [x] PWA instala desde navegador
- [x] Tests ≥ 80% cobertura

### Fase 2: Consulta Semáforo
- [ ] Endpoint /api/validate/{identifier} funcional
- [ ] Normalización de identificadores correcta
- [ ] Semáforo calcula correctamente (4 colores)
- [ ] No expone información identificable del reportante
- [ ] Rate limiting funciona (11ra consulta = 429)
- [ ] Tests ≥ 80% cobertura

### Fase 3: IA Triage
- [ ] Dataset 1,500 ejemplos generado y etiquetado
- [ ] Modelo con AUC-ROC ≥0.80 en test
- [ ] Fairness audit: disparidad <10%
- [ ] Red-teaming: 0 falsos negativos de alto riesgo
- [ ] Endpoint /api/analyze/{report_id} funcional (async)
- [ ] SHAP integrado para scores >0.7
- [ ] Model card aprobado
- [ ] Tests ≥ 80% cobertura

### Fase 4: Clustering + Perfil
- [ ] Clustering detecta mismo ID desde ≥3 ciudades
- [ ] Perfil genera tabla completa y precisa
- [ ] Alerta de red organizada funciona automáticamente
- [ ] Geocodificación sin exponer coordenadas exactas
- [ ] Tests ≥ 80% cobertura

### Fase 5: Panel Admin
- [ ] Auth JWT funcional (login, refresh, 2FA)
- [ ] Dashboard muestra métricas en tiempo real
- [ ] Desencriptación bajo demanda con audit trail
- [ ] Cambio de estado funciona (4 estados)
- [ ] Export JSON y PDF genera archivos correctos
- [ ] Roles funcionan (5 roles)
- [ ] Tests E2E con Playwright
- [ ] Tests ≥ 80% cobertura

### Fase 6: Pasarela Institucional
- [ ] Alerta severe enviada en <15 min
- [ ] Alerta red organizada enviada inmediatamente
- [ ] Digest diario, semanal, mensual funcionan
- [ ] API gateway funcional con API key
- [ ] Formatos JSON, PDF, NCMEC generados correctamente
- [ ] Tests de integración con mocks
- [ ] Tests ≥ 80% cobertura

### Fase 7: Producción + Piloto
- [ ] Deploy en VPS funcional
- [ ] TLS 1.3 activo
- [ ] Monitoreo 24/7 operativo
- [ ] OWASP ZAP: 0 vulnerabilidades críticas
- [ ] Piloto con 1 colegio B2B2C completado
- [ ] 500+ reportes reales procesados
- [ ] 1 contrato o carta de intención firmada

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Alcance detallado del Semáforo de Confianza*
