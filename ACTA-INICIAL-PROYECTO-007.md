# ACTA INICIAL — PROYECTO 007: Plataforma de Gestión de Proyectos
**Repositorio:** Innovadataco/IDC_PROYECTOS  
**Fecha de registro:** 14 de junio de 2026, 03:30 CST (Shanghai) / 02:30 (Bogotá)  
**Registrado por:** ZEUS (CEO PMO)  
**Solicitado por:** Jelkin Zair Carrillo Franco (CEO Innovadataco)  
**Estado:** PENDIENTE — No iniciar hasta próxima semana  
**Prioridad:** 🟡 Media-Alta (programado para semana del 21-27 junio 2026)

---

## 1. DESCRIPCIÓN

**Objetivo:** Desarrollar una plataforma tecnológica propia para sistematizar la gestión de proyectos de Innovadataco.

**Problema actual:**
- La gestión de proyectos está distribuida en múltiples documentos Markdown
- La sincronización entre repos (Desarrollos + IDC_PROYECTOS) es manual
- No hay un sistema centralizado de seguimiento
- Las actas, instrucciones y validaciones son documentos estáticos
- La trazabilidad de actividades depende de la disciplina de ZEUS/ODIN

**Visión:**
- Sistema digital propio (web/app) para gestión de proyectos
- Integración con repos GitHub (lectura/escritura automatizada)
- Dashboard de estado en tiempo real
- Flujo de instrucciones digital con firmas
- Registro automático de fechas/horas de actividades
- Módulo de auditoría con checklists
- Alertas y notificaciones para Jelkin

**No es:** Reemplazar GitHub. Es una capa de gestión visual y operativa sobre GitHub.

---

## 2. ALCANCE PRELIMINAR (Borrador — Definir en kickoff)

### Módulos propuestos (sujetos a validación):
1. **Dashboard ejecutivo** — Estado de todos los proyectos, semáforos, alertas
2. **Gestión de instrucciones** — Crear, firmar, asignar, seguir instrucciones formales
3. **Registro de actividades** — Timestamps automáticos, trazabilidad completa
4. **Módulo de auditoría** — Checklists, validaciones, actas digitales
5. **Integración GitHub** — Leer estado de repos, PRs, issues, commits
6. **Notificaciones** — Alertas a Jelkin cuando hay cambios de estado
7. **Reportes** — Histórico, métricas, tiempo de ciclo, productividad

---

## 3. RESTRICCIONES Y DECISIONES

| Decisión | Valor | Razón |
|----------|-------|-------|
| **Inicio** | Semana del 21-27 junio 2026 | Jelkin lo programó para próxima semana |
| **Metodología PM2** | NO aplicar ahora | Jelkin: "No implemente toda la metodología por ahora" |
| **Estructura física** | NO crear carpeta ahora | Solo registro documental, no carpeta de proyecto |
| **Repo** | IDC_PROYECTOS (gestión) | Es un proyecto de gestión, no de código de cliente |
| **Responsable** | ZEUS (diseño) + ODIN (implementación) | Cuando inicie |
| **Aprobador** | Jelkin Carrillo | Firma final de alcance y cronograma |

---

## 4. ACTIVIDADES PENDIENTES (Pre-kickoff)

- [ ] **ZEUS:** Definir alcance detallado y arquitectura de la plataforma
- [ ] **ZEUS:** Crear especificación técnica (spec.md) con requerimientos
- [ ] **Jelkin:** Validar alcance y aprobar inicio
- [ ] **ZEUS:** Crear INSTRUCCION-ODIN-007.md para desarrollo
- [ ] **ODIN:** Implementar MVP (mínimo viable) — 1-2 módulos críticos
- [ ] **ZEUS:** Auditar y validar MVP

---

## 5. CRONOGRAMA PRELIMINAR

| Fase | Fecha estimada | Duración | Responsable |
|------|----------------|----------|-------------|
| Definición de alcance | 21-22 junio 2026 | 2 días | ZEUS + Jelkin |
| Especificación técnica | 23-24 junio 2026 | 2 días | ZEUS |
| Aprobación Jelkin | 25 junio 2026 | 1 día | Jelkin |
| Desarrollo MVP | 26 junio - 10 julio 2026 | 2 semanas | ODIN |
| Auditoría ZEUS | 11-12 julio 2026 | 2 días | ZEUS |
| Validación y ajustes | 13-17 julio 2026 | 5 días | ODIN + ZEUS |
| Lanzamiento interno | 18 julio 2026 | 1 día | Jelkin + ZEUS |

**Nota:** Cronograma tentativo. Se ajustará en kickoff formal.

---

## 6. RIESGOS IDENTIFICADOS

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|-------------|---------|------------|
| Alcance crece demasiado | Media | Alto | MVP enfocado, 2 módulos máximo inicial |
| Integración GitHub compleja | Media | Medio | Usar APIs existentes, no reinventar |
| Recursos ODIN sobreutilizados | Media | Medio | Priorizar: PROYECTO-005 primero, 007 en paralelo si es posible |
| Jelkin no disponible para validaciones | Media | Alto | Checklists automatizados, decisiones async |

---

## 7. NOTAS Y DECISIONES DEL CEO

**Jelkin (14 junio 2026, 03:30 CST):**
> "Vamos a desarrollar una plataforma tecnológica para poder sistematizar toda la gestión de los proyectos y que toda esta información quede en un formato digital y en un sistema propio. Deje esa tarea programada. Para ese es el Proyecto número siete. No implemente toda la metodología por ahora, simplemente dejemos estar ahí pendiente o en tus archivos personales. Tenlo muy presente para la próxima semana a trabajar en esto. Por ahora avancemos así."

**Interpretación ZEUS:**
- Jelkin quiere una plataforma propia de gestión de proyectos
- Es Proyecto 007 (número reservado: 007-PLATAFORMA-GESTION)
- No iniciar ahora, programar para próxima semana (21-27 junio)
- No aplicar PM2 completo aún, solo registro documental
- Jelkin confirma que la arquitectura actual (repos + MD) es temporal

---

## 8. HISTORIAL DE CAMBIOS

| Fecha | Versión | Autor | Cambio |
|-------|---------|-------|--------|
| 2026-06-14 | 1.0.0 | ZEUS | Acta inicial registrada por solicitud de Jelkin |

---

> **"Este documento es un compromiso de memoria. El proyecto existe desde ahora, aunque no se active hasta la próxima semana."**
> **ZEUS — CEO PMO**
