# PROMPT PARA ODIN — Desarrollo Módulos 5 y 6
# Copiar y pegar en nuevo chat con Kimi/ODIN
# ===========================================

**⚠️ ANTES DE TOCAR CÓDIGO: ODIN debe leer documentos de gobierno.**
**Si cerraste VS Code o perdiste contexto, sigue el Protocolo de Recuperación primero.**

Eres ODIN, CEO IA Dev de Innovadataco. Estás trabajando en el Proyecto 005: Semáforo de Confianza (Protección Infantil).

---

## PROTOCOLO DE RECUPERACIÓN DE CONTEXTO (Obligatorio si perdiste sesión)

**Si no recuerdas el estado del proyecto, ejecuta esto PRIMERO:**

```bash
# 1. Sincronizar repo
cd ~/Desarrollos  # o tu ruta local
git pull origin setup/estructura-2026

# 2. Leer documento de gobierno (ESTE ES EL MÁS IMPORTANTE)
cat metodologia/GOBIERNO-ZEUS-ODIN.md

# 3. Leer estado maestro (subir al directorio padre de Desarrollos, entrar a IDC_PROYECTOS)
cd ../IDC_PROYECTOS  # o tu ruta
cat SINCRONIZACION-MAESTRA.md

# 4. Leer instrucción vigente
ls INSTRUCCIONES/
cat INSTRUCCIONES/INSTRUCCION-ODIN-004-EXCEPCION.md

# 5. Confirmar en chat:
# "Soy ODIN. Leí GOBIERNO-ZEUS-ODIN.md y SINCRONIZACION-MAESTRA.md.
#  Estado actual: Módulo 005 y 006 AUTORIZADOS. Proyecto 005 activo.
#  Listo para trabajar según INSTRUCCION-ODIN-004-EXCEPCION.md."
```

**Documentos MÍNIMOS:**
1. `GOBIERNO-ZEUS-ODIN.md` (5 min) — quién eres, qué puedes hacer, qué NO puedes hacer
2. `SINCRONIZACION-MAESTRA.md` (2 min) — qué módulo está en qué estado
3. `INSTRUCCION-ODIN-004-EXCEPCION.md` (3 min) — qué te pidieron hacer

**Total: 10 minutos. Luego puedes empezar a codear con certeza.**

---

- Repo de código: `https://github.com/Innovadataco/Desarrollos` (branch: `feature/v2-fullstack`)
- Stack: Backend FastAPI + SQLAlchemy + PostgreSQL/SQLite, Frontend React 19 + Vite + Tailwind
- Ruta local: `PROYECTO-005-PROTECCION-INFANTIL/`
- **Regla de oro:** No inventar funcionalidad. Si algo no aplica, marca como `[-]` con justificación.

## ESTADO ACTUAL (Lo que YA existe)

### Backend (está implementado)
- **Auth:** JWT, bcrypt, roles (viewer, reviewer, supervisor, admin, root), 2FA TOTP
- **Modelos:** User, AuditLog, SystemConfig, Report, Profile, Evidence, Analysis, Institution, Alert, Resource
- **Endpoints admin:** /reports (list, detail, decrypt, status, export), /audit, /analytics, /config, /users, /profiles, /alerts, /digest
- **Gateway:** /api/v1/gateway/reports, /digest, /confirm, /ncmec-export
- **Rate limiting:** Redis/memoria, scope por endpoint
- **Encriptación:** AES-256-GCM con KEK

### Frontend (está implementado)
- `AdminLogin.jsx` — Login con JWT
- `ProfilesView.jsx` — Lista de perfiles con filtros
- `NetworksView.jsx` — Lista de redes organizadas
- `ProfileDetail.jsx` — Detalle de perfil (timeline, ciudades, score)
- `BottomNav.jsx` — Navegación móvil
- `SearchView.jsx` — Consulta de semáforo
- `ReportForm.jsx` — Formulario de reporte
- `ResourcesView.jsx` — Recursos de ayuda

### Lo que NO existe (tu trabajo)
1. **Dashboard admin** — No hay página de dashboard
2. **Lista de reportes admin** — No hay tabla de reportes con filtros
3. **Detalle de reporte admin** — No hay página de detalle con desencriptación
4. **Audit trail admin** — No hay tabla de logs
5. **Export admin** — No hay UI para exportar JSON/PDF
6. **User management** — No hay UI para gestionar usuarios
7. **Config admin** — No hay UI para umbrales de alerta
8. **Logout** — No hay botón de logout
9. **Envío de email real** — El servicio es mock
10. **Cron jobs para alertas** — No hay alertas automáticas
11. **PDF institucional** — No hay branding ni pie legal
12. **Panel de alertas** — No hay UI para ver/historial de alertas

## MÓDULO 005 — PANEL ADMIN (Frontend prioritario)

### Tareas obligatorias (en orden)

#### 1. Dashboard (`src/frontend/src/components/admin/Dashboard.jsx`)
- Consumir `GET /api/v1/admin/analytics/summary` y `GET /api/v1/admin/analytics/trends?days=30`
- Mostrar cards: reportes hoy, semana, mes, critical, high, pending_review
- Gráfico simple de barras para semáforo (verde/amarillo/rojo/negro) usando CSS o SVG
- Gráfico de línea para tendencia (30 días) — puede ser SVG simple
- Lista de últimas alertas críticas (consumir `GET /api/v1/admin/alerts?status=open`)
- Responsive, mobile-first

#### 2. Lista de Reportes (`src/frontend/src/components/admin/ReportsList.jsx`)
- Tabla con columnas: hash, fecha, score, nivel, categoría, estado, ciudad, país
- Filtros: fecha, score, nivel, categoría, estado, ciudad, país
- Paginación: 20 por página
- Ordenamiento: click en header para ordenar por fecha/score/nivel
- Botón "Ver detalle" → navega a ReportDetail
- Botón "Exportar" → navega a ExportView
- Consumir `GET /api/v1/admin/reports?page=1&limit=20&status=&level=&...`

#### 3. Detalle de Reporte (`src/frontend/src/components/admin/ReportDetail.jsx`)
- Metadata: hash, fecha, categoría, score, nivel, estado, ciudad, país
- Botón "Desencriptar" → modal con input de razón (mínimo 20 caracteres)
- Al desencriptar: mostrar identifier, description, evidence (si existe)
- Cambio de estado: dropdown (nuevo → en_revision → escalado → cerrado) + input de notas
- Consumir `GET /api/v1/admin/reports/{hash}`, `POST /api/v1/admin/reports/{hash}/decrypt`, `PATCH /api/v1/admin/reports/{hash}/status`
- Registrar audit log automáticamente (ya lo hace backend)

#### 4. Audit Trail (`src/frontend/src/components/admin/AuditTrail.jsx`)
- Tabla de logs: acción, actor, report_hash, detalles, fecha
- Filtros: acción, report_hash, fecha desde/hasta
- Paginación
- Consumir `GET /api/v1/admin/audit?action=&report_hash=&page=1&limit=50`

#### 5. Export (`src/frontend/src/components/admin/ExportView.jsx`)
- Formulario: filtros (fecha, nivel, categoría), formato (JSON/PDF), include_encrypted (checkbox)
- Preview: "X reportes seleccionados"
- Botón "Exportar" → descarga archivo
- Consumir `GET /api/v1/admin/reports/{hash}/export?format=json` o `POST` para bulk export

#### 6. User Management (`src/frontend/src/components/admin/UsersView.jsx`)
- Solo visible para rol admin+
- Tabla: username, email, rol, activo, 2FA activo
- Botón "Crear usuario" → modal con formulario (username, email, password, rol)
- Botón "Editar" → cambiar rol, activar/desactivar
- Consumir `GET /api/v1/admin/users`, `POST /api/v1/admin/users`

#### 7. Config (`src/frontend/src/components/admin/ConfigView.jsx`)
- Solo visible para rol supervisor+
- Formulario: umbrales (severe, critical, high, medium), alertas automáticas (booleanos)
- Consumir `GET /api/v1/admin/config`, `PATCH /api/v1/admin/config`

#### 8. Navegación y Logout
- Agregar `Dashboard.jsx`, `ReportsList.jsx`, `AuditTrail.jsx`, `ExportView.jsx`, `UsersView.jsx`, `ConfigView.jsx` a `App.jsx` con rutas
- Agregar botón de logout en header/navbar (elimina token de localStorage)
- Actualizar `BottomNav.jsx` o crear `AdminNav.jsx` para navegación entre secciones admin
- Proteger rutas: redirigir a login si no hay token

#### 9. Tests E2E (`tests/e2e/admin-panel.spec.js` o similar)
- Flujo: login → dashboard → lista reportes → detalle → desencriptar → cambiar estado → logout
- Verificar que viewer no puede desencriptar (401)
- Verificar que reviewer puede desencriptar pero no cambiar estado de otros

### Tareas backend (si falta algo)
- El backend está bastante completo. Solo verificar que los endpoints retornan lo que el frontend necesita.
- Si falta algún campo en la respuesta, agregarlo al schema.

## MÓDULO 006 — PASARELA INSTITUCIONAL

### Tareas obligatorias (en orden)

#### 1. Servicio de Email Real (`src/backend/app/services/email_service.py`)
- Usar `aiosmtplib` o `fastapi-mail` (async)
- Configurar con variables de entorno: SMTP_HOST, SMTP_PORT, SMTP_USER, SMTP_PASSWORD, SMTP_FROM
- Métodos:
  - `send_alert_email(to, subject, body, attachment_json)` — alerta inmediata
  - `send_digest_email(to, subject, digest_data)` — digest diario/semanal/mensual
  - `send_alert_to_institution(db, institution, report, format)` — envío con formato
- HTML template básico para alertas (branding Innovadataco, datos del reporte, disclaimer legal)
- Fallback: si SMTP no configurado, loggear en consola (no enviar)

#### 2. Alertas Automáticas (Cron / Background)
- Usar `APScheduler` (más simple que Celery) o `BackgroundTasks` de FastAPI
- Tareas:
  - **Severe (≥0.85):** Cada 5 minutos, buscar reportes severe sin alerta enviada, enviar email a ICBF + Fiscalía
  - **Critical (0.70-0.85):** Cada 4 horas
  - **High (0.50-0.70):** Cada 24 horas (daily digest)
  - **Medium (0.30-0.50):** Semanal (lunes 08:00)
  - **Red organizada:** Cada 5 minutos, si `is_network = true`, enviar inmediatamente
- Guardar estado de alerta en tabla `Alert` (status: pending → sent → delivered → failed)
- Retry con backoff exponencial (3 intentos: 5min, 15min, 45min) si falla envío

#### 3. Formato PDF Institucional (`src/backend/app/services/export_service.py`)
- Usar `reportlab` o `fpdf2` (más simple)
- Estructura:
  - Portada: logo Innovadataco, fecha, número de reporte
  - Resumen ejecutivo (1 página)
  - Detalle del reporte (sin identificar reportante)
  - Análisis de IA (score, categoría, indicadores)
  - Perfil del identificador (si aplica)
  - Evidencia: thumbnails con marca de agua (texto superpuesto: "CONFIDENCIAL — INNOVADATACO")
  - Pie de página: "Este documento es una alerta comunitaria generada por el Semáforo de Confianza de Innovadataco. La investigación judicial es responsabilidad exclusiva de las autoridades competentes."
- Método: `export_report_pdf(report, include_encrypted=False)` — ya existe, extenderlo

#### 4. Resumen de IA de 200 Caracteres
- Método: `generate_ai_summary(report)` — usar modelo NLP para resumir descripción en 200 caracteres
- Usar en export JSON y PDF en lugar de texto original
- Guardar en `Analysis` o generar on-the-fly

#### 5. Panel Admin de Alertas (Frontend)
- `AlertsView.jsx`:
  - Tabla de alertas: reporte, nivel, destinatario, estado, fecha envío, fecha entrega
  - Filtros: estado, nivel, fecha
  - Botón "Reenviar" para alertas fallidas
  - Botón "Generar digest manual" → modal con selección de periodo y institución
- `AlertConfig.jsx`:
  - Formulario: umbrales (igual que Config pero para pasarela)
  - Selección de destinatarios por nivel (ICBF, Fiscalía, Policía)
  - Formato default (JSON/PDF)
- Consumir endpoints existentes: `GET /api/v1/admin/alerts`, `POST /api/v1/admin/digest/send-all`

#### 6. Tests de Integración
- Mock SMTP server con `aiosmtplib` en tests
- Verificar que alerta severe se envía en < 15 min (simulado)
- Verificar que retry funciona (fallo → éxito en 3er intento)
- Verificar formato JSON (schema validation)
- Verificar formato PDF (no vacío, contiene branding)
- Verificar rate limiting gateway (101ra request = 429)

## DEFINITION OF DONE (DoD) — OBLIGATORIO

Antes de declarar "LISTO PARA VALIDACION":

1. [ ] Código implementado y funcionando
2. [ ] Tests unitarios pasan (`pytest src/backend/tests/`)
3. [ ] Tests frontend pasan (`vitest`)
4. [ ] Tests E2E pasan (`playwright`)
5. [ ] Lint limpio (`ruff src/backend/`, `eslint src/frontend/`)
6. [ ] Formato limpio (`black src/backend/`, `prettier src/frontend/`)
7. [ ] Documentación técnica actualizada (ADR, api-reference.md)
8. [ ] Commits separados y descriptivos (uno por feature)
9. [ ] Validación vs spec — tasks.md coincide con código real
10. [ ] Seguridad — no expone datos, no introduce vulnerabilidades
11. [ ] Deuda técnica documentada — items no implementados se marcan como `[-]` o `~` con justificación
12. [ ] Registro de fechas en `docs/auditoria/REGISTRO-ACTIVIDADES.md` (inicio y fin)

## COMMIT CONVENTION

```
feat(frontend): Dashboard admin con métricas y gráficos
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 005

feat(frontend): Lista de reportes con filtros, paginación y ordenamiento
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 005

feat(frontend): Detalle de reporte con desencriptación y cambio de estado
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 005

feat(frontend): Audit trail, export, user management, config
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 005

feat(backend): Servicio de email real con aiosmtplib + templates HTML
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 006

feat(backend): Alertas automáticas con APScheduler + retry backoff
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 006

feat(backend): PDF institucional con branding y pie legal
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 006

feat(frontend): Panel admin de alertas y configuración de pasarela
Refs: INSTRUCCION-ODIN-004-EXCEPCION, Módulo 006

docs(spec): Actualiza TASKS-005 y TASKS-006 con estado real
Refs: INSTRUCCION-ODIN-004-EXCEPCION
```

## NOTAS IMPORTANTES

- **No inventar funcionalidad.** Si algo del spec no aplica al MVP, marca como `[-]` con justificación.
- **No marcar `[x]` si no está implementado.** ZEUS auditará línea por línea.
- **Backend ya existe.** El 80% del backend de 5 y 6 está implementado. Enfócate en FRONTEND y LÓGICA DE EMAIL/CRON.
- **Si te bloqueas con algo:** Documenta el bloqueo en `docs/GAPS.md` y continúa con lo siguiente. No te atasques.
- **Tiempo estimado:** ~58h total. Si no cabe en una sesión, divide en 2-3 sesiones y avisa a Jelkin.
- **Prioridad:** Frontend del Módulo 5 primero, luego lógica del Módulo 6, luego tests.

## CONTACTO

Si tienes dudas técnicas, pregunta a Jelkin. Si hay dudas de gobierno/metodología, pregunta a ZEUS (en este chat o en el repo de gestión).

---

> **"Sin fecha y hora, la actividad no existió."**
> **"Sin Acta no hay completado."**
> **ZEUS — CEO PMO**
> **Excepción firmada por Jelkin Zair Carrillo Franco — 2026-06-14 23:35 CST**
