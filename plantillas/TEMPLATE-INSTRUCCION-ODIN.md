# TEMPLATE — INSTRUCCIÓN-ODIN-XXX.md
**Proyecto:** [PROYECTO-XXX]  
**Módulo:** [XXX] — [Nombre del Módulo]  
**Spec:** SPEC-XXX  
**Fecha emisión:** [YYYY-MM-DD]  
**Firma CEO:** [Nombre del CEO]  
**Auditor:** ZEUS (CEO PMO)  
**Ejecutor:** ODIN (CEO IA Dev)  
**Estado:** ⏳ PENDIENTE FIRMA / ✅ APROBADO

---

## 1. CONTEXTO

[Módulo anterior] está **VALIDADO**. Ahora procedemos al Módulo [XXX]: [Nombre].

**Reglas de oro:**
- ODIN no puede declarar "completado"
- ODIN declara "listo para validación" cuando termina
- ZEUS audita y decide: VALIDADO o RECHAZADO
- Sin Acta de Validación, no hay merge, no hay siguiente módulo

---

## 2. TIMESTAMPS (Obligatorio)

**ODIN registra:**
```
Inicio: YYYY-MM-DD HH:MM CST (Shanghai) / HH:MM (Bogotá)
Fin: YYYY-MM-DD HH:MM CST (Shanghai) / HH:MM (Bogotá)
```

**ZEUS registra:**
```
Inicio auditoría: YYYY-MM-DD HH:MM CST (Shanghai) / HH:MM (Bogotá)
Fin auditoría: YYYY-MM-DD HH:MM CST (Shanghai) / HH:MM (Bogotá)
```

**Sin fecha/hora, la actividad no cuenta.**

---

## 3. REGLA CRÍTICA: ALCANCE COMPLETO (Obligatorio)

> **⚠️ REGLA INAMOVIBLE: ODIN debe implementar TODAS las tasks del módulo antes de declarar "listo para validación".**
>
> **NO se valida por task individual. Se valida por módulo completo.**
>
> **Ejemplo: Si este módulo tiene N tasks, ODIN debe completar las N tasks antes de declarar "listo".**

### 3.1 Verificación obligatoria antes de declarar "listo"

**ODIN debe verificar:**
- [ ] Todos los frontend tasks implementados (TF-XXX.X)
- [ ] Todos los backend tasks implementados (TB-XXX.X)
- [ ] Todos los infra tasks implementados (TI-XXX.X)
- [ ] Todos los tests pasan (pytest, vitest)
- [ ] Cobertura ≥ 80% (backend)
- [ ] DoD (Definition of Done) completo
- [ ] Timestamp de FIN registrado

**Si falta ALGUNA task → NO declarar "listo". Continuar implementando.**

### 3.2 Consecuencia de declarar incompleto

**Si ODIN declara "listo para validación" con tasks faltantes:**
- ZEUS audita y detecta incompletitud
- ZEUS genera ACTA-CORRECCION (no ACTA-VALIDACION)
- Se pierde tiempo en rechazo y re-implementación
- Se retrasa el siguiente módulo

**Regla de oro:**
> **"Mejor tardar en completar todo, que ser rechazado por incompleto."**

---

## 4. ESPECIFICACIONES TÉCNICAS

### 4.1 SPEC-XXX — [Nombre del Spec]

**Spec completo:** `specs/[XXX]-[nombre]/spec.md`

**Resumen ejecutivo:**
- [Bullet points del spec]

### 4.2 TASKS-XXX — Tareas pendientes

**Tasks completos:** `specs/[XXX]-[nombre]/tasks.md`

**Frontend ([N] tasks):**
- TF-XXX.1: [Descripción]
- TF-XXX.2: [Descripción]
- ...

**Backend ([N] tasks):**
- TB-XXX.1: [Descripción]
- TB-XXX.2: [Descripción]
- ...

**Infraestructura ([N] tasks):**
- TI-XXX.1: [Descripción]
- TI-XXX.2: [Descripción]
- ...

### 4.3 CRITERIOS DE ACEPTACIÓN (DoD)

- [ ] [Criterio 1]
- [ ] [Criterio 2]
- [ ] ...

---

## 5. CHECKLIST DE INICIO DE SESIÓN (Obligatorio)

ODIN debe ejecutar ESTO antes de tocar código:

```bash
# 1. PULL SINCRONIZACIÓN
cd /Users/innovadataco/Documents/GitHub/Desarrollos/PROYECTO-XXX-XXXXXXX
git pull origin setup/estructura-2026

# 2. RECORDAR REGLAS DE GOBIERNO
# - Leer metodologia/AGENTS.md §10 (Modo Autónomo restringido)
# - Recordar: NO puedo declarar "completado", solo "listo para validación"
# - Recordar: NO puedo tocar IDC_PROYECTOS (repo de gestión)
# - Recordar: Debo completar TODAS las tasks antes de declarar "listo"

# 3. VERIFICAR ESTADO ACT-[XXX-1]
# - Leer docs/auditoria/REGISTRO-ACTIVIDADES.md
# - Verificar que módulo anterior está VALIDADO

# 4. CAMBIAR DE CONTEXTO MENTAL
# - Módulo [XXX-1] = DONE
# - Módulo [XXX] = NUEVO
# - No mezclar código de módulos

# 5. INICIAR REGISTRO DE FECHAS
# - Escribir INICIO en esta instrucción
# - Formato: Inicio: YYYY-MM-DD HH:MM CST (Shanghai) / HH:MM (Bogotá)

# 6. REVISAR SPEC Y TASKS
# - Leer specs/[XXX]-[nombre]/spec.md (completo)
# - Leer specs/[XXX]-[nombre]/tasks.md (completo)
# - Leer specs/[XXX]-[nombre]/plan.md (completo)
```

---

## 6. REGLAS DE IMPLEMENTACIÓN

### 6.1 Commits (obligatorio)

Cada task = commit individual. Formato:
```
feat(PROYECTO-XXX): Módulo [XXX] - [TF/TB/TI-XXX.X] descripción breve

Refs: TASKS-XXX, SPEC-XXX
```

### 6.2 Tests (obligatorio)

- Cada backend task = tests unitarios (pytest)
- Cada frontend task = tests con Vitest/React Testing Library
- Coverage ≥ 80% para backend
- Tests de integración con TestClient
- NO declarar "listo" sin tests

### 6.3 Seguridad (obligatorio)

- [Reglas de seguridad específicas del módulo]

### 6.4 UX/UI (obligatorio)

- [Reglas de UX/UI específicas del módulo]

---

## 7. FLUJO DE TRABAJO

```
┌─────────────────┐
│  INICIO SESIÓN  │ ← Checklist de inicio (obligatorio)
│   (ODIN registra│
│    timestamps)  │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  IMPLEMENTACIÓN │ ← TODAS las tasks, commit por commit
│   (ODIN ejecuta) │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  VERIFICACIÓN   │ ← ¿Todas las tasks completas?
│   (ODIN verifica)│ ← Si NO → Continuar implementando
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
│   (ODIN escribe) │ ← SOLO si TODAS las tasks están completas
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

## 8. DECISIÓN DEL CEO

**[Nombre del CEO] decide:**

☐ **APROBADO** — ODIN procede con implementación del Módulo [XXX]
☐ **RECHAZADO** — Se requiere ajuste en spec/tasks antes de implementar
☐ **DIFERIDO** — Módulo [XXX] para más adelante

**Firma:** ___________________  
**Fecha/Hora:** YYYY-MM-DD ___________  

---

## 9. HISTORIAL

| Fecha | Evento | Actor |
|-------|--------|-------|
| YYYY-MM-DD | Módulo [XXX-1] VALIDADO | ZEUS |
| YYYY-MM-DD | Emisión de INSTRUCCIÓN-ODIN-[XXX].md | ZEUS |
| YYYY-MM-DD | PENDIENTE: Firma del CEO | [CEO] |
| YYYY-MM-DD | PENDIENTE: Inicio de implementación | ODIN |

---

> **"Template de instrucción con regla de alcance completo."**
> **ZEUS — CEO PMO**
