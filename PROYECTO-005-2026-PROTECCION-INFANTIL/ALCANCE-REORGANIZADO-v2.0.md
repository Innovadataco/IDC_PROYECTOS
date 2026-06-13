# ALCANCE REORGANIZADO — PROYECTO-005: Protección Infantil Comunitaria

**Fecha:** 13 de junio de 2026  
**Versión:** 2.0 — Reorganización por visión del CEO  
**Autor:** ZEUS PMO  
**Responsable:** Jelkin Zair Carrillo Franco (CEO)  
**Estado:** Borrador — pendiente aprobación del CEO

---

## 📋 CONTEXTO DE LA REORGANIZACIÓN

El CEO ha redefinido la visión del producto. El alcance original (4 módulos) se amplía y reestructura para incluir capacidades críticas nuevas: evidencia multimedia, validación de contactos, clustering geográfico y perfil del agresor.

**Cambios principales:**
- El reporte ahora incluye **evidencia multimedia** (fotos, videos, capturas de pantalla, audios)
- El sistema permite **validar si un número/cuenta ya tiene reportes previos**
- El sistema detecta **patrones geográficos** (mismo número reportado desde múltiples ciudades/países = red organizada)
- El sistema genera un **perfil del presunto agresor** con historial completo

---

## 🎯 VISION DEL PRODUCTO (ACTUALIZADA)

> **"Una plataforma segura donde cualquier persona puede reportar un riesgo para un niño, subir evidencia multimedia, y el sistema usa IA para identificar patrones, validar reportes previos, y generar perfiles de agresores para las autoridades."**

---

## 🏗️ ARQUITECTURA DE MÓDULOS REORGANIZADA

```
┌─────────────────────────────────────────────────────────────────────────┐
│                           USUARIO (Web/Móvil)                            │
│              Sin login, sin cookies, sin IP guardada                     │
└───────────────────────────┬─────────────────────────────────────────────┘
                            │ HTTPS
                            ▼
┌─────────────────────────────────────────────────────────────────────────┐
│  FRONTEND — React 19 + Vite + Tailwind CSS (PWA)                       │
│  • Formulario de reporte (texto + evidencia multimedia)                │
│  • Validador de contacto (buscar si existe reporte previo)               │
│  • Panel de confirmación (hash de envío)                                │
└───────────────────────────┬─────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────────────┐
│  BACKEND — FastAPI + SQLAlchemy + PostgreSQL/SQLite                     │
│  ┌─────────────────────────────────────────────────────────────────────┐ │
│  │ MÓDULO 001: Registro Anónimo (COMPLETADO)                         │ │
│  │ • POST /api/reportes                                              │ │
│  │ • Encriptación AES-256-GCM                                        │ │
│  │ • Rate limiting 5/hr/IP                                           │ │
│  │ • Health check                                                    │ │
│  └─────────────────────────────────────────────────────────────────────┘ │
│  ┌─────────────────────────────────────────────────────────────────────┐ │
│  │ MÓDULO 002: IA Scoring de Riesgo (EN DESARROLLO)                  │ │
│  │ • GET /api/analyze/{report_id}                                    │ │
│  │ • Score 0-1 (low/medium/high/critical)                            │ │
│  │ • Explicabilidad SHAP                                             │ │
│  │ • Dataset sintético + Logistic Regression                        │ │
│  └─────────────────────────────────────────────────────────────────────┘ │
│  ┌─────────────────────────────────────────────────────────────────────┐ │
│  │ MÓDULO 003: Validación de Contactos (NUEVO)                       │ │
│  │ • GET /api/validate/{identifier}                                  │ │
│  │ • Busca reportes previos por número/cuenta                        │ │
│  │ • Retorna: existe, cantidad reportes, score promedio, fechas      │ │
│  │ • Anonimato: solo retorna estadísticas agregadas                  │ │
│  └─────────────────────────────────────────────────────────────────────┘ │
│  ┌─────────────────────────────────────────────────────────────────────┐ │
│  │ MÓDULO 004: Clustering Geográfico y Perfil de Agresor (NUEVO)     │ │
│  │ • GET /api/profile/{identifier}                                   │ │
│  │ • Clustering: mismo ID desde múltiples ciudades/países            │ │
│  │ • Genera tabla "outbound" del agresor                             │ │
│  │ • Alerta de red organizada si ≥3 ciudades/países                  │ │
│  └─────────────────────────────────────────────────────────────────────┘ │
│  ┌─────────────────────────────────────────────────────────────────────┐ │
│  │ MÓDULO 005: Panel de Administración (NUEVO)                       │ │
│  │ • Auth seguro (admin)                                             │ │
│  │ • Dashboard de reportes con filtros                               │ │
│  │ • Desencriptación bajo demanda                                    │ │
│  │ • Cambio de estado (nuevo, en revisión, escalado, cerrado)        │ │
│  │ • Export de datos para autoridades                                │ │
│  └─────────────────────────────────────────────────────────────────────┘ │
│  ┌─────────────────────────────────────────────────────────────────────┐ │
│  │ MÓDULO 006: Notificaciones a Autoridades (NUEVO)                  │ │
│  │ • Integración ICBF / Fiscalía / Policía                            │ │
│  │ • Alertas automáticas por severidad (critical)                    │ │
│  │ • Resúmenes periódicos (diario/semanal)                            │ │
│  │ • Formato de exportación estándar (JSON/PDF)                       │ │
│  └─────────────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────────────┐
│  INFRAESTRUCTURA                                                       │
│  • PostgreSQL (datos encriptados)                                       │
│  • Redis (rate limiting + cache)                                        │
│  • Docker + Docker Compose                                              │
│  • GitHub Actions CI/CD                                                 │
│  • VPS Cloud (DigitalOcean / Hetzner / AWS Lightsail)                  │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## 📅 FASES Y TIMELINE REORGANIZADO

### FASE 1: FUNDACIÓN (Completada — Junio 2026)
**Módulo 001: Registro Anónimo** ✅

| Entregable | Estado | Fecha |
|------------|--------|-------|
| Formulario web anónimo | ✅ Completado | Junio 2026 |
| API REST POST /api/reportes | ✅ Completado | Junio 2026 |
| Encriptación AES-256-GCM | ✅ Completado | Junio 2026 |
| Rate limiting | ✅ Completado | Junio 2026 |
| Tests + cobertura ≥80% | ✅ Completado | Junio 2026 |
| SDD: spec, plan, tasks, ADR | ✅ Completado | Junio 2026 |

**Horas invertidas:** 40h (ODIN)

---

### FASE 2: INTELIGENCIA ARTIFICIAL (Julio 2026)
**Módulo 002: IA Scoring de Riesgo** 🔄 En desarrollo

| Entregable | Estado | Estimación |
|------------|--------|------------|
| Dataset sintético 1.500 ejemplos | ⬜ Pendiente | 4h |
| Modelo TF-IDF + Logistic Regression | ⬜ Pendiente | 6h |
| Endpoint /api/analyze/{report_id} | ⬜ Pendiente | 4h |
| Explicabilidad SHAP | ⬜ Pendiente | 4h |
| Red-teaming + fairness audit | ⬜ Pendiente | 8h |
| Tests + cobertura ≥80% | ⬜ Pendiente | 4h |
| Model card + evaluation report | ⬜ Pendiente | 3h |
| ADR-IA-001 aprobado | ⬜ Pendiente | 1h |

**Horas estimadas:** 36h (ODIN)
**Dependencia:** FASE 1 completada

---

### FASE 3: VALIDACIÓN Y CLUSTERING (Agosto 2026)
**Módulos 003 + 004: Validación de Contactos + Clustering Geográfico** ⬜ NUEVO

| Entregable | Descripción | Estimación |
|------------|-------------|------------|
| **MÓDULO 003: Validación** | | |
| Endpoint /api/validate/{identifier} | Busca reportes previos por número/cuenta | 6h |
| Respuesta anónima agregada | Retorna: existe, cantidad, score promedio, fechas | 4h |
| Tests de integración | TestClient + pytest | 4h |
| **MÓDULO 004: Clustering** | | |
| Geocodificación de reportes | Extraer ciudad/país de metadata (si consiente) | 6h |
| Algoritmo de clustering | Detectar mismo ID desde múltiples ubicaciones | 8h |
| Generación de perfil de agresor | Tabla consolidada: reportes, scores, ubicaciones, evidencia | 8h |
| Alerta de red organizada | Si ≥3 ciudades/países → flag "POSIBLE RED" | 4h |
| Endpoint /api/profile/{identifier} | Retorna perfil completo del agresor | 6h |
| Tests + cobertura | pytest + dataset de prueba | 6h |
| ADR-003: Arquitectura de clustering | Decisión técnica: geocodificación, privacidad | 2h |

**Horas estimadas:** 54h (ODIN)
**Dependencia:** FASE 2 completada (necesita scoring para perfil)

---

### FASE 4: PANEL DE ADMINISTRACIÓN (Septiembre 2026)
**Módulo 005: Panel de Admin** ⬜ NUEVO

| Entregable | Descripción | Estimación |
|------------|-------------|------------|
| Auth seguro (admin) | JWT + 2FA opcional | 8h |
| Dashboard de reportes | Tabla con filtros (fecha, score, nivel, estado) | 10h |
| Desencriptación bajo demanda | Botón "Ver contenido" con auditoría | 6h |
| Cambio de estado | Nuevo → En revisión → Escalado → Cerrado | 4h |
| Visualización de score + explicación | UI para ver SHAP y nivel de riesgo | 6h |
| Export de datos | JSON/PDF para autoridades | 6h |
| Tests E2E | Playwright: flujo completo admin | 8h |
| ADR-004: Arquitectura de auth | Decisión técnica: JWT vs sessions | 2h |

**Horas estimadas:** 50h (ODIN)
**Dependencia:** FASE 3 completada (necesita scoring y clustering)

---

### FASE 5: NOTIFICACIONES A AUTORIDADES (Octubre 2026)
**Módulo 006: Notificaciones** ⬜ NUEVO

| Entregable | Descripción | Estimación |
|------------|-------------|------------|
| Integración ICBF | API o email de alertas | 8h |
| Integración Fiscalía | Formato de alertas estructuradas | 8h |
| Alertas automáticas por severidad | Critical → inmediato / High → 4h / Medium → 24h | 6h |
| Resúmenes periódicos | Daily digest + weekly summary | 6h |
| Formato de exportación estándar | JSON con schema fijo + PDF con branding | 8h |
| Configuración de umbrales | Admin define qué score genera alerta | 4h |
| Tests de integración | Mock servers + pytest | 6h |
| ADR-005: Integración con autoridades | Decisión técnica: API vs email vs portal | 2h |

**Horas estimadas:** 48h (ODIN)
**Dependencia:** FASE 4 completada (necesita panel de admin para configuración)

---

### FASE 6: PRODUCCIÓN Y PILOTO (Noviembre-Diciembre 2026)

| Entregable | Descripción | Estimación |
|------------|-------------|------------|
| Deploy en VPS/cloud | DigitalOcean / Hetzner / AWS Lightsail | 8h |
| TLS 1.3 + dominio propio | Certificados Let's Encrypt | 4h |
| Monitoreo y alerting | Uptime + logs + métricas | 6h |
| Auditoría de seguridad externa | OWASP ZAP + pentest | 16h (externo) |
| Capacitación a autoridades | Demo + manual de uso | 8h |
| Piloto con 1 municipio | Prueba real con autoridad local | 20h (operativo) |
| Iteración post-piloto | Ajustes UX + feedback | 16h |

**Horas estimadas:** 78h (mix ODIN + operativo)
**Dependencia:** FASE 5 completada

---

## 📊 RESUMEN DE HORAS Y ESFUERZO

| Fase | Módulo | Horas | Estado |
|------|--------|-------|--------|
| 1 | Registro Anónimo | 40h | ✅ Completado |
| 2 | IA Scoring | 36h | 🔄 En desarrollo |
| 3 | Validación + Clustering | 54h | ⬜ Nuevo |
| 4 | Panel Admin | 50h | ⬜ Nuevo |
| 5 | Notificaciones | 48h | ⬜ Nuevo |
| 6 | Producción + Piloto | 78h | ⬜ Nuevo |
| **TOTAL** | | **306h** | ~19 semanas (1 FTE) |

**Equipo requerido:**
- 1 desarrollador (ODIN) full-time
- 1 reviewer de seguridad (ZEUS) part-time
- 1 asesor legal (Diana) consultivo
- 1 marketing/posicionamiento (Zaira) consultivo

---

## 🎨 REQUISITOS FUNCIONALES POR MÓDULO (NUEVOS)

### MÓDULO 003: Validación de Contactos

| ID | Requisito | Prioridad | Descripción |
|----|-----------|-----------|-------------|
| RF-013 | Validar número/cuenta | Alta | Cualquier usuario puede ingresar un identificador y ver si existe reporte previo |
| RF-014 | Respuesta agregada | Alta | No retorna detalles del reporte, solo estadísticas: cantidad, score promedio, fechas |
| RF-015 | Protección de privacidad | Alta | No expone información identificable del reportante ni del contenido |
| RF-016 | Rate limiting en validación | Media | 10 validaciones/hora/IP para evitar scraping |

### MÓDULO 004: Clustering Geográfico y Perfil de Agresor

| ID | Requisito | Prioridad | Descripción |
|----|-----------|-----------|-------------|
| RF-017 | Geocodificación de reportes | Alta | Extraer ciudad/país de la IP o metadata (si el usuario consiente) |
| RF-018 | Clustering de mismo ID | Alta | Detectar si el mismo identificador ha sido reportado desde ≥3 ubicaciones diferentes |
| RF-019 | Perfil del agresor | Alta | Generar tabla consolidada: reportes, scores, ubicaciones, tipos de evidencia, timeline |
| RF-020 | Alerta de red organizada | Alta | Flag automático si ≥3 ciudades/países reportan el mismo ID |
| RF-021 | Análisis de patrones | Media | Detectar modus operandi (textos similares, horarios, tipos de contacto) |
| RF-022 | Export de perfil | Media | Generar PDF/JSON del perfil para autoridades |

### MÓDULO 005: Panel de Administración

| ID | Requisito | Prioridad | Descripción |
|----|-----------|-----------|-------------|
| RF-023 | Auth seguro | Alta | JWT + contraseña fuerte + 2FA opcional |
| RF-024 | Dashboard de reportes | Alta | Ver todos los reportes con filtros y paginación |
| RF-025 | Desencriptación bajo demanda | Alta | Ver contenido encriptado con auditoría de quién lo vio y cuándo |
| RF-026 | Cambio de estado | Alta | Nuevo → En revisión → Escalado → Cerrado |
| RF-027 | Visualización de score | Alta | Ver score, nivel, explicación SHAP en UI |
| RF-028 | Export para autoridades | Media | Generar JSON/PDF con datos estructurados |

### MÓDULO 006: Notificaciones a Autoridades

| ID | Requisito | Prioridad | Descripción |
|----|-----------|-----------|-------------|
| RF-029 | Alerta inmediata (critical) | Alta | Notificar a ICBF/Fiscalía en <1h si score ≥0.85 |
| RF-030 | Alerta diferida (high/medium) | Alta | Notificar en 4h/24h según nivel |
| RF-031 | Resumen diario | Media | Email con todos los reportes del día agregados |
| RF-032 | Resumen semanal | Media | Email con tendencias, nuevos perfiles, alertas |
| RF-033 | Formato estándar | Alta | Schema JSON fijo para integración con sistemas de autoridades |
| RF-034 | Configuración de umbrales | Media | Admin define qué score/nivel genera alerta y a quién |

---

## 🛡️ REQUISITOS NO FUNCIONALES ACTUALIZADOS

| ID | Requisito | Categoría | Criterio | Prioridad |
|----|-----------|-----------|----------|-----------|
| RNF-001 | Encriptación AES-256-GCM | Seguridad | Datos sensibles encriptados | Alta |
| RNF-002 | Headers OWASP | Seguridad | HSTS, CSP, X-Frame, etc. | Alta |
| RNF-003 | Cobertura de tests ≥80% | Calidad | pytest + vitest | Alta |
| RNF-004 | Tiempo de respuesta <500ms | Performance | 95 percentile | Media |
| RNF-005 | Sin cookies de tracking | Privacidad | No cookies ni localStorage | Alta |
| RNF-006 | Latencia IA <500ms | Performance | 95 percentile | Alta |
| RNF-007 | AUC-ROC ≥0.80 | Calidad IA | Validación holdout | Alta |
| RNF-008 | Explicabilidad SHAP | Transparencia | Para score >0.7 | Alta |
| RNF-009 | Modelo versionado | MLOps | Reproducible | Alta |
| RNF-010 | Sin datos identificables en logs IA | Privacidad | No texto original | Alta |
| **RNF-011** | **Geocodificación sin identificar** | **Privacidad** | **No guardar IP, solo ciudad/país aproximado** | **Alta** |
| **RNF-012** | **Perfil de agresor encriptado** | **Seguridad** | **Datos del perfil encriptados en reposo** | **Alta** |
| **RNF-013** | **Audit trail de acceso admin** | **Seguridad** | **Quién vio qué y cuándo** | **Alta** |
| **RNF-014** | **Alta disponibilidad** | **Performance** | **99.5% uptime en producción** | **Media** |

---

## 📝 ESQUEMA DE DATOS ACTUALIZADO

### Entidad `Report` (existente, ampliada)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | UUID | PK |
| report_hash | String(64), unique | Hash de confirmación |
| reported_identifier | LargeBinary | Identificador encriptado (número, cuenta, email) |
| description | LargeBinary | Descripción encriptada |
| evidence_type | String(20), nullable | `text`, `image`, `video`, `audio`, `screenshot` |
| evidence_content | LargeBinary, nullable | Evidencia encriptada |
| evidence_media_url | String(255), nullable | URL segura a archivo multimedia (encriptado) |
| **city** | **String(100), nullable** | **Ciudad aproximada (no exacta)** |
| **country** | **String(100), nullable** | **País** |
| **consent_location** | **Boolean** | **Usuario consiente compartir ubicación aproximada** |
| reported_at | DateTime | Fecha creación |
| updated_at | DateTime | Fecha actualización |

### Entidad `Analysis` (nueva, Módulo 002)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | UUID | PK |
| report_id | UUID | FK → reports.id |
| score | Float | 0.0 - 1.0 |
| level | String(20) | low / medium / high / critical |
| model_version | String(50) | Versión del modelo |
| explanation | JSON | SHAP values o coefficients |
| created_at | DateTime | Timestamp |

### Entidad `Profile` (nueva, Módulo 004)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | UUID | PK |
| identifier_hash | String(64), unique | Hash del identificador (no el valor real) |
| report_count | Integer | Cantidad de reportes |
| score_average | Float | Promedio de scores |
| score_max | Float | Score máximo alcanzado |
| cities | JSON | Lista de ciudades únicas |
| countries | JSON | Lista de países únicos |
| is_network | Boolean | True si ≥3 ciudades/países |
| evidence_types | JSON | Tipos de evidencia recibidos |
| first_reported_at | DateTime | Primer reporte |
| last_reported_at | DateTime | Último reporte |
| updated_at | DateTime | Actualización |

### Entidad `AuditLog` (nueva, Módulo 005)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | UUID | PK |
| admin_id | String(100) | Quién accedió |
| action | String(50) | Ver reporte, descifrar, cambiar estado, exportar |
| report_id | UUID | FK (nullable) |
| timestamp | DateTime | Cuándo |
| ip_address | String(45) | IP del admin (audit trail) |

---

## 🎯 CRITERIOS DE ACEPTACIÓN GLOBALES (POR FASE)

### FASE 2: IA Scoring
- [ ] Dataset sintético 1.500 ejemplos etiquetados
- [ ] Modelo con AUC-ROC ≥0.80 en test
- [ ] Endpoint /api/analyze/{report_id} funcional
- [ ] Explicabilidad SHAP integrada
- [ ] Red-teaming: 0 ejemplos de alto riesgo clasificados como low
- [ ] Fairness: disparidad <10% entre subgrupos
- [ ] Cobertura backend ≥80%
- [ ] ADR-IA-001 aprobado

### FASE 3: Validación + Clustering
- [ ] Endpoint /api/validate/{identifier} retorna estadísticas agregadas
- [ ] No expone datos individuales del reportante
- [ ] Clustering detecta correctamente mismo ID desde ≥3 ubicaciones
- [ ] Perfil de agresor genera tabla completa y precisa
- [ ] Alerta de red organizada funciona automáticamente
- [ ] Tests de integración pasan
- [ ] ADR-003 aprobado

### FASE 4: Panel Admin
- [ ] Auth seguro con JWT + 2FA opcional
- [ ] Dashboard muestra todos los reportes con filtros
- [ ] Desencriptación bajo demanda con audit trail
- [ ] Cambio de estado funciona (Nuevo → En revisión → Escalado → Cerrado)
- [ ] Export JSON/PDF genera archivos correctos
- [ ] Tests E2E pasan (Playwright)
- [ ] ADR-004 aprobado

### FASE 5: Notificaciones
- [ ] Alerta critical llega a ICBF/Fiscalía en <1h
- [ ] Alerta high llega en <4h
- [ ] Resumen diario y semanal funcionan
- [ ] Formato JSON estándar validado
- [ ] Configuración de umbrales funciona desde panel admin
- [ ] Tests de integración con mocks pasan
- [ ] ADR-005 aprobado

### FASE 6: Producción
- [ ] Deploy en VPS/cloud funcional
- [ ] TLS 1.3 activo
- [ ] Monitoreo 24/7 operativo
- [ ] Auditoría OWASP ZAP: 0 vulnerabilidades críticas
- [ ] Piloto con 1 autoridad completado
- [ ] 500+ reportes reales procesados
- [ ] 1 contrato o carta de intención firmada

---

## 📁 ESQUEMA DE ARCHIVOS SDD/PM2 REORGANIZADO

```
PROYECTO-005-PROTECCION-INFANTIL/
├── specs/
│   ├── 001-registro-anonimo/
│   │   ├── spec.md          ✅ Completado
│   │   ├── plan.md          ✅ Completado
│   │   ├── tasks.md         ✅ Completado
│   │   └── ADR-001-seguridad.md  ✅ Completado
│   ├── 002-ia-scoring/
│   │   ├── spec.md          🔄 Borrador
│   │   ├── plan.md          🔄 Borrador
│   │   ├── tasks.md         🔄 Borrador
│   │   └── ADR-IA-001.md    🔄 Borrador
│   ├── 003-validacion-contactos/
│   │   ├── spec.md          ⬜ NUEVO — PENDIENTE
│   │   ├── plan.md          ⬜ NUEVO — PENDIENTE
│   │   ├── tasks.md         ⬜ NUEVO — PENDIENTE
│   │   └── ADR-003.md       ⬜ NUEVO — PENDIENTE
│   ├── 004-clustering-perfil/
│   │   ├── spec.md          ⬜ NUEVO — PENDIENTE
│   │   ├── plan.md          ⬜ NUEVO — PENDIENTE
│   │   ├── tasks.md         ⬜ NUEVO — PENDIENTE
│   │   └── ADR-004.md       ⬜ NUEVO — PENDIENTE
│   ├── 005-panel-admin/
│   │   ├── spec.md          ⬜ NUEVO — PENDIENTE
│   │   ├── plan.md          ⬜ NUEVO — PENDIENTE
│   │   ├── tasks.md         ⬜ NUEVO — PENDIENTE
│   │   └── ADR-005.md       ⬜ NUEVO — PENDIENTE
│   └── 006-notificaciones-autoridades/
│       ├── spec.md          ⬜ NUEVO — PENDIENTE
│       ├── plan.md          ⬜ NUEVO — PENDIENTE
│       ├── tasks.md         ⬜ NUEVO — PENDIENTE
│       └── ADR-006.md       ⬜ NUEVO — PENDIENTE
├── docs/
│   ├── gaps.md              ✅ Completado
│   ├── model-card.md        ⬜ Pendiente (Módulo 002)
│   ├── evaluation.md        ⬜ Pendiente (Módulo 002)
│   ├── red-teaming.md       ⬜ Pendiente (Módulo 002)
│   ├── fairness.md          ⬜ Pendiente (Módulo 002)
│   └── api-reference.md     ⬜ NUEVO — PENDIENTE
└── README.md                ✅ Completado
```

---

## ⚠️ RIESGOS Y MITIGACIÓN (ACTUALIZADOS)

| ID | Riesgo | Probabilidad | Impacto | Mitigación | Responsable |
|----|--------|-------------|---------|------------|-------------|
| R-001 | Clave de encriptación comprometida | Baja | Catastrófico | Rotación manual, re-encriptación, HSM futuro | ODIN + ZEUS |
| R-002 | Modelo IA sesgado o injusto | Media | Alto | Fairness audit, dataset balanceado, red-teaming | ODIN + ZEUS |
| R-003 | Abuso del formulario (spam) | Media | Medio | Rate limiting + scoring de spam + revisión humana | ODIN + ZEUS |
| R-004 | Fuga de datos del perfil de agresor | Baja | Catastrófico | Encriptación del perfil, acceso solo admin, audit trail | ODIN + ZEUS |
| R-005 | Geocodificación imprecisa | Alta | Medio | Usar solo ciudad/país aproximado, no coordenadas exactas | ODIN |
| R-006 | Dependencia de ODIN como único dev | Media | Alto | Documentación completa (SDD), Juan como backup | ZEUS |
| R-007 | Autoridades no integran el sistema | Alta | Alto | Open source + piloto gratuito + case study | Jelkin (CEO) |
| R-008 | Responsabilidad legal si alerta no se procesa | Media | Catastrófico | Contrato limita responsabilidad, seguro, cláusula de canal tecnológico | Diana (Legal) |
| R-009 | Escalabilidad del clustering | Baja | Medio | Índices en identifier_hash, caché en Redis, queries optimizadas | ODIN |
| R-010 | Costo de infraestructura en producción | Media | Medio | VPS económico ($50-200/mes), auto-scaling manual, monitoreo de costos | ZEUS + Jelkin |

---

## 🎯 DECISIONES PENDIENTES DEL CEO (ACTUALIZADAS)

| # | Decisión | Opciones | Tu respuesta |
|---|----------|----------|--------------|
| **1** | ¿Aprobamos la reorganización de 4 a 6 módulos? | Sí / No (mantener 4 originales) | **¿?** |
| **2** | ¿Aprobamos el Módulo 002 (IA Scoring) para desarrollo inmediato? | Sí / No / Prioridad baja | **¿?** |
| **3** | ¿Aprobamos los Módulos 003+004 (Validación + Clustering) como nuevos? | Sí / No / Después de Módulo 002 | **¿?** |
| **4** | ¿Aprobamos el Panel de Admin (Módulo 005) con auth JWT + 2FA? | Sí / No / Versión simple sin 2FA | **¿?** |
| **5** | ¿Aprobamos Notificaciones a ICBF/Fiscalía (Módulo 006)? | Sí / No / Solo email, no API | **¿?** |
| **6** | ¿Proveedor de infraestructura? | DigitalOcean / Hetzner / AWS Lightsail / Otro | **¿?** |
| **7** | ¿Modelo de negocio prioritario? | SaaS B2G / Operador / Open Source + servicios / Híbrido | **¿?** |
| **8** | ¿Innovadataco asume responsabilidad legal de operación? | Sí, con seguro / No, solo tecnología / A definir con Diana | **¿?** |

---

> **Documento preparado por ZEUS PMO para decisión del CEO.**
>
> **Estado:** Borrador v2.0 — Listo para revisión y aprobación.
>
> **Próximo paso:** Jelkin revisa, responde las 8 decisiones pendientes, y ZEUS/ODIN proceden según lo indicado.
>
> *ZEUS online. La empresa está operando.* ⚡
