# REQUISITOS FUNCIONALES — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. MÓDULO 001: REGISTRO ANÓNIMO

| ID | Requisito | Prioridad | Descripción | Criterio de Aceptación |
|----|-----------|-----------|-------------|----------------------|
| RF-001 | Formulario de reporte | Alta | PWA con formulario de 3 campos: identificador, descripción, categoría | Formulario funciona en móvil 320px+, <2 min por reporte |
| RF-002 | Upload de evidencia | Media | Permitir adjuntar imagen, video, audio, captura de pantalla | Máx 5MB imagen, 50MB video, 10MB audio. Strip EXIF. |
| RF-003 | Categorización | Alta | Seleccionar categoría del incidente (6 opciones) | Categoría obligatoria, alimenta modelo IA (Módulo 003) |
| RF-004 | Hash de confirmación | Alta | Generar hash SHA-256 único como prueba de envío | Hash de 64 caracteres, retornado al usuario |
| RF-005 | Anonimato absoluto | Alta | No almacenar IP, user-agent, cookies, localStorage, metadata | Auditoría de headers: 0 metadata identificable |
| RF-006 | Rate limiting | Media | Limitar a 5 reportes/hora/IP | 6to reporte retorna 429, retry_after=3600 |
| RF-007 | Health check | Baja | Endpoint de verificación de estado del sistema | GET /api/health retorna status, versión, timestamp |
| RF-008 | Strip EXIF | Alta | Eliminar metadata GPS y EXIF de imágenes antes de encriptar | Validación: imagen resultante sin EXIF ni GPS |
| RF-009 | Thumbnail | Media | Generar thumbnail 200x200 para imágenes | Thumbnail encriptado, almacenado junto con original |
| RF-010 | PWA | Alta | Funcionar como PWA: manifest, service worker, offline | Instala desde Chrome/Safari, funciona offline para shell |

---

## 2. MÓDULO 002: CONSULTA SEMÁFORO

| ID | Requisito | Prioridad | Descripción | Criterio de Aceptación |
|----|-----------|-----------|-------------|----------------------|
| RF-011 | Buscador universal | Alta | Input que acepta teléfono, email, @usuario, URL, nombre | Detecta tipo automáticamente, normaliza (E.164, lowercase, trim) |
| RF-012 | Normalización | Alta | Normalizar identificador antes de buscar | Teléfono: E.164. Email: lowercase. @usuario: lowercase sin @. URL: sin query params. |
| RF-013 | Hash de búsqueda | Alta | Usar SHA-256 del identificador normalizado para buscar | No almacena identificador en texto plano, solo hash |
| RF-014 | Semáforo verde | Alta | Sin reportes: retornar semáforo verde con mensaje positivo | report_count=0, score=null, message="Sin reportes" |
| RF-015 | Semáforo amarillo | Alta | 1-2 reportes leves o score promedio 0.3-0.5: amarillo | report_count>=1 OR score_max>=0.5, semaforo=amarillo |
| RF-016 | Semáforo rojo | Alta | 3+ reportes o score>=0.8: rojo | report_count>=3 OR score_max>=0.8, semaforo=rojo |
| RF-017 | Semáforo negro | Alta | Red organizada detectada (>=3 ciudades/países): negro | is_network=true, semaforo=negro, alerta máxima |
| RF-018 | Respuesta agregada | Alta | Retornar estadísticas agregadas, nunca detalles individuales | Incluye: conteo, score promedio, categorías, ciudades_count, is_network. NUNCA texto del reporte. |
| RF-019 | Botón reportar | Alta | Desde resultado, botón "Reportar este identificador" | Pre-llena identificador en formulario de Módulo 001 |
| RF-020 | Rate limiting consulta | Media | Limitar a 10 consultas/hora/IP | 11ra consulta retorna 429, retry_after=3600 |
| RF-021 | Cache de consultas | Media | Cachear respuestas frecuentes en Redis (TTL 1h) | Consulta repetida: <100ms, cache hit |
| RF-022 | Compartir resultado | Baja | Botón "Compartir" que genera URL sin identificador | URL compartible: solo hash, no identificador real |

---

## 3. MÓDULO 003: IA TRIAGE

| ID | Requisito | Prioridad | Descripción | Criterio de Aceptación |
|----|-----------|-----------|-------------|----------------------|
| RF-023 | Clasificación automática | Alta | Al recibir reporte, clasificar en categoría (CAT-01 a CAT-06) | Categoría detectada con confidence >= 0.70 |
| RF-024 | Scoring de riesgo | Alta | Calcular score de riesgo (0.0 - 1.0) | Score en 4 decimales, calibrado con Platt scaling |
| RF-025 | Nivel de riesgo | Alta | Asignar nivel: low, medium, high, critical, severe | low: 0-0.3, medium: 0.3-0.5, high: 0.5-0.7, critical: 0.7-0.85, severe: 0.85-1.0 |
| RF-026 | Detección de grooming | Alta | Detectar indicadores de grooming en texto del reporte | Lista de indicadores: secreción, aislamiento, progresión gradual, normalización, minimización de edad |
| RF-027 | Explicabilidad SHAP | Alta | Para scores >0.7, retornar top 5 tokens que contribuyen al score | SHAP values calculados, top 5 tokens identificados |
| RF-028 | Procesamiento async | Alta | Procesar análisis de IA de forma asíncrona (no bloquear reporte) | POST /api/analyze retorna 202 Accepted, procesa en background |
| RF-029 | Modelo versionado | Alta | Cada análisis registra versión del modelo | model_version string, ej: "grooming-v1.0" |
| RF-030 | No almacenar texto desencriptado | Alta | Nunca almacenar texto original en logs, disco, ni cache de IA | Auditoría: texto desencriptado solo en memoria durante inferencia, luego descartado |
| RF-031 | Resumen de IA | Media | Generar resumen de 200 caracteres para exportación institucional | Resumen automático, no texto original, incluido en alertas y digest |
| RF-032 | AUC-ROC >= 0.80 | Alta | Modelo con AUC-ROC >= 0.80 en test holdout | Métrica validada en dataset de test (15% del dataset) |
| RF-033 | Fairness | Alta | Disparidad <10% entre subgrupos (dialecto, género, tipo de evidencia) | Fairness audit reportado, aprobado por ZEUS |
| RF-034 | Red-teaming | Alta | 0 ejemplos de alto riesgo clasificados como low | 100 ejemplos de alto riesgo en test: 0 falsos negativos |
| RF-035 | Dataset sintético | Alta | Generar 1,500 ejemplos etiquetados en español | Distribución: 30% CAT-01, 20% CAT-02, 25% CAT-03, 15% CAT-04, 10% CAT-05, 5% CAT-06 |
| RF-036 | Model card | Alta | Documentar objetivo, dataset, métricas, limitaciones, riesgos | Model card en docs/model-card.md, aprobado por ZEUS |

---

## 4. MÓDULO 004: CLUSTERING + PERFIL

| ID | Requisito | Prioridad | Descripción | Criterio de Aceptación |
|----|-----------|-----------|-------------|----------------------|
| RF-037 | Geocodificación | Alta | Extraer ciudad/país aproximado de IP (si consentimiento) | MaxMind GeoLite2 local, solo ciudad/país, nunca coordenadas exactas |
| RF-038 | Consentimiento explícito | Alta | Usuario debe marcar checkbox "Compartir ciudad aproximada" | Checkbox no pre-marcado, puede desactivarse sin afectar envío de reporte |
| RF-039 | Descarte de IP | Alta | Hashear IP con SHA-256 y descartar inmediatamente | IP nunca almacenada en base de datos ni logs |
| RF-040 | Perfil de identificador | Alta | Generar tabla consolidada por identifier_hash | Incluye: report_count, score_average, score_max, cities, countries, is_network, timeline |
| RF-041 | Clustering geográfico | Alta | Detectar mismo identificador desde >=3 ciudades o >=2 países | Flag is_network=true si criterios cumplidos |
| RF-042 | Detección de red organizada | Alta | Flag automático si 2+ criterios: >=3 ciudades, >=2 países, >=5 reportes con score_avg>0.6, >=3 tipos de evidencia | Algoritmo: criterios >= 2 → is_network = true |
| RF-043 | Timeline | Media | Generar timeline de reportes por mes/año | Agrupación: año-mes, count, score_avg. Sin día exacto. |
| RF-044 | Categorías frecuentes | Media | Detectar categorías más frecuentes por identificador | Lista de categorías con conteo, ordenadas por frecuencia |
| RF-045 | Tipos de evidencia | Media | Detectar tipos de evidencia únicos por identificador | Lista: ["image", "audio", "screenshot"], no contenido |
| RF-046 | Recálculo automático | Alta | Recalcular perfil al recibir nuevo reporte | Trigger: INSERT en reports → UPDATE en profiles + INSERT en profile_updates |
| RF-047 | Cache de perfil | Media | Cachear perfil en Redis (TTL 1h) | GET /api/profile: <100ms si cache hit |
| RF-048 | Audit trail de perfil | Media | Registrar cada cambio en ProfileUpdate | Quién (trigger), qué cambió, cuándo, si activó red organizada |

---

## 5. MÓDULO 005: PANEL ADMIN

| ID | Requisito | Prioridad | Descripción | Criterio de Aceptación |
|----|-----------|-----------|-------------|----------------------|
| RF-049 | Auth JWT | Alta | Login con username/password, retornar access token (1h) + refresh token (24h) | bcrypt 12 rounds, JWT firmado, expiración correcta |
| RF-050 | 2FA TOTP | Media | 2FA opcional con TOTP (Google Authenticator compatible) | Setup por admin root, verify en login, QR code generado |
| RF-051 | Roles | Alta | 5 roles: viewer, reviewer, supervisor, admin, root | viewer: solo lectura. reviewer: + decrypt + status. supervisor: + export + config. admin: + users. root: + keys. |
| RF-052 | Dashboard | Alta | Dashboard con métricas: reportes hoy/semana/mes, semáforo, alertas, networks | Cards actualizadas en tiempo real, <2s de carga |
| RF-053 | Lista de reportes | Alta | Tabla con filtros (fecha, score, nivel, categoría, estado, ciudad) y paginación | 20 por página, filtros combinables, ordenamiento |
| RF-054 | Detalle de reporte | Alta | Página de detalle: metadata, score, nivel, categoría, botón desencriptar | Solo metadata sin desencriptar. Botón visible para reviewer+. |
| RF-055 | Desencriptación bajo demanda | Alta | Desencriptar reporte con razón obligatoria (20 chars), límite 10/hora | Razón registrada en AuditLog. Evidence URL temporal (5 min). |
| RF-056 | Audit trail | Alta | Registrar cada acción sensible: login, logout, view, decrypt, status_change, export | AuditLog con user_id, action, report_id, details, ip, timestamp |
| RF-057 | Cambio de estado | Alta | Cambiar estado de reporte: Nuevo → En revisión → Escalado → Cerrado | Estados válidos, transiciones permitidas, notas opcionales |
| RF-058 | Export JSON | Media | Exportar reportes en JSON estructurado (schema fijo) | Schema v1.0, datos agregados, nunca texto original |
| RF-059 | Export PDF | Media | Exportar reportes en PDF institucional (branding Innovadataco) | Portada, resumen, detalle, evidencia thumbnails, pie legal |
| RF-060 | Gestión de usuarios | Media | Admin puede crear, editar rol, desactivar usuarios | CRUD de users, validación de roles, no desactivar root |
| RF-061 | Configuración de umbrales | Media | Supervisor+ puede configurar umbrales de alerta (severe, critical, high, medium) | Valores entre 0.1 y 1.0, guardados en tabla config |
| RF-062 | Evidence URL temporal | Alta | URL de evidencia expira en 5 minutos, token único | URL expirada retorna 410 Gone |
| RF-063 | Límite de desencriptación | Alta | Max 10 desencriptaciones/hora por admin | 11ra desencriptación retorna 429 |
| RF-064 | No desencriptar viewer | Alta | Viewer no puede desencriptar | 403 Forbidden si viewer intenta decrypt |

---

## 6. MÓDULO 006: PASARELA INSTITUCIONAL

| ID | Requisito | Prioridad | Descripción | Criterio de Aceptación |
|----|-----------|-----------|-------------|----------------------|
| RF-065 | Seed de instituciones | Alta | ICBF, Fiscalía, Policía, NCMEC pre-registradas | Código único, contacto, alert config por defecto |
| RF-066 | API key por institución | Alta | Generar API key única por institución (bcrypt) | API key de 64 chars, rotada cada 3 meses, almacenada hasheada |
| RF-067 | Alerta automática severe | Alta | Enviar alerta inmediata (<15 min) si score >= 0.85 | Cron job cada 5 min, envía email + registra en Alert |
| RF-068 | Alerta automática critical | Alta | Enviar alerta en <4h si score >= 0.70 | Cron job cada 1h, batch de reportes critical pendientes |
| RF-069 | Alerta automática high | Alta | Enviar alerta en <24h si score >= 0.50 | Cron job cada 6h, batch de reportes high pendientes |
| RF-070 | Alerta red organizada | Alta | Enviar alerta inmediata si is_network=true (sin importar score) | Cron job cada 5 min, prioridad máxima, todos los destinatarios |
| RF-071 | Digest diario | Media | Enviar resumen diario a instituciones (08:00) | Cron: 08:00, incluye reportes del día por nivel |
| RF-072 | Digest semanal | Media | Enviar resumen semanal a instituciones (lunes 08:00) | Cron: lunes 08:00, incluye tendencias, nuevos perfiles, alertas |
| RF-073 | Digest mensual | Media | Enviar resumen mensual a instituciones (primer día 08:00) | Cron: primer día 08:00, incluye analytics agregados |
| RF-074 | Formato JSON | Alta | JSON estructurado (schema v1.0) para exportación | Schema validado, datos agregados, nunca texto original |
| RF-075 | Formato PDF | Alta | PDF institucional con branding Innovadataco | Portada, resumen, detalle, evidencia thumbnails, pie legal |
| RF-076 | Formato NCMEC | Media | Conforme a CyberTipline API v2 | XML validado contra schema NCMEC |
| RF-077 | Resumen de IA | Alta | Generar resumen de 200 caracteres para exportación | Resumen automático, no texto original, incluido en todos los formatos |
| RF-078 | Retry con backoff | Alta | Reintentar envío 3 veces con backoff exponencial | Intento 1: inmediato. Intento 2: 5 min. Intento 3: 15 min. Luego: failed. |
| RF-079 | API gateway | Alta | API REST para instituciones con API key (X-API-Key) | Auth por API key, rate limit 100/hr, TLS 1.3 obligatorio |
| RF-080 | Confirmación de recepción | Alta | Institución puede confirmar recepción de alerta | POST /api/gateway/v1/confirm con report_hash y status |
| RF-081 | Rate limiting gateway | Alta | 100 requests/hora por institución | 101ra request retorna 429 |
| RF-082 | Sin datos identificables | Alta | Nunca retornar texto original del reporte, identificador real del reportante, ni coordenadas | Validación: response JSON solo contiene agregados y resúmenes |
| RF-083 | Panel admin alertas | Media | Enviar alerta manual desde panel admin | Selección de reporte, destinatarios, formato, notas |
| RF-084 | Panel admin digest | Media | Generar digest manual desde panel admin | Selección de período, fecha, institución, formato |
| RF-085 | Panel admin config | Media | Configurar umbrales y destinatarios por institución | Supervisor+ puede editar alert_config por institución |
| RF-086 | Panel admin historial | Baja | Ver historial de alertas enviadas | Tabla con filtros: fecha, institución, estado, formato |

---

## 7. REQUISITOS NO FUNCIONALES (NFR)

| ID | Requisito | Categoría | Criterio | Prioridad | Módulo |
|----|-----------|-----------|----------|-----------|--------|
| RNF-001 | Encriptación AES-256-GCM | Seguridad | Todos los datos sensibles encriptados | Alta | Todos |
| RNF-002 | Headers OWASP | Seguridad | HSTS, CSP, X-Frame-Options, X-Content-Type-Options, Referrer-Policy | Alta | Todos |
| RNF-003 | Tests >= 80% | Calidad | pytest + vitest, cobertura de líneas | Alta | Todos |
| RNF-004 | Tiempo consulta <500ms | Performance | 95 percentile | Alta | 002 |
| RNF-005 | Tiempo reporte <2s | Performance | 95 percentile | Alta | 001 |
| RNF-006 | Tiempo inferencia IA <500ms | Performance | 95 percentile | Alta | 003 |
| RNF-007 | Sin cookies | Privacidad | Zero cookies, zero localStorage (reporte) | Alta | 001, 002 |
| RNF-008 | Sin IP en logs | Privacidad | Nginx access_log off para /api/reportes | Alta | 001 |
| RNF-009 | Anonimato absoluto | Privacidad | No user-agent, no fingerprint, no metadata | Alta | 001, 002 |
| RNF-010 | AUC-ROC >= 0.80 | Calidad IA | Validación en test holdout | Alta | 003 |
| RNF-011 | Explicabilidad SHAP | Transparencia | Para scores >0.7 | Alta | 003 |
| RNF-012 | Modelo versionado | MLOps | Reproducible, model card | Alta | 003 |
| RNF-013 | Sin datos en logs IA | Privacidad | Texto desencriptado nunca en logs ni disco | Alta | 003 |
| RNF-014 | Geocodificación sin identificar | Privacidad | Solo ciudad/país, nunca coordenadas | Alta | 004 |
| RNF-015 | Perfil encriptado | Seguridad | Datos del perfil en reposo encriptados | Alta | 004 |
| RNF-016 | Audit trail admin | Seguridad | Quién vio qué y cuándo | Alta | 005 |
| RNF-017 | Alta disponibilidad | Performance | 99.5% uptime en producción | Media | Infra |
| RNF-018 | Escalabilidad horizontal | Arquitectura | Docker + stateless + load balancer ready | Media | Infra |
| RNF-019 | Multi-idioma i18n | Internacionalización | Estructura preparada para español, portugués, inglés | Baja | Todos |
| RNF-020 | WCAG 2.1 AA | Accesibilidad | Compatible con lectores de pantalla | Media | Todos |

---

## 8. DEPENDENCIAS ENTRE REQUISITOS

```
RF-001 (Crear reporte)
  ├── RF-002 (Evidencia) [opcional]
  ├── RF-003 (Categoría) [obligatorio]
  ├── RF-004 (Hash) [automático]
  ├── RF-005 (Anonimato) [obligatorio]
  ├── RF-006 (Rate limit) [obligatorio]
  └── RF-008 (Strip EXIF) [obligatorio si evidencia imagen]

RF-023 (Clasificación IA)
  └── RF-035 (Dataset) [obligatorio]
  └── RF-001 (Crear reporte) [obligatorio]

RF-037 (Geocodificación)
  └── RF-038 (Consentimiento) [obligatorio]
  └── RF-001 (Crear reporte) [obligatorio]

RF-040 (Perfil identificador)
  └── RF-023 (Clasificación IA) [obligatorio, necesita score]
  └── RF-037 (Geocodificación) [opcional, mejora perfil]

RF-049 (Auth JWT)
  └── RF-051 (Roles) [obligatorio]
  └── RF-052 (Dashboard) [obligatorio]
  └── RF-053 (Lista reportes) [obligatorio]

RF-055 (Desencriptar)
  └── RF-049 (Auth JWT) [obligatorio]
  └── RF-056 (Audit trail) [obligatorio]
  └── RF-064 (No viewer) [obligatorio]

RF-065 (Seed instituciones)
  └── RF-067 (Alerta severe) [obligatorio]
  └── RF-079 (API gateway) [obligatorio]
```

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Requisitos funcionales por módulo*
