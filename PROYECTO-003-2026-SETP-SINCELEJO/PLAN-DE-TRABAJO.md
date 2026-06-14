# PLAN DE TRABAJO — PROYECTO 003-2026: SETP SINCELEJO

**Fecha:** 15 de junio de 2026  
**Estado:** 🟡 Fase 0 — Exploración / Preparación  
**Bloqueo:** Pendiente firma de contrato  
**PMO:** ZEUS (INNOVADATACO)  
**Director:** Jelkin Zair Carrillo Franco

---

## 🎯 OBJETIVO DEL PLAN

Estructurar el proyecto SETP Sincelejo bajo metodología PM2, preparar todos los artefactos de INICIO y PLANIFICACIÓN, y definir el plan de entregables para cuando se firme el contrato y se active el proyecto.

**Diferencia clave con APP Chía-Girardot:**
- APP Chía-Girardot: Corredor vial (306 km), 6 UF, 15 tramos, 93 subtramos
- SETP Sincelejo: Sistema urbano de transporte público (ciudad), flota ~34 buses, 5 rutas

---

## 📁 ESTRUCTURA PM2 A CREAR

```
PROYECTO-003-2026-SETP-SINCELEJO/
├── 00-META/              ← Documentos de control
├── 01-INICIO/            ← Fase de inicio (6 artefactos)
├── 02-PLANIFICACION/     ← Fase de planificación (12 planes)
├── 03-EJECUCION/         ← Fase de ejecución (registros, entregables)
├── 04-CIERRE/            ← Fase de cierre (3 informes)
└── 05-ENTREGABLES/       ← Productos del proyecto
```

---

## 📋 ENTREGABLES DEL PROYECTO (Propuesta)

Basado en análisis de proyectos SETP similares y la estructura de APP Chía-Girardot:

| # | Entregable | Descripción | Estado | Dependencia |
|---|-----------|-------------|--------|-------------|
| **E1** | **Clasificación ITS** | Servicios ITS prioritarios para SETP urbano, matriz de aplicabilidad | 🔴 Pendiente | Contrato firmado |
| **E2** | **Arquitectura ITS** | Arquitectura multinivel, gobernanza, marcos de referencia | 🔴 Pendiente | E1 |
| **E3** | **ConOps + EOVs** | Concepto de Operación, Escenarios Operativos de Valor | 🔴 Pendiente | E2 |
| **E4** | **Diseño de Componentes** | Fichas técnicas de componentes de campo | 🔴 Pendiente | E3 |
| **E5** | **RF/RNF + Plan** | Requisitos funcionales/no funcionales, cronograma de implementación | 🔴 Pendiente | E4 |
| **E6** | **Modelo de Costos** | Estimación de inversión ITS, 5 hitos de pago | 🔴 Pendiente | E5 |
| **E7** | **Propuesta Técnica** | Documento de contratación / licitación | 🔴 Pendiente | E1-E6 |

---

## 📅 CRONOGRAMA DE ACTIVACIÓN (Post-Firma)

### Fase 0: Preparación (Actual — Sin contrato)
| Actividad | Responsable | Duración | Estado |
|-----------|-------------|----------|--------|
| Estructurar PM2 | ZEUS | 1 día | 🟡 En curso |
| Revisar carpeta Drive | ZEUS | Por definir | ⏳ Esperando acceso |
| Identificar contacto SETP | Jelkin | 1-3 días | ⏳ Pendiente |
| Preparar templates | ZEUS | 2 días | ⏳ Pendiente |

### Fase 1: Inicio (Semana 1-2 post-firma)
| Actividad | Responsable | Duración | Producto |
|-----------|-------------|----------|----------|
| Acta de Constitución | ZEUS | 2 días | 01-INICIO/03-ACTA-CONSTITUCION.md |
| Ficha Técnica | ZEUS | 2 días | 01-INICIO/02-FICHA-TECNICA.md |
| Caso de Negocios | ZEUS | 3 días | 01-INICIO/01-CASO-NEGOCIOS.md |
| Acta de Kick-off | Jelkin | 1 día | 01-INICIO/04-ACTA-KICKOFF.md |
| Stakeholders | ZEUS | 1 día | 01-INICIO/05-STAKEHOLDERS.md |

### Fase 2: Planificación (Semana 3-4 post-firma)
| Actividad | Responsable | Duración | Producto |
|-----------|-------------|----------|----------|
| Plan de Gestión | ZEUS | 2 días | 02-PLANIFICACION/01-PLAN-GESTION.md |
| Plan de Alcance | ZEUS | 2 días | 02-PLANIFICACION/02-PLAN-ALCANCE.md |
| Plan de Calidad | ZEUS | 1 día | 02-PLANIFICACION/03-PLAN-CALIDAD.md |
| Plan de Riesgos | ZEUS | 2 días | 02-PLANIFICACION/05-PLAN-RIESGOS.md |
| Plan de Cronograma | ZEUS | 2 días | 02-PLANIFICACION/08-PLAN-CRONOGRAMA.md |
| Plan de Costos | ZEUS | 3 días | 02-PLANIFICACION/09-PLAN-COSTOS.md |

### Fase 3: Ejecución — Entregables (Semana 5-12 post-firma)
| Entregable | Responsable | Duración | Semana |
|-----------|-------------|----------|--------|
| E1 — Clasificación ITS | ZEUS | 5 días | 5-6 |
| E2 — Arquitectura ITS | ZEUS | 7 días | 6-7 |
| E3 — ConOps + EOVs | ZEUS | 7 días | 7-8 |
| E4 — Diseño Componentes | ZEUS | 10 días | 8-10 |
| E5 — RF/RNF + Plan | ZEUS | 7 días | 10-11 |
| E6 — Modelo de Costos | ZEUS | 5 días | 11-12 |
| E7 — Propuesta Técnica | ZEUS | 5 días | 12-13 |

---

## 🚨 DEPENDENCIAS CRÍTICAS

| # | Dependencia | Bloqueo | Acción |
|---|-------------|---------|--------|
| 1 | **Firma de contrato** | 🔴 CRÍTICO | Jelkin gestiona con Alcaldía |
| 2 | **Acceso a carpeta Drive** | 🟡 ALTO | Jelkin comparte contenido o lista de archivos |
| 3 | **Contacto SETP / Alcaldía** | 🟡 ALTO | Identificar stakeholder técnico |
| 4 | **Términos de Referencia** | 🟡 MEDIO | Revisar si existen en Drive |
| 5 | **Estudios previos** | 🟢 BAJO | Documentación de base para E1-E2 |

---

## 📊 ESTADO ACTUAL (15 Jun 2026)

| Fase PM2 | Estado | % | Notas |
|----------|--------|:-:|:------|
| 00-META | 🟡 En preparación | 25% | README actualizado, estructura definida |
| 01-INICIO | 🔴 Pendiente | 0% | Esperando contrato |
| 02-PLANIFICACION | 🔴 Pendiente | 0% | Esperando contrato |
| 03-EJECUCION | 🔴 Pendiente | 0% | Esperando contrato |
| 04-CIERRE | 🔴 Pendiente | 0% | Esperando contrato |
| 05-ENTREGABLES | 🔴 Pendiente | 0% | Esperando contrato |

---

## 🎯 PRÓXIMAS ACCIONES (Prioridad)

| # | Acción | Responsable | Fecha Límite | Estado |
|---|--------|-------------|--------------|--------|
| 1 | **Generar estructura PM2 completa** | ZEUS | 15 jun 2026 | 🟡 En curso |
| 2 | **Jelkin comparte contenido de Drive** | Jelkin | 15-16 jun 2026 | ⏳ Pendiente |
| 3 | **Identificar contacto SETP** | Jelkin | 16 jun 2026 | ⏳ Pendiente |
| 4 | **Generar artefactos 00-META** | ZEUS | 16 jun 2026 | ⏳ Pendiente |
| 5 | **Generar artefactos 01-INICIO** | ZEUS | 17-18 jun 2026 | ⏳ Pendiente |

---

> **ZEUS PMO — INNOVADATACO**  
> *Plan de Trabajo Generado: 15 junio 2026*  
> *Estado: Preparación / Esperando contrato y documentación de base*
