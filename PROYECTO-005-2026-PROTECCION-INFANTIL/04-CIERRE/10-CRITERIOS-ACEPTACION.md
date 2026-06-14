# CRITERIOS DE ACEPTACIÓN — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. DEFINICIÓN DE "DONE" (DEFINITION OF DONE)

Una funcionalidad, módulo, o fase se considera **COMPLETADA** cuando cumple TODOS los criterios siguientes:

### DoD General (aplica a todos los módulos)

| # | Criterio | Verificación | Responsable |
|---|----------|-------------|-------------|
| 1 | Código funcional | La funcionalidad ejecuta sin errores críticos | ODIN |
| 2 | Tests unitarios | Cobertura ≥ 80% de líneas (pytest --cov) | ODIN |
| 3 | Tests de integración | Flujo completo funciona (API + DB + cache) | ODIN |
| 4 | Tests E2E (si aplica) | Playwright: flujo de usuario completo | ODIN |
| 5 | Documentación SDD | Spec, Plan, Tasks actualizados en el repo | ODIN |
| 6 | ADR actualizado | Si implica decisión arquitectónica, ADR documentado | ZEUS |
| 7 | Seguridad validada | OWASP ZAP: 0 vulnerabilidades críticas, 0 altas | ODIN |
| 8 | Performance validada | P95 de tiempo de respuesta dentro de meta | ODIN |
| 9 | Anonimato validado | Auditoría: 0 metadata identificable en requests | ODIN + ZEUS |
| 10 | Revisión de código | PR revisado por ZEUS (o Juan como backup) | ZEUS / Juan |
| 11 | CI/CD verde | GitHub Actions: tests, lint, build pass | GitHub Actions |
| 12 | Deploy en staging | Funcionalidad desplegada en staging y verificada | ODIN |
| 13 | Aprobación ZEUS | ZEUS aprueba que cumple criterios y DoD | ZEUS |
| 14 | Aprobación Jelkin (si crítico) | Jelkin aprueba si implica decisión de negocio | Jelkin |

### DoD por Tipo de Trabajo

| Tipo | DoD Específico |
|------|----------------|
| **Feature (funcionalidad)** | DoD general + demo en Weekly Review + documentación de API |
| **Bug fix** | DoD general + test de regresión + root cause analysis en INCIDENCIAS.md |
| **Refactor** | DoD general + tests de regresión + performance no degradada |
| **Documentación** | Revisión por ZEUS + publicación en GitHub + link en PM2 |
| **Infraestructura** | DoD general + monitoreo operativo + runbook actualizado |
| **Seguridad** | DoD general + auditoría OWASP ZAP + reporte de pentest (si externo) |
| **IA/ML** | DoD general + evaluation report + fairness audit + model card |

---

## 2. CRITERIOS DE ACEPTACIÓN POR FASE

### Fase 1: Registro Anónimo (COMPLETADO)

| # | Criterio | Estado | Evidencia |
|---|----------|--------|-----------|
| 1.1 | Formulario PWA funcional en móvil (320px+) | ✅ | Screenshot de Chrome DevTools responsive |
| 1.2 | POST /api/v1/reportes retorna hash único de 64 caracteres | ✅ | curl test + response JSON |
| 1.3 | Encriptación AES-256-GCM validada: texto encriptado no legible en DB | ✅ | Query directa a PostgreSQL, campo es bytes |
| 1.4 | Rate limiting funciona: 6to reporte retorna 429 | ✅ | curl test con 6 requests, verificar 429 |
| 1.5 | Evidencia multimedia se encripta y almacena | ✅ | Subir imagen, verificar en filesystem (UUID, encriptada) |
| 1.6 | Strip EXIF funciona: imagen sin metadata GPS | ✅ | ExifTool sobre imagen almacenada, verificar no GPS |
| 1.7 | Thumbnail generado (200x200) | ✅ | Verificar archivo thumbnail en filesystem |
| 1.8 | PWA instala desde Chrome/Safari | ✅ | Chrome DevTools → Lighthouse → PWA audit |
| 1.9 | Health check endpoint funciona | ✅ | curl /api/v1/health, retorna 200 + status |
| 1.10 | Tests unitarios + integración ≥ 80% | ✅ | pytest --cov, reporte de cobertura |
| 1.11 | Docker + Docker Compose funciona | ✅ | docker-compose up, todos los servicios healthy |
| 1.12 | OWASP ZAP: 0 vulnerabilidades críticas | ✅ | OWASP ZAP report, 0 critical, 0 high |
| 1.13 | Anonimato validado: 0 metadata identificable en requests | ✅ | Nginx logs: no IP, no user-agent para /api/reportes |
| 1.14 | SPEC-001, PLAN-001, TASKS-001, ADR-001, ADR-002 documentados | ✅ | Archivos en /tmp/semaforo-specs/ |
| 1.15 | Aprobación ZEUS | ✅ | Acta de Weekly Review 2026-06-13 |

### Fase 2: Consulta Semáforo (NUEVO)

| # | Criterio | Verificación | Estado |
|---|----------|-------------|--------|
| 2.1 | Página principal es buscador de confianza | Visual: input prominente, centrado, placeholder claro | ⬜ |
| 2.2 | Input universal: acepta teléfono, email, @usuario, URL, nombre | Test: 5 tipos de input, todos normalizan correctamente | ⬜ |
| 2.3 | Normalización correcta: E.164, lowercase, trim, sin query params | Test: input "+573001234567" → "+573001234567", "  @Usuario  " → "usuario" | ⬜ |
| 2.4 | Hash SHA-256 del identificador normalizado | Test: verificar que se usa hash para query, no identificador en texto plano | ⬜ |
| 2.5 | Semáforo verde: report_count=0, score=null | Test: consulta identificador nuevo → verde | ⬜ |
| 2.6 | Semáforo amarillo: report_count>=1 OR score_max>=0.5 | Test: consulta identificador con 1 reporte leve → amarillo | ⬜ |
| 2.7 | Semáforo rojo: report_count>=3 OR score_max>=0.8 | Test: consulta identificador con 3 reportes o score 0.8 → rojo | ⬜ |
| 2.8 | Semáforo negro: is_network=true | Test: consulta identificador con red organizada → negro | ⬜ |
| 2.9 | Respuesta agregada: nunca expone texto de reporte ni identificador del reportante | Auditoría: response JSON no contiene "description", "reported_by", "ip" | ⬜ |
| 2.10 | Botón "Reportar este identificador" pre-llena formulario | Test: click en botón → navega a /reporte?identifier=hash | ⬜ |
| 2.11 | Rate limiting: 11ra consulta retorna 429 | Test: 11 requests en <1h, verificar 429 | ⬜ |
| 2.12 | Cache Redis: consulta repetida <100ms | Test: primera consulta >200ms, segunda <100ms | ⬜ |
| 2.13 | Landing page + SEO básico | Lighthouse SEO score >= 80 | ⬜ |
| 2.14 | Tests unitarios + integración >= 80% | pytest --cov | ⬜ |
| 2.15 | SPEC-002, PLAN-002, TASKS-002 documentados | Archivos en /tmp/semaforo-specs/ | ⬜ |
| 2.16 | Aprobación ZEUS | Acta de Weekly Review | ⬜ |

### Fase 3: IA Triage (NUEVO)

| # | Criterio | Verificación | Estado |
|---|----------|-------------|--------|
| 3.1 | Dataset 1,500 ejemplos generado y etiquetado | Contar filas en dataset, verificar distribución (30% CAT-01, 20% CAT-02, 25% CAT-03, 15% CAT-04, 10% CAT-05, 5% CAT-06) | ⬜ |
| 3.2 | Preprocesamiento NLP funciona (spaCy) | Test: tokenizar, lematizar, eliminar stopwords, español correcto | ⬜ |
| 3.3 | Feature extraction: TF-IDF (n-grams 1-3) | Test: vectorizar texto, verificar dimensiones | ⬜ |
| 3.4 | Lexicon de grooming implementado | Test: texto con "no le digas a nadie" → detectado como grooming | ⬜ |
| 3.5 | Ensemble LR + RF entrenado y guardado | Test: predict_proba retorna score entre 0.0 y 1.0 | ⬜ |
| 3.6 | AUC-ROC >= 0.80 en test holdout (15%) | Test: calcular AUC-ROC, verificar >= 0.80 | ⬜ |
| 3.7 | Fairness audit: disparidad <10% entre subgrupos | Test: calcular AUC-ROC por subgrupo (dialecto, género), verificar <10% | ⬜ |
| 3.8 | Red-teaming: 0 falsos negativos de alto riesgo | Test: 100 ejemplos de alto riesgo, verificar 0 clasificados como low | ⬜ |
| 3.9 | SHAP explicabilidad: top 5 tokens para scores >0.7 | Test: score >0.7, verificar SHAP retorna 5 tokens con valores | ⬜ |
| 3.10 | Endpoint POST /api/analyze/{report_id} funcional (async) | Test: POST retorna 202 Accepted, procesa en background | ⬜ |
| 3.11 | Integración automática: al recibir reporte, trigger análisis | Test: POST /api/reportes → verificar que se encola tarea de análisis | ⬜ |
| 3.12 | Modelo versionado: cada análisis registra model_version | Test: verificar campo model_version en tabla analyses | ⬜ |
| 3.13 | No almacenar texto desencriptado en logs, disco, ni cache | Auditoría: grep logs por texto desencriptado, verificar 0 matches | ⬜ |
| 3.14 | Resumen de IA de 200 caracteres generado | Test: verificar longitud de resumen, verificar que no es texto original | ⬜ |
| 3.15 | Model card documentado | Leer docs/model-card.md, verificar 10 secciones | ⬜ |
| 3.16 | Evaluation report documentado | Leer docs/evaluation-report.md, verificar métricas, fairness, red-teaming | ⬜ |
| 3.17 | Tests unitarios + integración >= 80% | pytest --cov | ⬜ |
| 3.18 | SPEC-003, PLAN-003, TASKS-003, ADR-003 documentados | Archivos en /tmp/semaforo-specs/ | ⬜ |
| 3.19 | Aprobación ZEUS + Diana (fairness) | Acta de Weekly Review | ⬜ |

### Fase 4: Clustering + Perfil (NUEVO)

| # | Criterio | Verificación | Estado |
|---|----------|-------------|--------|
| 4.1 | Geocodificación: MaxMind GeoLite2 local | Test: IP → ciudad/país, sin coordenadas exactas | ⬜ |
| 4.2 | Consentimiento: checkbox no pre-marcado, puede desactivarse | Test: enviar reporte sin marcar checkbox → no geocodificación | ⬜ |
| 4.3 | IP hasheada y descartada: no en DB ni logs | Auditoría: grep DB y logs por IP, verificar solo hash | ⬜ |
| 4.4 | Modelo Profile: tabla con identifier_hash, report_count, score_average, score_max, cities, countries, is_network, timeline | Test: verificar schema, verificar datos correctos | ⬜ |
| 4.5 | Clustering: mismo ID desde >=3 ciudades → flag is_network | Test: insertar 3 reportes de 3 ciudades, verificar is_network=true | ⬜ |
| 4.6 | Clustering: mismo ID desde >=2 países → flag is_network | Test: insertar 2 reportes de 2 países, verificar is_network=true | ⬜ |
| 4.7 | Clustering: >=5 reportes con score_avg >0.6 → flag is_network | Test: insertar 5 reportes con score promedio 0.7, verificar is_network=true | ⬜ |
| 4.8 | Clustering: >=3 tipos de evidencia → flag is_network | Test: insertar 3 reportes con tipos image, audio, screenshot, verificar is_network=true | ⬜ |
| 4.9 | Recálculo automático: al recibir reporte, profile se actualiza | Test: POST /api/reportes → verificar que profile se actualiza | ⬜ |
| 4.10 | Timeline: agrupación por año-mes, count, score_avg | Test: verificar timeline en respuesta de /api/profile | ⬜ |
| 4.11 | Cache Redis: GET /api/profile <100ms si cache hit | Test: primera consulta >200ms, segunda <100ms | ⬜ |
| 4.12 | Audit trail: ProfileUpdate registra cada cambio | Test: verificar tabla profile_updates, verificar quién, qué, cuándo | ⬜ |
| 4.13 | Tests unitarios + integración >= 80% | pytest --cov | ⬜ |
| 4.14 | SPEC-004, PLAN-004, TASKS-004, ADR-004 documentados | Archivos en /tmp/semaforo-specs/ | ⬜ |
| 4.15 | Aprobación ZEUS + Diana (privacidad) | Acta de Weekly Review | ⬜ |

### Fase 5: Panel Admin (NUEVO)

| # | Criterio | Verificación | Estado |
|---|----------|-------------|--------|
| 5.1 | Auth JWT: login retorna access_token (1h) + refresh_token (24h) | Test: POST /api/admin/auth/login, verificar tokens, verificar expiración | ⬜ |
| 5.2 | 2FA TOTP: setup genera QR, verify funciona | Test: PyOTP generate → verify, login con 2FA | ⬜ |
| 5.3 | Roles: 5 roles funcionan correctamente | Test: viewer solo lectura, reviewer decrypt, supervisor config, admin users, root keys | ⬜ |
| 5.4 | Dashboard: métricas actualizadas en <2s | Test: cargar dashboard, verificar <2s, verificar datos correctos | ⬜ |
| 5.5 | Lista de reportes: filtros + paginación (20 por página) | Test: filtrar por fecha, score, nivel, categoría, estado, ciudad | ⬜ |
| 5.6 | Detalle de reporte: metadata sin desencriptar, botón visible para reviewer+ | Test: viewer accede a detalle, verificar que no hay botón decrypt | ⬜ |
| 5.7 | Desencriptación: razón >=20 chars, límite 10/hr, evidence URL 5 min | Test: desencriptar con razón corta → 400, 11ra desencriptación → 429, URL expirada → 410 | ⬜ |
| 5.8 | Audit trail: cada acción sensible registrada en AuditLog | Test: login, decrypt, status_change, export, verificar en AuditLog | ⬜ |
| 5.9 | Cambio de estado: Nuevo → En revisión → Escalado → Cerrado | Test: PATCH /api/admin/reports/{id}/status, verificar transiciones válidas | ⬜ |
| 5.10 | Export JSON: schema v1.0, datos agregados, sin texto original | Test: export JSON, verificar schema, verificar no contiene "description" | ⬜ |
| 5.11 | Export PDF: branding Innovadataco, portada, resumen, detalle, thumbnails | Test: export PDF, verificar contenido, verificar thumbnails | ⬜ |
| 5.12 | Gestión de usuarios: admin puede crear, editar rol, desactivar | Test: CRUD de users, verificar que no se puede desactivar root | ⬜ |
| 5.13 | Configuración de umbrales: supervisor+ puede editar, valores 0.1-1.0 | Test: PATCH /api/admin/config, verificar validación de rango | ⬜ |
| 5.14 | Tests E2E con Playwright: flujo completo de admin | Test: login → dashboard → lista → detalle → decrypt → logout | ⬜ |
| 5.15 | Tests unitarios + integración >= 80% | pytest --cov | ⬜ |
| 5.16 | SPEC-005, PLAN-005, TASKS-005 documentados | Archivos en /tmp/semaforo-specs/ | ⬜ |
| 5.17 | Aprobación ZEUS (seguridad) | Acta de Weekly Review | ⬜ |

### Fase 6: Pasarela Institucional (NUEVO)

| # | Criterio | Verificación | Estado |
|---|----------|-------------|--------|
| 6.1 | Seed de instituciones: ICBF, Fiscalía, Policía, NCMEC | Test: verificar tabla institutions, verificar datos correctos | ⬜ |
| 6.2 | Alerta severe: enviada en <15 min | Test: insertar reporte severe, cron job, verificar email enviado en <15 min | ⬜ |
| 6.3 | Alerta critical: enviada en <4h | Test: insertar reporte critical, verificar email enviado en <4h | ⬜ |
| 6.4 | Alerta high: enviada en <24h | Test: insertar reporte high, verificar email enviado en <24h | ⬜ |
| 6.5 | Alerta red organizada: enviada inmediatamente, sin importar score | Test: insertar reporte con is_network=true, verificar email enviado inmediatamente | ⬜ |
| 6.6 | Digest diario: enviado a 08:00, incluye reportes del día | Test: cron job, verificar email con conteos por nivel | ⬜ |
| 6.7 | Digest semanal: enviado lunes 08:00, incluye tendencias | Test: cron job, verificar email con tendencias, nuevos perfiles | ⬜ |
| 6.8 | Digest mensual: enviado primer día 08:00, incluye analytics | Test: cron job, verificar email con analytics agregados | ⬜ |
| 6.9 | Formato JSON: schema v1.0, validado | Test: JSON schema validation, verificar estructura | ⬜ |
| 6.10 | Formato PDF: branding, portada, resumen, detalle, thumbnails | Test: verificar PDF generado, verificar contenido | ⬜ |
| 6.11 | Formato NCMEC: XML validado contra CyberTipline v2 | Test: XML validation, verificar schema NCMEC | ⬜ |
| 6.12 | Resumen de IA: 200 caracteres, no texto original | Test: verificar longitud, verificar no es texto original | ⬜ |
| 6.13 | Retry con backoff: 3 intentos, luego failed | Test: simular fallo SMTP, verificar 3 reintentos, luego status=failed | ⬜ |
| 6.14 | API gateway: auth por API key, rate limit 100/hr | Test: POST /api/gateway/v1/reports con X-API-Key, verificar 100 requests, 101→429 | ⬜ |
| 6.15 | Confirmación de recepción: institución puede confirmar | Test: POST /api/gateway/v1/confirm, verificar status actualizado | ⬜ |
| 6.16 | Panel admin: envío manual, generación manual de digest, configuración, historial | Test: UI de admin, verificar funcionalidad | ⬜ |
| 6.17 | Sin datos identificables: nunca texto original, identificador real, coordenadas | Auditoría: response JSON de gateway, verificar no contiene datos sensibles | ⬜ |
| 6.18 | Tests de integración con mock servers | Test: mock SMTP, mock API, verificar flujo completo | ⬜ |
| 6.19 | Tests unitarios + integración >= 80% | pytest --cov | ⬜ |
| 6.20 | SPEC-006, PLAN-006, TASKS-006, ADR-005 documentados | Archivos en /tmp/semaforo-specs/ | ⬜ |
| 6.21 | Aprobación ZEUS + Diana (legal) | Acta de Weekly Review | ⬜ |

### Fase 7: Producción + Piloto (NUEVO)

| # | Criterio | Verificación | Estado |
|---|----------|-------------|--------|
| 7.1 | Deploy en VPS funcional (DigitalOcean) | Test: dominio responde, HTTPS, certificado válido | ⬜ |
| 7.2 | TLS 1.3 activo | Test: SSL Labs scan, score A+ | ⬜ |
| 7.3 | Monitoreo 24/7 operativo | Test: Uptime Kuma, alerta por email/Slack si caída | ⬜ |
| 7.4 | OWASP ZAP: 0 vulnerabilidades críticas | Test: OWASP ZAP scan, reporte 0 critical, 0 high | ⬜ |
| 7.5 | Pentest externo: 0 vulnerabilidades críticas | Test: Reporte de firma de seguridad, 0 critical | ⬜ |
| 7.6 | Piloto con 1 colegio B2B2C completado | Test: Colegio reporta satisfacción, sin bugs críticos | ⬜ |
| 7.7 | 500+ reportes reales procesados | Contar reportes en producción, verificar >= 500 | ⬜ |
| 7.8 | 1 contrato o carta de intención firmada | Documento firmado por ICBF, Fiscalía, o colegio | ⬜ |
| 7.9 | Manual de operación + runbook | Leer docs/runbook.md, verificar procedimientos | ⬜ |
| 7.10 | Marketing de lanzamiento: redes, PR, evento | Verificar publicaciones, asistencia a evento | ⬜ |
| 7.11 | Aprobación Jelkin (CEO) | Acta de aprobación final | ⬜ |

---

## 3. CRITERIOS DE ACEPTACIÓN DE DOCUMENTACIÓN

| # | Documento | Criterio | Verificación | Estado |
|---|-----------|----------|-------------|--------|
| D.1 | 00-PORTADA.md | Nombre "Semáforo de Confianza", código IDC_2026_05, fecha, versión 2.0 | Leer archivo | ✅ |
| D.2 | 01-CASO-NEGOCIOS.md | PWA + B2B2C + freemium, modelo de negocio, competencia, 3 módulos | Leer archivo | ✅ |
| D.3 | DOCUMENTO-EJECUTIVO-NEGOCIO.md | Visión, monetización, legal, competencia, fases, stack | Leer archivo | ✅ |
| D.4 | 02-VISION-PROYECTO.md | Visión técnica y de producto, diagrama de arquitectura, stack, principios | Leer archivo | ✅ |
| D.5 | 03-ALCANCE-DETALLADO.md | 6 módulos, horas, qué incluye, qué NO incluye, criterios por fase | Leer archivo | ✅ |
| D.6 | 04-REQUISITOS-FUNCIONALES.md | RF por módulo (86 requisitos), NFR (20 requisitos), dependencias | Leer archivo | ✅ |
| D.7 | 05-ARQUITECTURA-TECNOLOGICA.md | Diagrama, stack detallado, ADRs, flujo de datos, seguridad, escalabilidad | Leer archivo | ✅ |
| D.8 | 06-CRONOGRAMA.md | 7 fases, fechas, hitos, dependencias, riesgos al cronograma | Leer archivo | ✅ |
| D.9 | 07-EQUIPO-Y-ROLES.md | 6 roles, RACI, comunicación, competencias, contratación | Leer archivo | ✅ |
| D.10 | 08-RIESGOS-Y-MITIGACION.md | 20 riesgos, mapa de riesgos, 4 planes de contingencia | Leer archivo | ✅ |
| D.11 | 09-KPI-Y-METRICAS.md | 4 dimensiones, 50+ métricas, 3 OKRs trimestrales | Leer archivo | ✅ |
| D.12 | 10-CRITERIOS-ACEPTACION.md | DoD general, DoD por tipo, 7 fases con criterios detallados | Leer archivo | ✅ |
| D.13 | 11-LISTA-ENTREGABLES.md | Todos los artefactos por fase, formato, ubicación | Leer archivo | ⬜ |
| D.14 | SPEC-001 a SPEC-006 | Spec, Plan, Tasks por módulo, formato SDD | Verificar en /tmp/semaforo-specs/ | Parcial |
| D.15 | ADR-001 a ADR-005 | Decisión, justificación, consecuencias, estado | Verificar en /tmp/semaforo-specs/ | Parcial |
| D.16 | gaps.md | Gaps resueltos y nuevos, formato tabla | Verificar en /tmp/semaforo-specs/ | ⬜ |
| D.17 | estructura-datos.md | Esquema SQL completo, 10 tablas, índices | Verificar en /tmp/semaforo-specs/ | ⬜ |
| D.18 | api-reference.md | Todos los endpoints, métodos, parámetros, respuestas | Verificar en /tmp/semaforo-specs/ | ⬜ |
| D.19 | README.md | Visión PWA, arquitectura, stack, instalación, uso | Verificar en /tmp/semaforo-specs/ | ✅ |
| D.20 | model-card.md | Objetivo, dataset, métricas, limitaciones, riesgos | Verificar en /tmp/semaforo-specs/ (futuro) | ⬜ |
| D.21 | evaluation-report.md | AUC-ROC, fairness, red-teaming, SHAP | Verificar en /tmp/semaforo-specs/ (futuro) | ⬜ |
| D.22 | runbook.md | Deploy, monitoreo, respuesta a incidentes, rotación de claves | Verificar en /tmp/semaforo-specs/ (futuro) | ⬜ |

---

## 4. DEFINICIÓN DE RECHAZO (REJECTION CRITERIA)

Una funcionalidad, módulo, o fase se **RECHAZA** si cumple ALGUNO de los siguientes:

| # | Criterio de Rechazo | Consecuencia |
|---|---------------------|-------------|
| R.1 | Anonimato comprometido: se detecta metadata identificable (IP, cookies, user-agent, fingerprint) en requests de reporte o consulta | Rechazo inmediato. Bloqueo de deploy. Revisión de seguridad. |
| R.2 | Encriptación comprometida: texto sensible legible en DB, logs, o cache | Rechazo inmediato. Rotación de KEK. Re-encriptación de datos. |
| R.3 | Vulnerabilidad crítica en OWASP ZAP | Rechazo de deploy. Corrección obligatoria antes de aprobación. |
| R.4 | AUC-ROC < 0.70 en IA Triage | Rechazo de modelo. Usar keyword matching como fallback. Re-entrenar. |
| R.5 | Fairness audit falla: disparidad >15% entre subgrupos | Rechazo de modelo. Re-entrenar con pesos por grupo. |
| R.6 | Red-teaming falla: >2 falsos negativos de alto riesgo | Rechazo de modelo. Revisar lexicon, dataset, threshold. |
| R.7 | Brute force exitoso en admin panel | Rechazo de auth. Revisar bcrypt, rate limiting, 2FA. |
| R.8 | Evidence multimedia accesible sin autenticación | Rechazo de seguridad. Revisar URL temporal, auth, encriptación. |
| R.9 | Texto original del reporte expuesto en export institucional | Rechazo de pasarela. Revisar resumen de IA, filtros de export. |
| R.10 | Alerta severe no enviada en <30 min | Rechazo de pasarela. Revisar cron job, SMTP, queue. |

---

## 5. APROBACIONES REQUERIDAS

| Fase | Aprobador | Qué aprueba | Cuándo |
|------|-----------|-------------|--------|
| 1 | ZEUS | Módulo 001 completo, specs, seguridad, anonimato | Weekly Review 2026-06-13 |
| 2 | ZEUS | Módulo 002 completo, specs, consulta funcional | Weekly Review de julio |
| 3 | ZEUS + Diana | Módulo 003 completo, modelo, fairness, red-teaming | Weekly Review de agosto |
| 4 | ZEUS + Diana | Módulo 004 completo, clustering, privacidad, geocodificación | Weekly Review de septiembre |
| 5 | ZEUS | Módulo 005 completo, auth, panel, seguridad | Weekly Review de octubre |
| 6 | ZEUS + Diana | Módulo 006 completo, pasarela, legal, formatos | Weekly Review de noviembre |
| 7 | Jelkin + ZEUS + Diana | Producción, piloto, contrato, seguridad | Monthly Review de diciembre |
| Documentación | ZEUS | Todos los docs PM2, SDD, ADRs | Weekly Review de cada fase |

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Criterios de aceptación del Semáforo de Confianza*
> *7 fases, 100+ criterios de aceptación, 10 criterios de rechazo, 7 aprobadores*
