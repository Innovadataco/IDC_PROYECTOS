# INSTRUCCIÓN-ODIN-002 — Módulo 002: Consulta Semáforo
**Proyecto:** PROYECTO-005: Semáforo de Confianza (Protección Infantil)  
**Módulo:** 002 — Consulta Semáforo  
**Spec:** SPEC-002  
**Fecha emisión:** 2026-06-14  
**Firma CEO:** Jelkin Zair Carrillo Franco  
**Auditor:** ZEUS (CEO PMO)  
**Ejecutor:** ODIN (CEO IA Dev)  
**Estado:** ✅ APROBADO — Firma del CEO registrada

---

## 1. CONTEXTO

El Módulo 001 (Registro Anónimo) está **VALIDADO**. Ahora procedemos al Módulo 002: Consulta Semáforo.

Este módulo es el **corazón del producto**: un buscador universal donde cualquier persona puede consultar si un número de teléfono, cuenta de redes sociales, email o URL ha sido reportado como riesgo para menores.

**Reglas de oro:**
- ODIN no puede declarar "completado"
- ODIN declara "listo para validación" cuando termina
- ZEUS audita y decide: VALIDADO o RECHAZADO
- Sin Acta de Validación, no hay merge, no hay siguiente módulo

---

## 2. TIMESTAMPS (Obligatorio)

**ODIN registra:**
```
Inicio: 2026-06-14 HH:MM CST (Shanghai) / HH:MM (Bogotá)
Fin: 2026-06-14 HH:MM CST (Shanghai) / HH:MM (Bogotá)
```

**ZEUS registra:**
```
Inicio auditoría: 2026-06-14 HH:MM CST (Shanghai) / HH:MM (Bogotá)
Fin auditoría: 2026-06-14 HH:MM CST (Shanghai) / HH:MM (Bogotá)
```

**Sin fecha/hora, la actividad no cuenta.**

---

## 3. ESPECIFICACIONES TÉCNICAS

### 3.1 SPEC-002 — Consulta Semáforo de Confianza

**Spec completo:** `specs/002-consulta-semaforo/spec.md`

**Resumen ejecutivo:**
- Endpoint: `GET /api/validate/{identifier}`
- Buscador universal: teléfono, email, @usuario, URL
- Semáforo de 4 colores: 🟢 VERDE / 🟡 AMARILLO / 🔴 ROJO / ⚫ NEGRO
- Algoritmo basado en: report_count, score_max, cities_count, is_network
- Rate limiting: 10 consultas/hora
- No expone información del reportante
- Modelo freemium: 3 consultas/día gratis, $2.99/mes premium

### 3.2 TASKS-002 — Tareas pendientes

**Tasks completos:** `specs/002-consulta-semaforo/tasks.md`

**Frontend (10 tasks):**
- TF-002.1: Crear página principal como buscador
- TF-002.2: Input universal con placeholder dinámico
- TF-002.3: Detectar tipo de identificador
- TF-002.4: Cards de semáforo (4 colores, animación)
- TF-002.5: Detalle de resultado (conteos, categorías, timeline)
- TF-002.6: Botón "Reportar" → pre-llena Módulo 001
- TF-002.7: Botón "Compartir resultado"
- TF-002.8: "Alertarme si cambia" (Premium)
- TF-002.9: PWA página principal como consulta (routing)
- TF-002.10: Tests E2E con Playwright

**Backend (9 tasks):**
- TB-002.1: Endpoint GET /api/validate/{identifier}
- TB-002.2: Normalización de identificadores (E.164, email, @, URL)
- TB-002.3: Hash SHA-256 para búsqueda
- TB-002.4: Query agregada por identifier_hash
- TB-002.5: Algoritmo de semáforo (verde/amarillo/rojo/negro)
- TB-002.6: Rate limiting 10/hr para consulta
- TB-002.7: Respuesta que NO expone datos del reportante
- TB-002.8: Tests unitarios (pytest, ≥ 80% cobertura)
- TB-002.9: Tests de integración (TestClient, fixtures)

**Infraestructura (3 tasks):**
- TI-002.1: Índice en identifier_hash (PostgreSQL)
- TI-002.2: Cache de consultas frecuentes (Redis, TTL 1h)
- TI-002.3: Nginx cache de respuestas 200 (5 min)

### 3.3 CRITERIOS DE ACEPTACIÓN (DoD)

- [ ] Endpoint /api/validate/{identifier} funcional y documentado
- [ ] Normalización de identificadores correcta
- [ ] Semáforo calcula correctamente según reglas
- [ ] No expone información identificable del reportante
- [ ] Rate limiting: 11ra consulta retorna 429
- [ ] Página de consulta funciona en móvil (320px+)
- [ ] Resultado muestra semáforo visual (colores claros)
- [ ] Botón "Reportar" lleva a formulario de Módulo 001
- [ ] Tests unitarios ≥ 80% cobertura
- [ ] Tests de integración con TestClient
- [ ] ADR-002 aprobado (PWA vs App Store)

---

## 4. CHECKLIST DE INICIO DE SESIÓN (Obligatorio)

ODIN debe ejecutar ESTO antes de tocar código:

```bash
# 1. PULL SINCRONIZACIÓN
cd /Users/innovadataco/Documents/GitHub/Desarrollos/PROYECTO-005-PROTECCION-INFANTIL
git pull origin setup/estructura-2026

# 2. RECORDAR REGLAS DE GOBIERNO
# - Leer metodologia/AGENTS.md §10 (Modo Autónomo restringido)
# - Recordar: NO puedo declarar "completado", solo "listo para validación"
# - Recordar: NO puedo tocar IDC_PROYECTOS (repo de gestión)

# 3. VERIFICAR ESTADO ACT-001
# - Leer docs/auditoria/REGISTRO-ACTIVIDADES.md (ACT-001 = VALIDADO)
# - Verificar que Módulo 001 está en producción/mergeado

# 4. CAMBIAR DE CONTEXTO MENTAL
# - Módulo 001 = Registro Anónimo (DONE)
# - Módulo 002 = Consulta Semáforo (NUEVO)
# - No mezclar código de módulos

# 5. INICIAR REGISTRO DE FECHAS
# - Escribir INICIO en esta instrucción
# - Formato: Inicio: 2026-06-14 HH:MM CST (Shanghai) / HH:MM (Bogotá)

# 6. REVISAR SPEC Y TASKS
# - Leer specs/002-consulta-semaforo/spec.md (completo)
# - Leer specs/002-consulta-semaforo/tasks.md (completo)
# - Leer specs/002-consulta-semaforo/plan.md (completo)
```

---

## 5. REGLAS DE IMPLEMENTACIÓN

### 5.1 Commits (obligatorio)

Cada task = commit individual. Formato:
```
feat(PROYECTO-005): Módulo 002 - [TF/TB/TI-002.X] descripción breve

Refs: TASKS-002, SPEC-002
```

Ejemplos:
```
feat(PROYECTO-005): Módulo 002 - [TF-002.1] crea página principal como buscador

Refs: TASKS-002, SPEC-002

feat(PROYECTO-005): Módulo 002 - [TB-002.1] implementa endpoint GET /api/validate

Refs: TASKS-002, SPEC-002

feat(PROYECTO-005): Módulo 002 - [TB-002.5] implementa algoritmo de semáforo

Refs: TASKS-002, SPEC-002
```

### 5.2 Tests (obligatorio)

- Cada backend task = tests unitarios (pytest)
- Cada frontend task = tests con Vitest/React Testing Library
- Coverage ≥ 80% para backend
- Tests de integración con TestClient
- NO declarar "listo" sin tests

### 5.3 Seguridad (obligatorio)

- NO exponer datos del reportante
- NO exponer contenido del reporte
- Hash SHA-256 del identificador (nunca en texto plano)
- Rate limiting: 10 consultas/hora por IP
- Cache de respuestas: NO cachear si hay datos sensibles

### 5.4 UX/UI (obligatorio)

- Página principal = buscador (no reporte)
- Mobile-first: 320px+
- Semáforo visual: colores claros, accesibles
- Animación suave en cambio de color
- Loading states claros
- Error states con mensajes amigables

---

## 6. FLUJO DE TRABAJO

```
┌─────────────────┐
│  INICIO SESIÓN  │ ← Checklist de inicio (obligatorio)
│   (ODIN registra│
│    timestamps)  │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  IMPLEMENTACIÓN │ ← Task por task, commit por commit
│   (ODIN ejecuta) │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  TESTS LOCALES  │ ← pytest, vitest, cobertura ≥ 80%
│   (ODIN ejecuta) │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  DECLARACIÓN    │ ← ODIN escribe: "LISTO PARA VALIDACIÓN"
│   (ODIN escribe) │ ← NO escribe: "COMPLETADO"
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  AUDITORÍA ZEUS │ ← ZEUS audita código real
│   (ZEUS decide) │ ← VALIDADO o RECHAZADO
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  ACTA GENERADA  │ ← ACTA-VALIDACION o ACTA-CORRECCION
│   (ZEUS genera) │ ← Sincronizada en IDC_PROYECTOS
└─────────────────┘
```

---

## 7. DECISIÓN DEL CEO

**Jelkin Zair Carrillo Franco decide:**

☑️ **APROBADO** — ODIN procede con implementación del Módulo 002
☐ **RECHAZADO** — Se requiere ajuste en spec/tasks antes de implementar
☐ **DIFERIDO** — Módulo 002 para más adelante, continuar con otro

**Firma:** Jelkin Zair Carrillo Franco (vía Telegram, mensaje "si, debemos derile a odin que implemente los 6 specs !")  
**Fecha/Hora:** 2026-06-14 05:48 CST (Shanghai) / 04:48 (Bogotá)  
**Nota:** El CEO mencionó "los 6 specs", lo que implica implementar los 6 módulos restantes (002-006). ZEUS interpreta esto como: aprobar Módulo 002 y preparar instrucciones para 003-006 en secuencia.

---

## 8. HISTORIAL

| Fecha | Evento | Actor |
|-------|--------|-------|
| 2026-06-14 | Módulo 001 VALIDADO | ZEUS |
| 2026-06-14 | Emisión de INSTRUCCION-ODIN-002.md | ZEUS |
| 2026-06-14 | PENDIENTE: Firma del CEO | Jelkin Carrillo |
| 2026-06-14 | PENDIENTE: Inicio de implementación | ODIN |

---

> **"El Semáforo de Confianza es el corazón del producto. Sin consulta, no hay valor."**
> **ZEUS — CEO PMO**
