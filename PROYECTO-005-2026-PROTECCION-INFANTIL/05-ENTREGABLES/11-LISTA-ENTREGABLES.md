# LISTA DE ENTREGABLES — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. ENTREGABLES POR FASE

### Fase 1: Registro Anónimo (COMPLETADO — Junio 2026)

| # | Entregable | Formato | Ubicación | Estado | Responsable |
|---|------------|---------|-----------|--------|-------------|
| 1.1 | Código fuente: formulario PWA | React 19 + Vite + Tailwind | `github.com/Innovadataco/Desarrollos/PROYECTO-005-PROTECCION-INFANTIL/frontend/` | ✅ | ODIN |
| 1.2 | Código fuente: API de reporte | FastAPI + SQLAlchemy | `github.com/Innovadataco/Desarrollos/PROYECTO-005-PROTECCION-INFANTIL/backend/` | ✅ | ODIN |
| 1.3 | Encriptación AES-256-GCM | Python cryptography | `backend/src/crypto.py` | ✅ | ODIN |
| 1.4 | Rate limiting | Redis INCR + EXPIRE | `backend/src/rate_limit.py` | ✅ | ODIN |
| 1.5 | Evidence multimedia: strip EXIF, thumbnail | Pillow + Python | `backend/src/evidence.py` | ✅ | ODIN |
| 1.6 | Docker + Docker Compose | YAML | `docker-compose.yml` | ✅ | ODIN |
| 1.7 | Tests unitarios + integración | pytest | `backend/tests/` | ✅ | ODIN |
| 1.8 | SPEC-001: Registro Anónimo | Markdown | `docs/specs/001-registro-anonimo/spec.md` | ✅ | ZEUS |
| 1.9 | PLAN-001: Registro Anónimo | Markdown | `docs/specs/001-registro-anonimo/plan.md` | ✅ | ZEUS |
| 1.10 | TASKS-001: Registro Anónimo | Markdown | `docs/specs/001-registro-anonimo/tasks.md` | ✅ | ZEUS |
| 1.11 | ADR-001: Encriptación | Markdown | `docs/ADR-001-seguridad.md` | ✅ | ZEUS |
| 1.12 | ADR-002: PWA vs App Store | Markdown | `docs/ADR-002-pwa.md` | ✅ | ZEUS |
| 1.13 | README.md | Markdown | `README.md` | ✅ | ZEUS |

### Fase 2: Consulta Semáforo (NUEVO — Julio 2026)

| # | Entregable | Formato | Ubicación | Estado | Responsable |
|---|------------|---------|-----------|--------|-------------|
| 2.1 | Código: buscador PWA | React 19 | `frontend/src/pages/SearchPage.tsx` | ⬜ | ODIN |
| 2.2 | Código: normalización de identificadores | Python | `backend/src/normalizer.py` | ⬜ | ODIN |
| 2.3 | Código: algoritmo de semáforo | Python | `backend/src/semaforo.py` | ⬜ | ODIN |
| 2.4 | Código: endpoint GET /api/validate | FastAPI | `backend/src/api/validate.py` | ⬜ | ODIN |
| 2.5 | Código: cache de consultas | Redis | `backend/src/cache.py` | ⬜ | ODIN |
| 2.6 | Landing page (SEO) | React 19 | `frontend/src/pages/LandingPage.tsx` | ⬜ | Zaira + ODIN |
| 2.7 | Tests unitarios + integración | pytest | `backend/tests/test_validate.py` | ⬜ | ODIN |
| 2.8 | SPEC-002: Consulta Semáforo | Markdown | `docs/specs/002-consulta-semaforo/spec.md` | ✅ | ZEUS |
| 2.9 | PLAN-002: Consulta Semáforo | Markdown | `docs/specs/002-consulta-semaforo/plan.md` | ✅ | ZEUS |
| 2.10 | TASKS-002: Consulta Semáforo | Markdown | `docs/specs/002-consulta-semaforo/tasks.md` | ✅ | ZEUS |
| 2.11 | Stripe integration (MVP: gratuito) | JavaScript | `frontend/src/stripe/` | ⬜ | ODIN |

### Fase 3: IA Triage (NUEVO — Agosto 2026)

| # | Entregable | Formato | Ubicación | Estado | Responsable |
|---|------------|---------|-----------|--------|-------------|
| 3.1 | Dataset sintético 1,500 ejemplos | CSV/JSON | `data/dataset_synthetic_1500.csv` | ⬜ | ODIN |
| 3.2 | Código: preprocesamiento NLP | Python + spaCy | `backend/src/nlp.py` | ⬜ | ODIN |
| 3.3 | Código: feature extraction (TF-IDF) | Python + scikit-learn | `backend/src/features.py` | ⬜ | ODIN |
| 3.4 | Código: lexicon de grooming | Python + JSON | `backend/src/lexicon_grooming.json` | ⬜ | ODIN |
| 3.5 | Código: modelo ensemble (LR + RF) | Python + scikit-learn | `backend/src/model.py` | ⬜ | ODIN |
| 3.6 | Código: Platt scaling | Python + scikit-learn | `backend/src/calibration.py` | ⬜ | ODIN |
| 3.7 | Código: SHAP explicabilidad | Python + shap | `backend/src/shap_explainer.py` | ⬜ | ODIN |
| 3.8 | Código: fairness audit | Python | `backend/src/fairness.py` | ⬜ | ODIN |
| 3.9 | Código: red-teaming | Python | `backend/src/red_teaming.py` | ⬜ | ODIN |
| 3.10 | Código: endpoint async /api/analyze | FastAPI + Celery | `backend/src/api/analyze.py` | ⬜ | ODIN |
| 3.11 | Model card | Markdown | `docs/model-card.md` | ⬜ | ODIN + ZEUS |
| 3.12 | Evaluation report | Markdown | `docs/evaluation-report.md` | ⬜ | ODIN + ZEUS |
| 3.13 | Tests unitarios + integración | pytest | `backend/tests/test_model.py` | ⬜ | ODIN |
| 3.14 | SPEC-003: IA Triage | Markdown | `docs/specs/003-ia-triage/spec.md` | ✅ | ZEUS |
| 3.15 | PLAN-003: IA Triage | Markdown | `docs/specs/003-ia-triage/plan.md` | ✅ | ZEUS |
| 3.16 | TASKS-003: IA Triage | Markdown | `docs/specs/003-ia-triage/tasks.md` | ✅ | ZEUS |
| 3.17 | ADR-003: Modelo NLP | Markdown | `docs/ADR-003-ia-triage.md` | ✅ | ZEUS |

### Fase 4: Clustering + Perfil (NUEVO — Septiembre 2026)

| # | Entregable | Formato | Ubicación | Estado | Responsable |
|---|------------|---------|-----------|--------|-------------|
| 4.1 | Código: geocodificación MaxMind GeoLite2 | Python + geoip2 | `backend/src/geocode.py` | ⬜ | ODIN |
| 4.2 | Código: modelo Profile (SQLAlchemy) | Python | `backend/src/models/profile.py` | ⬜ | ODIN |
| 4.3 | Código: modelo ProfileUpdate (audit) | Python | `backend/src/models/profile_update.py` | ⬜ | ODIN |
| 4.4 | Código: algoritmo de clustering | Python | `backend/src/clustering.py` | ⬜ | ODIN |
| 4.5 | Código: detección de red organizada | Python | `backend/src/network_detection.py` | ⬜ | ODIN |
| 4.6 | Código: recálculo automático de perfil | Python + Celery | `backend/src/profile_update.py` | ⬜ | ODIN |
| 4.7 | Código: cache Redis de perfiles | Python + Redis | `backend/src/profile_cache.py` | ⬜ | ODIN |
| 4.8 | Código: timeline de reportes | Python | `backend/src/timeline.py` | ⬜ | ODIN |
| 4.9 | Código: endpoints /api/profile y /api/networks | FastAPI | `backend/src/api/profile.py` | ⬜ | ODIN |
| 4.10 | Tests unitarios + integración | pytest | `backend/tests/test_clustering.py` | ⬜ | ODIN |
| 4.11 | SPEC-004: Clustering + Perfil | Markdown | `docs/specs/004-clustering-perfil/spec.md` | ✅ | ZEUS |
| 4.12 | PLAN-004: Clustering + Perfil | Markdown | `docs/specs/004-clustering-perfil/plan.md` | ✅ | ZEUS |
| 4.13 | TASKS-004: Clustering + Perfil | Markdown | `docs/specs/004-clustering-perfil/tasks.md` | ✅ | ZEUS |
| 4.14 | ADR-004: Clustering + Privacidad | Markdown | `docs/ADR-004-clustering.md` | ✅ | ZEUS |

### Fase 5: Panel Admin (NUEVO — Octubre 2026)

| # | Entregable | Formato | Ubicación | Estado | Responsable |
|---|------------|---------|-----------|--------|-------------|
| 5.1 | Código: auth JWT (login, refresh, logout) | Python + FastAPI | `backend/src/auth/jwt.py` | ⬜ | ODIN |
| 5.2 | Código: 2FA TOTP | Python + PyOTP | `backend/src/auth/totp.py` | ⬜ | ODIN |
| 5.3 | Código: modelo de roles (5 roles) | Python + SQLAlchemy | `backend/src/models/role.py` | ⬜ | ODIN |
| 5.4 | Código: dashboard de métricas | React 19 + Recharts | `frontend/src/pages/Admin/Dashboard.tsx` | ⬜ | ODIN |
| 5.5 | Código: lista de reportes con filtros | React 19 + TanStack Table | `frontend/src/pages/Admin/ReportsList.tsx` | ⬜ | ODIN |
| 5.6 | Código: detalle de reporte | React 19 | `frontend/src/pages/Admin/ReportDetail.tsx` | ⬜ | ODIN |
| 5.7 | Código: desencriptación bajo demanda | Python + FastAPI | `backend/src/api/decrypt.py` | ⬜ | ODIN |
| 5.8 | Código: audit trail (AuditLog) | Python + SQLAlchemy | `backend/src/models/audit_log.py` | ⬜ | ODIN |
| 5.9 | Código: cambio de estado de reporte | Python + FastAPI | `backend/src/api/status.py` | ⬜ | ODIN |
| 5.10 | Código: export JSON (schema v1.0) | Python + FastAPI | `backend/src/export/json.py` | ⬜ | ODIN |
| 5.11 | Código: export PDF (reportlab) | Python + WeasyPrint | `backend/src/export/pdf.py` | ⬜ | ODIN |
| 5.12 | Código: gestión de usuarios | React 19 + FastAPI | `frontend/src/pages/Admin/Users.tsx` | ⬜ | ODIN |
| 5.13 | Código: configuración de umbrales | React 19 + FastAPI | `frontend/src/pages/Admin/Config.tsx` | ⬜ | ODIN |
| 5.14 | Tests E2E con Playwright | JavaScript | `frontend/e2e/admin.spec.ts` | ⬜ | ODIN + Juan |
| 5.15 | Tests unitarios + integración | pytest | `backend/tests/test_admin.py` | ⬜ | ODIN |
| 5.16 | SPEC-005: Panel Admin | Markdown | `docs/specs/005-panel-admin/spec.md` | ✅ | ZEUS |
| 5.17 | PLAN-005: Panel Admin | Markdown | `docs/specs/005-panel-admin/plan.md` | ✅ | ZEUS |
| 5.18 | TASKS-005: Panel Admin | Markdown | `docs/specs/005-panel-admin/tasks.md` | ✅ | ZEUS |

### Fase 6: Pasarela Institucional (NUEVO — Noviembre 2026)

| # | Entregable | Formato | Ubicación | Estado | Responsable |
|---|------------|---------|-----------|--------|-------------|
| 6.1 | Código: modelo Institution + seed | Python + SQLAlchemy | `backend/src/models/institution.py` | ⬜ | ODIN |
| 6.2 | Código: modelo Alert + Digest | Python + SQLAlchemy | `backend/src/models/alert.py` | ⬜ | ODIN |
| 6.3 | Código: envío de alerta por email (SMTP) | Python + Celery | `backend/src/email/alert.py` | ⬜ | ODIN |
| 6.4 | Código: formato JSON estructurado | Python | `backend/src/export/json_institutional.py` | ⬜ | ODIN |
| 6.5 | Código: formato PDF institucional | Python + WeasyPrint | `backend/src/export/pdf_institutional.py` | ⬜ | ODIN |
| 6.6 | Código: formato NCMEC (CyberTipline) | Python + lxml | `backend/src/export/ncmec.py` | ⬜ | ODIN |
| 6.7 | Código: resumen de IA | Python | `backend/src/summary.py` | ⬜ | ODIN |
| 6.8 | Código: alertas automáticas por severidad (cron) | Python + Celery | `backend/src/cron/alerts.py` | ⬜ | ODIN |
| 6.9 | Código: digest diario/semanal/mensual (cron) | Python + Celery | `backend/src/cron/digest.py` | ⬜ | ODIN |
| 6.10 | Código: retry con backoff | Python | `backend/src/retry.py` | ⬜ | ODIN |
| 6.11 | Código: API gateway (X-API-Key) | Python + FastAPI | `backend/src/api/gateway.py` | ⬜ | ODIN |
| 6.12 | Código: confirmación de recepción | Python + FastAPI | `backend/src/api/confirm.py` | ⬜ | ODIN |
| 6.13 | Código: panel admin alertas + digest + config | React 19 | `frontend/src/pages/Admin/Alerts.tsx` | ⬜ | ODIN |
| 6.14 | Tests de integración con mock servers | pytest | `backend/tests/test_gateway.py` | ⬜ | ODIN |
| 6.15 | Tests unitarios + integración | pytest | `backend/tests/test_pasarela.py` | ⬜ | ODIN |
| 6.16 | SPEC-006: Pasarela Institucional | Markdown | `docs/specs/006-pasarela-institucional/spec.md` | ✅ | ZEUS |
| 6.17 | PLAN-006: Pasarela Institucional | Markdown | `docs/specs/006-pasarela-institucional/plan.md` | ✅ | ZEUS |
| 6.18 | TASKS-006: Pasarela Institucional | Markdown | `docs/specs/006-pasarela-institucional/tasks.md` | ✅ | ZEUS |
| 6.19 | ADR-005: Pasarela Institucional | Markdown | `docs/ADR-005-pasarela.md` | ✅ | ZEUS |
| 6.20 | Manual de integración para instituciones | Markdown | `docs/institution-integration-guide.md` | ⬜ | ZEUS |

### Fase 7: Producción + Piloto (NUEVO — Diciembre 2026)

| # | Entregable | Formato | Ubicación | Estado | Responsable |
|---|------------|---------|-----------|--------|-------------|
| 7.1 | VPS deploy (DigitalOcean) | Droplet | `api.semaforo.innovadataco.com` | ⬜ | ODIN |
| 7.2 | TLS 1.3 + dominio propio | Let's Encrypt | `semaforo.innovadataco.com` | ⬜ | ODIN |
| 7.3 | Monitoreo 24/7 (Uptime Kuma) | Docker | `monitor.innovadataco.com` | ⬜ | ODIN |
| 7.4 | OWASP ZAP: 0 vulnerabilidades | Reporte | `docs/security/owasp-zap-report.pdf` | ⬜ | ODIN |
| 7.5 | Pentest externo | Reporte | `docs/security/pentest-report.pdf` | ⬜ | Firma externa |
| 7.6 | Piloto con 1 colegio B2B2C | Demo + feedback | `docs/pilot/colegio-piloto-report.md` | ⬜ | Zaira + ODIN |
| 7.7 | 500+ reportes reales | PostgreSQL | `production DB` | ⬜ | Usuarios |
| 7.8 | 1 contrato o carta de intención | PDF firmado | `docs/contracts/` | ⬜ | Jelkin |
| 7.9 | Manual de operación | Markdown | `docs/runbook.md` | ⬜ | ZEUS + ODIN |
| 7.10 | Marketing de lanzamiento | Redes sociales, PR | `instagram.com/semaforodeconfianza` | ⬜ | Zaira |
| 7.11 | Guía de seguridad | Markdown | `docs/security-guide.md` | ⬜ | ZEUS + ODIN |
| 7.12 | Guía de privacidad | Markdown | `docs/privacy-guide.md` | ⬜ | ZEUS + Diana |
| 7.13 | Términos de servicio | HTML | `semaforo.innovadataco.com/tos` | ⬜ | Diana |
| 7.14 | Política de privacidad | HTML | `semaforo.innovadataco.com/privacy` | ⬜ | Diana |
| 7.15 | OpenAPI auto-generado | YAML/JSON | `api.semaforo.innovadataco.com/docs` | ⬜ | FastAPI (auto) |
| 7.16 | Estructura de datos (schema SQL) | SQL | `docs/schema.sql` | ✅ | ZEUS |
| 7.17 | API reference completo | Markdown | `docs/api-reference.md` | ✅ | ZEUS |
| 7.18 | Gaps documentados | Markdown | `docs/gaps.md` | ✅ | ZEUS |
| 7.19 | PM2 completo | Markdown | `IDC_PROYECTOS/PROYECTO-005-2026-PROTECCION-INFANTIL/` | ✅ | ZEUS |
| 7.20 | SDD completo | Markdown | `docs/specs/` + `docs/` | Parcial | ZEUS + ODIN |
| 7.21 | Model card | Markdown | `docs/model-card.md` | ⬜ | ODIN + ZEUS |
| 7.22 | Evaluation report | Markdown | `docs/evaluation-report.md` | ⬜ | ODIN + ZEUS |
| 7.23 | Fairness report | Markdown | `docs/fairness-report.md` | ⬜ | ODIN + ZEUS |
| 7.24 | Red-teaming report | Markdown | `docs/red-teaming-report.md` | ⬜ | ODIN + ZEUS |
| 7.25 | Licencia AGPL v3 | Texto | `LICENSE` | ⬜ | Diana |
| 7.26 | Código en repositorio GitHub | Git | `github.com/Innovadataco/Desarrollos/PROYECTO-005-PROTECCION-INFANTIL/` | Parcial | ODIN |
| 7.27 | CI/CD (GitHub Actions) | YAML | `.github/workflows/ci-cd.yml` | ⬜ | ODIN |
| 7.28 | Docker images en registry | Docker | `ghcr.io/innovadataco/semaforo` | ⬜ | GitHub Actions |
| 7.29 | Database migrations (Alembic) | Python | `backend/migrations/` | ⬜ | ODIN |
| 7.30 | Seed de admin root | Python | `backend/scripts/seed_admin.py` | ⬜ | ODIN |
| 7.31 | Backup script | Shell + Python | `scripts/backup.sh` | ⬜ | ODIN |
| 7.32 | Rotación de KEK script | Python | `scripts/rotate_kek.py` | ⬜ | ODIN |
| 7.33 | Log rotation | logrotate | `/etc/logrotate.d/semaforo` | ⬜ | ODIN |
| 7.34 | Nginx config | Nginx | `nginx/semaforo.conf` | ⬜ | ODIN |
| 7.35 | Environment template | .env | `.env.template` | ⬜ | ODIN |
| 7.36 | CONTRIBUTING.md | Markdown | `CONTRIBUTING.md` | ⬜ | ZEUS |
| 7.37 | CODE_OF_CONDUCT.md | Markdown | `CODE_OF_CONDUCT.md` | ⬜ | ZEUS |
| 7.38 | CHANGELOG.md | Markdown | `CHANGELOG.md` | ⬜ | ZEUS |
| 7.39 | Versión 1.0.0 tag | Git | `git tag v1.0.0` | ⬜ | ODIN |

---

## 2. RESUMEN DE ENTREGABLES

| Fase | Estado | Entregables | Completados | Pendientes | % Completado |
|------|--------|-------------|-------------|------------|--------------|
| 1: Registro Anónimo | ✅ | 13 | 13 | 0 | 100% |
| 2: Consulta Semáforo | ⬜ | 11 | 3 | 8 | 27% |
| 3: IA Triage | ⬜ | 17 | 4 | 13 | 24% |
| 4: Clustering + Perfil | ⬜ | 14 | 4 | 10 | 29% |
| 5: Panel Admin | ⬜ | 18 | 3 | 15 | 17% |
| 6: Pasarela Institucional | ⬜ | 20 | 4 | 16 | 20% |
| 7: Producción + Piloto | ⬜ | 39 | 4 | 35 | 10% |
| **Total** | | **132** | **35** | **97** | **27%** |

---

## 3. ENTREGABLES CRÍTICOS (Ruta Crítica)

Los siguientes entregables son **bloqueantes** para la siguiente fase:

| Fase | Entregable Crítico | Bloquea |
|------|-------------------|---------|
| 1 | 1.1 (Código PWA) | 2.1 (Página buscador) |
| 1 | 1.2 (Código API) | 2.4 (Endpoint validate), 3.10 (Endpoint analyze) |
| 1 | 1.3 (Encriptación) | 5.7 (Desencriptación), 6.12 (Resumen IA) |
| 2 | 2.2 (Normalización) | 4.2 (Perfil), 4.9 (Endpoints profile) |
| 3 | 3.5 (Modelo ensemble) | 4.2 (Perfil, necesita score), 5.4 (Dashboard, necesita score) |
| 3 | 3.10 (Endpoint analyze) | 4.6 (Recálculo perfil), 6.8 (Alertas automáticas) |
| 4 | 4.2 (Perfil) | 5.12 (Panel admin perfiles), 6.8 (Alertas con profile) |
| 5 | 5.1 (Auth JWT) | 6.13 (Panel admin alertas), 6.14 (API gateway) |
| 5 | 5.7 (Desencriptación) | 6.4 (Export JSON), 6.5 (Export PDF), 6.6 (Export NCMEC) |
| 6 | 6.3 (Email SMTP) | 6.8 (Alertas automáticas), 6.9 (Digest) |
| 6 | 6.11 (API gateway) | 6.15 (Tests gateway) |
| 7 | 7.1 (VPS deploy) | 7.7 (500 reportes reales), 7.8 (Contrato) |
| 7 | 7.4 (OWASP ZAP) | 7.5 (Pentest), 7.8 (Contrato) |

---

## 4. ENTREGABLES DOCUMENTALES (SDD + PM2)

| Documento | Ubicación | Estado | Fase |
|-----------|-----------|--------|------|
| PM2: 00-PORTADA.md | `IDC_PROYECTOS/PROYECTO-005/00-META/` | ✅ | 1 |
| PM2: 01-CASO-NEGOCIOS.md | `IDC_PROYECTOS/PROYECTO-005/01-INICIO/` | ✅ | 1 |
| PM2: DOCUMENTO-EJECUTIVO-NEGOCIO.md | `IDC_PROYECTOS/PROYECTO-005/01-INICIO/` | ✅ | 1 |
| PM2: 02-VISION-PROYECTO.md | `IDC_PROYECTOS/PROYECTO-005/02-PLANIFICACION/` | ✅ | 2 |
| PM2: 03-ALCANCE-DETALLADO.md | `IDC_PROYECTOS/PROYECTO-005/02-PLANIFICACION/` | ✅ | 2 |
| PM2: 04-REQUISITOS-FUNCIONALES.md | `IDC_PROYECTOS/PROYECTO-005/02-PLANIFICACION/` | ✅ | 2 |
| PM2: 05-ARQUITECTURA-TECNOLOGICA.md | `IDC_PROYECTOS/PROYECTO-005/02-PLANIFICACION/` | ✅ | 2 |
| PM2: 06-CRONOGRAMA.md | `IDC_PROYECTOS/PROYECTO-005/03-EJECUCION/` | ✅ | 2 |
| PM2: 07-EQUIPO-Y-ROLES.md | `IDC_PROYECTOS/PROYECTO-005/03-EJECUCION/` | ✅ | 2 |
| PM2: 08-RIESGOS-Y-MITIGACION.md | `IDC_PROYECTOS/PROYECTO-005/03-EJECUCION/` | ✅ | 2 |
| PM2: 09-KPI-Y-METRICAS.md | `IDC_PROYECTOS/PROYECTO-005/03-EJECUCION/` | ✅ | 2 |
| PM2: 10-CRITERIOS-ACEPTACION.md | `IDC_PROYECTOS/PROYECTO-005/04-CIERRE/` | ✅ | 2 |
| PM2: 11-LISTA-ENTREGABLES.md | `IDC_PROYECTOS/PROYECTO-005/05-ENTREGABLES/` | ✅ | 2 |
| SDD: README.md | `docs/` | ✅ | 1 |
| SDD: SPEC-001 | `docs/specs/001-registro-anonimo/` | ✅ | 1 |
| SDD: SPEC-002 | `docs/specs/002-consulta-semaforo/` | ✅ | 2 |
| SDD: SPEC-003 | `docs/specs/003-ia-triage/` | ✅ | 3 |
| SDD: SPEC-004 | `docs/specs/004-clustering-perfil/` | ✅ | 4 |
| SDD: SPEC-005 | `docs/specs/005-panel-admin/` | ✅ | 5 |
| SDD: SPEC-006 | `docs/specs/006-pasarela-institucional/` | ✅ | 6 |
| SDD: ADR-001 | `docs/ADR-001-seguridad.md` | ✅ | 1 |
| SDD: ADR-002 | `docs/ADR-002-pwa.md` | ✅ | 1 |
| SDD: ADR-003 | `docs/ADR-003-ia-triage.md` | ✅ | 3 |
| SDD: ADR-004 | `docs/ADR-004-clustering.md` | ✅ | 4 |
| SDD: ADR-005 | `docs/ADR-005-pasarela.md` | ✅ | 6 |
| SDD: gaps.md | `docs/gaps.md` | ✅ | 2 |
| SDD: estructura-datos.md | `docs/estructura-datos.md` | ✅ | 2 |
| SDD: api-reference.md | `docs/api-reference.md` | ✅ | 2 |
| SDD: model-card.md | `docs/model-card.md` | ⬜ | 3 |
| SDD: evaluation-report.md | `docs/evaluation-report.md` | ⬜ | 3 |
| SDD: fairness-report.md | `docs/fairness-report.md` | ⬜ | 3 |
| SDD: red-teaming-report.md | `docs/red-teaming-report.md` | ⬜ | 3 |
| SDD: runbook.md | `docs/runbook.md` | ⬜ | 7 |
| SDD: security-guide.md | `docs/security-guide.md` | ⬜ | 7 |
| SDD: privacy-guide.md | `docs/privacy-guide.md` | ⬜ | 7 |
| SDD: institution-integration-guide.md | `docs/institution-integration-guide.md` | ⬜ | 6 |
| SDD: CONTRIBUTING.md | `CONTRIBUTING.md` | ⬜ | 7 |
| SDD: CODE_OF_CONDUCT.md | `CODE_OF_CONDUCT.md` | ⬜ | 7 |
| SDD: CHANGELOG.md | `CHANGELOG.md` | ⬜ | 7 |

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Lista de entregables del Semáforo de Confianza*
> *132 entregables totales, 35 completados (27%), 97 pendientes*
