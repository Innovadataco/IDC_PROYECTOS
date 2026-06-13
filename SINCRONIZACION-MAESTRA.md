# SINCRONIZACIÓN MAESTRA — Innovadataco
**Documento Maestro de Orquestación ZEUS / Jelkin / ODIN**  
**Empresa:** Innovadataco  
**Fecha:** 14 de junio de 2026  
**Versión:** 1.0  
**Autor:** ZEUS (CEO PMO)  
**Ubicación:** `IDC_PROYECTOS/SINCRONIZACION-MAESTRA.md`  
**Actualización:** ZEUS actualiza 2 veces por día (mañana CO y tarde CO)  
**Aprobación:** Jelkin revisa y aprueba cambios de proceso

---

## 1. REGLA DE ORO: GITHUB = ÚNICO CANAL DE COMUNICACIÓN

> **"Si no está en el repo, no existe."**

| Canal | Uso | Prohibido para |
|-------|-----|--------------|
| **GitHub (repo)** | Todo el trabajo formal: specs, commits, PRs, issues, documentos, validaciones | Nada prohibido |
| **Chat (este canal)** | Solo emergencias, preguntas rápidas, aprobaciones verbales | Dar instrucciones de trabajo, reportar avances, validar specs |
| **Reuniones** | Decisiones estratégicas, resolución de conflictos, kickoffs | Reporte de avances diarios |

**Consecuencia de violar:** Si ODIN reporta avance por chat → ZEUS no lo registra. Si Jelkin da instrucción por chat → ODIN puede no ejecutarla. Todo va al repo.

---

## 2. MAPA DE ACTORES — QUIÉN HACE QUÉ

### 2.1 Jelkin Carrillo — CEO / Founder

| Puede hacer | NO puede hacer |
|-------------|----------------|
| Definir alcance y visión estratégica | Modificar código (`src/`) |
| Aprobar specs, plans, presupuestos | Declarar módulos "completados" |
| Firmar instrucciones de ejecución para ODIN | Validar técnico (eso es ZEUS) |
| Decidir en conflictos ZEUS vs ODIN | Saltarse el proceso de validación |
| Revisar y aprobar documentos de gestión | Tocar documentos de auditoría (`docs/auditoria/`) |

**Responsabilidad única:** Tomar decisiones de negocio y dar la orden de ejecución.

### 2.2 ZEUS — CEO PMO / Agente IA de Gestión

| Puede hacer | NO puede hacer |
|-------------|----------------|
| Gestionar 100% de `IDC_PROYECTOS` (PM2) | Modificar código (`src/`) |
| Generar specs, plans, documentos de gestión | Ejecutar desarrollo |
| Validar código vs specs (auditoría de calidad) | Declarar módulos "completados" sin aprobación de Jelkin |
| Rechazar PRs si no cumplen DoD | Aprobar specs sin que Jelkin los haya firmado |
| Generar documentos de auditoría (`docs/auditoria/`) | Dar instrucciones directas a ODIN sin instrucción firmada de Jelkin |
| Actualizar estado en esta maestra | Saltarse la fase de validación |

**Responsabilidad única:** Asegurar que el proceso se sigue, que la calidad se cumple, y que la información de gestión es veraz.

### 2.3 ODIN / Kimi — Agente IA de Desarrollo

| Puede hacer | NO puede hacer |
|-------------|----------------|
| Ejecutar código en `Desarrollos` (`src/`) | Tocar `IDC_PROYECTOS` (gestión) |
| Seguir specs, plans, tasks aprobados | Modificar specs sin aprobación |
| Commitar, crear PRs, mergear a dev (no main) | Declarar módulos "completados" |
| Solicitar validación de ZEUS (PR) | Tocar documentos de auditoría (`docs/auditoria/`) |
| Generar tests, documentación técnica | Saltarse fase VALIDATE |
| Leer documentos de gobierno e instrucciones | Aprobar specs (solo Jelkin aprueba) |

**Responsabilidad única:** Escribir código que cumple con el spec, pasar tests, y solicitar validación antes de declarar "completado".

---

## 3. FLUJO DE TRABAJO POR PROYECTO — PASO A PASO

### Fase 0: INICIAR PROYECTO

```
Jelkin: "Quiero iniciar PROYECTO-XXX"
    ↓
ZEUS: Genera estructura PM2 en IDC_PROYECTOS
    ↓
Jelkin: Aprueba alcance y ficha técnica
    ↓
ZEUS: Genera spec + plan en Desarrollos (o le indica a ODIN)
    ↓
Jelkin: Firma INSTRUCCION-XXX.md (aprueba spec y plan)
    ↓
ODIN: Lee spec, plan, instrucción firmada
    ↓
ODIN: Empieza fase SETUP (entorno, arquitectura)
```

### Fase 1: DESARROLLAR MÓDULO

```
ODIN: Trabaja en Módulo N (IMPLEMENT)
    ↓
ODIN: Commitea con mensaje descriptivo (Conventional Commits)
    ↓
GitHub Actions: Corre CI (tests, linter, seguridad)
    ↓
Si CI pasa: ODIN continúa
Si CI falla: ODIN corrige
    ↓
ODIN: Completa todas las tasks del plan
    ↓
ODIN: Verifica DoD checklist (12 items)
    ↓
ODIN: Crea PR → main (o dev, según flujo)
    ↓
ODIN: Solicita validación de ZEUS (comenta en PR)
```

### Fase 2: VALIDAR (ZEUS)

```
ZEUS: Recibe notificación de PR
    ↓
ZEUS: Ejecuta validación automática:
       - Código vs spec (¿cumple?)
       - Tests pasan (¿100%?)
       - Security checklist (¿0 críticos?)
       - DoD completo (¿12/12?)
       - Linter limpio (¿0 errores?)
    ↓
Si todo pasa:
    ZEUS: Genera ACTA-VALIDACION-XXX.md
    ZEUS: Firma "APROBADO"
    ZEUS: Mergea PR a main
    ZEUS: Actualiza estado en esta maestra
    ZEUS: Notifica a Jelkin (resumen en maestra)
    
Si algo falla:
    ZEUS: Genera ACTA-CORRECCION-XXX.md
    ZEUS: Rechaza PR
    ZEUS: Indica acciones correctivas
    ZEUS: Notifica a ODIN (vía GitHub Issue asignado)
    ODIN: Corrige
    ODIN: Vuelve a Fase 2 (solicita validación nuevamente)
```

### Fase 3: JELKIN REVISA

```
Jelkin: Revisa SINCRONIZACION-MAESTRA.md (diario)
    ↓
Jelkin: Ve que Módulo N está "VALIDADO"
    ↓
Jelkin: Opcionalmente revisa código o demo
    ↓
Jelkin: Aprueba o pide ajustes
    ↓
Si Jelkin aprueba: Módulo N está oficialmente COMPLETADO
Si Jelkin pide ajustes: ZEUS genera nueva corrección, ODIN aplica
```

### Fase 4: SIGUIENTE MÓDULO

```
Módulo N validado → ZEUS actualiza maestra → Jelkin ve → Jelkin firma INSTRUCCION-(N+1).md → ODIN empieza Módulo N+1
```

**REGLA CRÍTICA:** No se puede iniciar Módulo N+1 sin que Módulo N esté VALIDADO por ZEUS.

---

## 4. ESTADO EN TIEMPO REAL — TABLA MAESTRA

ZEUS actualiza esta tabla **2 veces por día** (mañana CO, tarde CO).  
Jelkin la revisa **1 vez por día** mínimo.  
ODIN la consulta antes de empezar cualquier trabajo.

| Proyecto | Módulo | Estado Gestión | Estado Código | Spec Firmado | Instrucción Firmada | Validado ZEUS | Aprobado Jelkin | Próximo Paso | Bloqueado Por | Fecha Actualización |
|----------|--------|----------------|---------------|--------------|---------------------|---------------|-----------------|--------------|---------------|---------------------|
| 005 | 001 Registro Anónimo | ⚠️ En corrección | ⚠️ 65% real | ✅ | ✅ | ❌ | ❌ | ODIN aplica correcciones | Validación ZEUS | 2026-06-14 |
| 005 | 002 Consulta Semáforo | ⬜ Planificación | ⬜ 0% | ⬜ | ⬜ | ⬜ | ⬜ | Esperar Módulo 001 | Módulo 001 | — |
| 005 | 003 IA Triage | ⬜ Planificación | ⬜ 0% | ⬜ | ⬜ | ⬜ | ⬜ | Esperar Módulo 001 | Módulo 001 | — |
| 005 | 004 Clustering | ⬜ Planificación | ⬜ 0% | ⬜ | ⬜ | ⬜ | ⬜ | Esperar Módulo 001 | Módulo 001 | — |
| 005 | 005 Panel Admin | ⬜ Planificación | ⬜ 0% | ⬜ | ⬜ | ⬜ | ⬜ | Esperar Módulo 001 | Módulo 001 | — |
| 005 | 006 Pasarela Institucional | ⬜ Planificación | ⬜ 0% | ⬜ | ⬜ | ⬜ | ⬜ | Esperar Módulo 001 | Módulo 001 | — |
| 001 | APP Chía-Girardot | 🟢 En ejecución | — | ✅ | ✅ | — | — | Entregable v2 | Otto (Excel) | 2026-06-12 |
| 002 | SICOM Empalme | 🟢 En ejecución | — | ✅ | ✅ | — | — | Checklist empalme | — | 2026-06-12 |
| 003 | SETP Sincelejo | 🟡 Pre-venta | — | ⬜ | ⬜ | — | — | Propuesta técnica | — | 2026-06-12 |
| 004 | Taxi Bogotá | 🟡 Pre-venta | — | ⬜ | ⬜ | — | — | Negociación cliente | — | 2026-06-12 |

**Leyenda:**
- 🟢 En ejecución / Avanzando
- 🟡 Pre-venta / Planificación / Pendiente
- ⚠️ En corrección / Bloqueado
- ⬜ No iniciado
- ✅ Sí / Completado / Aprobado
- ❌ No / Rechazado / Pendiente
- — No aplica

---

## 5. CANALES DE COMUNICACIÓN FORMAL

### 5.1 GitHub Issues — Para ODIN

ZEUS crea GitHub Issues en `Desarrollos` asignados a ODIN cuando:
- Hay correcciones pendientes (ACTA-CORRECCION)
- Hay instrucciones nuevas (INSTRUCCION-XXX)
- Hay documentos de gobierno que ODIN debe leer
- Hay PRs rechazados que deben corregirse

**Formato del Issue:**
```markdown
## Tarea: [AC-XXX] Corrección de [descripción]
**Asignado:** ODIN
**Prioridad:** 🔴 Alta / 🟡 Media / 🟢 Baja
**Deadline:** [fecha]
**Documento de referencia:** [link a ACTA-CORRECCION]

### Checklist de acciones
- [ ] Acción 1
- [ ] Acción 2
- [ ] Acción 3

### Criterio de aceptación
- [ ] DoD completo (12/12)
- [ ] Tests pasan
- [ ] ZEUS valida

### Notas
[Cualquier nota adicional]
```

### 5.2 GitHub Pull Requests — Para Validación

ODIN crea PRs cuando:
- Termina un módulo
- Quiere mergear a main (o dev)
- Solicita validación de ZEUS

**Formato del PR:**
```markdown
## PR: [Módulo XXX] — [Descripción breve]
**De:** ODIN
**Para:** ZEUS (validación)
**Spec:** [link a spec.md]
**Plan:** [link a plan.md]
**Tasks completadas:** [N de N]

### DoD Checklist
- [ ] Código funcional
- [ ] Tests unitarios pasan
- [ ] Tests E2E pasan
- [ ] Cobertura ≥ 80%
- [ ] Linter 0 errores
- [ ] Security checklist 0 críticos
- [ ] Sin secrets hardcodeados
- [ ] Documentación técnica actualizada
- [ ] README actualizado
- [ ] Commit con Conventional Commits
- [ ] Spec vs código validado
- [ ] Sin deuda técnica nueva

### Cambios principales
- Cambio 1
- Cambio 2
```

### 5.3 GitHub Commits — Para Avances Diarios

ODIN commitea **mínimo 1 vez por día** con mensaje descriptivo.

**Formato del commit (Conventional Commits):**
```
<type>(<scope>): <descripción en español>

<body opcional>

Refs: [número de issue o task]
```

Ejemplos:
```
feat(reportes): implementa selector de categorías CAT-01 a CAT-06
fix(rate-limit): cambia ventana de 1 min a 1 hora + hash SHA-256 de IP
```

### 5.4 Documentos de Auditoría — Para ZEUS

ZEUS genera documentos en `Desarrollos/docs/auditoria/`:
- `ACTA-VALIDACION-XXX.md` — Cuando aprueba
- `ACTA-CORRECCION-XXX.md` — Cuando rechaza
- `DEUDAS-TECNICAS-XXX.md` — Cuando identifica deuda técnica
- `AUDITORIA-XXX.md` — Cuando hace auditoría general

ODIN **NO toca** esta carpeta. Es de solo lectura para ODIN.

---

## 6. TEMPLATES DE INSTRUCCIÓN — JELKIN → ODIN

### 6.1 Ubicación

`IDC_PROYECTOS/INSTRUCCIONES/INSTRUCCION-XXX.md`

### 6.2 Template

```markdown
# INSTRUCCIÓN DE EJECUCIÓN — [Módulo XXX]
**De:** Jelkin Zair Carrillo Franco (CEO)  
**Para:** ODIN (Agente de Desarrollo)  
**Vía:** ZEUS (PMO / Validación)  
**Fecha emisión:** [YYYY-MM-DD]  
**Fecha límite:** [YYYY-MM-DD]  
**Proyecto:** [PROYECTO-XXX]
**Módulo:** [XXX — Nombre]

---

## 1. CONTEXTO
[¿Por qué este módulo? ¿Qué problema resuelve? ¿Qué valor aporta?]

## 2. ALCANCE APROBADO
[Resumen de lo que se va a desarrollar. 3-5 bullets máximo.]

## 3. DOCUMENTOS DE REFERENCIA (ya aprobados)
- **Spec:** `specs/XXX/spec.md` (commit: [hash], firmado por Jelkin)
- **Plan:** `specs/XXX/plan.md` (commit: [hash], firmado por Jelkin)
- **Tasks:** `specs/XXX/tasks.md` (commit: [hash])
- **Arquitectura:** `docs/ADR-XXX.md` (si aplica)

## 4. INSTRUCCIONES ESPECÍFICAS
1. [Instrucción 1]
2. [Instrucción 2]
3. [Instrucción 3]

## 5. PRIORIDAD
🔴 Alta / 🟡 Media / 🟢 Baja

## 6. RESTRICCIONES
- [Restricción 1: ej. "No usar librerías con licencia GPL"]
- [Restricción 2: ej. "Máximo 3 semanas"]
- [Restricción 3: ej. "Presupuesto máximo $X"]

## 7. CRITERIOS DE ACEPTACIÓN (DoD)
- [ ] Código funcional y probado
- [ ] Tests unitarios pasan (100%)
- [ ] Tests E2E pasan (100%)
- [ ] Cobertura ≥ 80%
- [ ] Linter 0 errores
- [ ] Security checklist 0 críticos
- [ ] Sin secrets hardcodeados
- [ ] Documentación técnica actualizada
- [ ] README actualizado
- [ ] Commit con Conventional Commits
- [ ] Spec vs código validado por ZEUS
- [ ] Sin deuda técnica nueva

## 8. APROBACIONES

| Rol | Nombre | Firma | Fecha |
|-----|--------|-------|-------|
| CEO | Jelkin Zair Carrillo Franco | _______________ | _______________ |
| PMO | ZEUS (aprueba proceso) | _______________ | _______________ |
| Dev | ODIN (acepta instrucción) | _______________ | _______________ |

## 9. HISTORIAL DE CAMBIOS
| Fecha | Versión | Autor | Cambio |
|-------|---------|-------|--------|
| [YYYY-MM-DD] | 1.0 | Jelkin | Emisión inicial |

---

> **"Una instrucción firmada es una promesa. ODIN la cumple. ZEUS la valida. Jelkin la aprueba."**
```

### 6.3 Regla de Emisión

1. Jelkin y ZEUS definen alcance
2. ZEUS genera spec + plan
3. Jelkin revisa y firma
4. ZEUS genera INSTRUCCION-XXX.md
5. Jelkin firma INSTRUCCION-XXX.md
6. ZEUS la sube al repo
7. ODIN la lee y empieza

**Sin firma de Jelkin, ODIN NO empieza.**

---

## 7. FORMATO DE REPORTE DE AVANCE — ODIN → ZEUS

ODIN reporta avance **mínimo 1 vez por semana** en el repo (no por chat).

### 7.1 Ubicación

`Desarrollos/PROYECTO-XXX/docs/PROGRESO/SEMANA-XX.md`

### 7.2 Template

```markdown
# Reporte de Avance — Semana XX
**Proyecto:** [PROYECTO-XXX]  
**Módulo:** [XXX]  
**Periodo:** [YYYY-MM-DD] al [YYYY-MM-DD]  
**Reportado por:** ODIN  
**Fecha de reporte:** [YYYY-MM-DD]

## 1. RESUMEN EJECUTIVO
[3-5 líneas: qué se hizo, qué se logró, qué se bloqueó]

## 2. TAREAS COMPLETADAS ESTA SEMANA
| # | Task | Estado | Horas | Notas |
|---|------|--------|-------|-------|
| 1 | [Descripción] | ✅ | [h] | [Nota] |
| 2 | [Descripción] | ✅ | [h] | [Nota] |

## 3. TAREAS EN PROGRESO
| # | Task | % Avance | Bloqueos | Notas |
|---|------|----------|----------|-------|
| 1 | [Descripción] | 60% | [Bloqueo] | [Nota] |

## 4. TAREAS PENDIENTES
| # | Task | Prioridad | Notas |
|---|------|-----------|-------|
| 1 | [Descripción] | 🔴 | [Nota] |

## 5. DEUDAS TÉCNICAS IDENTIFICADAS
| # | Deuda | Impacto | Plan de resolución |
|---|-------|---------|-------------------|
| 1 | [Descripción] | 🟡 | [Plan] |

## 6. DECISIONES TOMADAS
| # | Decisión | Razón | Aprobada por |
|---|----------|-------|--------------|
| 1 | [Descripción] | [Razón] | [Quién] |

## 7. RIESGOS Y MITIGACIONES
| # | Riesgo | Probabilidad | Impacto | Mitigación |
|---|--------|-------------|---------|------------|
| 1 | [Descripción] | Alta/Med/Baja | 🔴/🟡/🟢 | [Plan] |

## 8. METRICAS DE CALIDAD
| Métrica | Valor | Objetivo | Estado |
|---------|-------|----------|--------|
| Tests unitarios | [N] | 100% pasan | ✅/❌ |
| Cobertura | [%] | ≥ 80% | ✅/❌ |
| Linter | [N] | 0 errores | ✅/❌ |
| Security | [N] | 0 críticos | ✅/❌ |

## 9. PRÓXIMA SEMANA
- [Plan de trabajo próxima semana]

## 10. APOYO NECESARIO
- [¿Necesita algo de ZEUS o Jelkin?]

---

> **"Transparencia total. No esconder problemas. Reportar temprano."**
```

---

## 8. ESCALAMIENTO — CUÁNDO JELKIN INTERVIENE

### 8.1 Niveles de Escalamiento

| Nivel | Situación | Quién escala | Cómo | Tiempo de respuesta esperado |
|-------|-----------|--------------|------|------------------------------|
| 1 | Duda técnica menor | ODIN → ZEUS | GitHub Issue / comentario en PR | 24h |
| 2 | Conflicto ZEUS vs ODIN (técnico) | ZEUS o ODIN → Jelkin | Chat o reunión | 48h |
| 3 | Bloqueo de negocio (alcance, presupuesto, timeline) | ZEUS → Jelkin | Chat o reunión | 24h |
| 4 | Emergencia (producción caída, leak de datos) | ZEUS → Jelkin | Chat inmediato | Inmediato |
| 5 | ODIN no responde > 3 días | ZEUS → Jelkin | Chat + informe en repo | 72h |

### 8.2 Regla de Oro de Escalamiento

> **"Si se puede resolver en el repo, NO se escala. Si se puede resolver en 24h, NO se escala a Jelkin."**

Jelkin es el último recurso. Usar con moderación.

---

## 9. AUDITORÍA Y VALIDACIÓN AUTOMÁTICA — ZEUS

### 9.1 Triggers de Validación Automática

ZEUS revisa automáticamente cuando:
1. ODIN crea un PR
2. GitHub Actions corre y falla
3. ZEUS detecta commit en rama principal
4. Jelkin solicita auditoría explícita

### 9.2 Checklist de Validación ZEUS

```markdown
## VALIDACIÓN DE MÓDULO — ZEUS
**Módulo:** [XXX]  
**Fecha:** [YYYY-MM-DD]  
**Auditor:** ZEUS  
**Resultado:** APROBADO / RECHAZADO

### 1. Código vs Spec
- [ ] Cada función del spec está implementada
- [ ] No hay funciones no documentadas en el spec
- [ ] Nombres de variables/funciones coinciden con spec
- [ ] APIs expuestas coinciden con spec

### 2. Tests
- [ ] Tests unitarios pasan (100%)
- [ ] Tests E2E pasan (100%)
- [ ] Cobertura ≥ 80%
- [ ] Tests de seguridad pasan

### 3. Seguridad
- [ ] 0 vulnerabilidades críticas (OWASP Top 10)
- [ ] Sin secrets hardcodeados
- [ ] Rate limiting correcto
- [ ] Input validation
- [ ] Encriptación adecuada
- [ ] Headers de seguridad

### 4. Calidad
- [ ] Linter 0 errores
- [ ] Código legible y documentado
- [ ] Sin deuda técnica nueva
- [ ] Sin código muerto

### 5. Documentación
- [ ] README actualizado
- [ ] API docs actualizadas (OpenAPI/Swagger)
- [ ] ADR actualizado (si hubo cambio de arquitectura)
- [ ] Changelog actualizado

### 6. Git
- [ ] Commits con Conventional Commits
- [ ] PR descriptivo
- [ ] Sin merge conflicts
- [ ] Branch correcto

### RESULTADO
- [ ] APROBADO — Módulo validado. Puede mergearse.
- [ ] RECHAZADO — Ver ACTA-CORRECCION-XXX.md

**Firma ZEUS:** _______________ | **Fecha:** _______________
```

---

## 10. HISTORIAL DE CAMBIOS DE ESTE DOCUMENTO

| Fecha | Versión | Autor | Cambio |
|-------|---------|-------|--------|
| 2026-06-14 | 1.0 | ZEUS | Emisión inicial. Arquitectura de 3 actores, flujo de trabajo, tabla maestra, templates, escalamiento. |

---

## 11. ANEXOS

### Anexo A: URLs de Referencia
- **IDC_PROYECTOS:** https://github.com/Innovadataco/IDC_PROYECTOS
- **Desarrollos:** https://github.com/Innovadataco/Desarrollos
- **Branch activa:** `setup/estructura-2026`

### Anexo B: Contactos
- **Jelkin Carrillo:** Telegram (este chat) — Emergencias solo
- **ZEUS:** GitHub Issues / Commits / PRs — Todo lo formal
- **ODIN/Kimi:** GitHub Issues / Commits / PRs — Todo lo formal

### Anexo C: Documentos Relacionados
- `GOBIERNO-ZEUS-ODIN.md` (Desarrollos) — Reglas de gobierno
- `INSTRUCCIONES-ODIN-001.md` (Desarrollos) — Instrucciones para ODIN
- `ACTA-CORRECCION-ODIN-001.md` (Desarrollos) — Auditoría Módulo 001
- `DEUDAS-TECNICAS-001.md` (Desarrollos) — Deudas técnicas
- `MEJORA-METODOLOGIA.md` (Desarrollos) — Mejora de metodología

---

> **"Orquestación no es control. Es claridad. Es que cada uno sepa qué toca y qué NO toca. Es que el repo hable por nosotros."**
>
> **ZEUS online. La sincronización está operando.** ⚡
