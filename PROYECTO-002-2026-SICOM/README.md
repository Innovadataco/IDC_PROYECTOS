# PROYECTO 002-2026: SICOM — Sistema de Información de Combustibles Minerales

**Sistema Operativo Empresarial:** ZEUS EOS  
**Metodología:** PM2 (Project Management Methodology)  
**Entidad:** Ministerio de Minas y Energía (MME)  
**Contrato:** GGC-2034-2025  
**Gerente de Proyecto CI2:** Luis Felipe Herrera (CI2 / IND TECH)  
**Director de Empalme / PM Ejecutivo:** Jelkin Zair Carrillo Franco (Innovadataco)  
**Fecha de Inicio del Empalme:** 19 de mayo de 2026  
**Última Actualización:** 12 de junio de 2026  
**Estado:** 🔴 **CERRADO** — Empalme finalizado por decisión del Director de Empalme  
**Motivo de cierre:** CI2 (Luis Felipe Herrera) no confirmó continuidad del proyecto. Sin avances operativos. Inviable continuar.  
**Fecha de cierre:** 12 de junio de 2026  
**Duración efectiva:** 25 días (de 42 planificados)  
**Acción post-cierre:** Notificar CI2 y MME; archivar repo; documentar lecciones aprendidas

---

## 📋 Resumen Ejecutivo

El **Sistema de Información de Combustibles Minerales (SICOM)** es un sistema de información crítico operado por el **Ministerio de Minas y Energía (MME)** de Colombia. Su función principal es monitorear la cadena de suministro de combustibles, controlar precios e inventarios, regular el mercado y reportar a entidades de control.

| Parámetro | Valor |
|-----------|-------|
| **Operador Actual (Saliente)** | INTERNEXA S.A. |
| **Operador Nuevo (Entrante)** | CI2 / IND TECH |
| **Contrato Vigente** | GGC-2034-2025 (MME ↔ INTERNEXA) |
| **Periodo de Empalme** | 19 mayo — 30 junio 2026 (6 semanas) |
| **Inicio Operación CI2** | 1 julio 2026 |
| **Vigencia Contrato** | 01 julio — 30 noviembre 2026 (5 meses) |
| **Plataformas** | JAVA, BPM, Web, APPs, BI, DataMart |
| **ANS Disponibilidad** | 99.90% |
| **Equipo Mínimo Requerido** | 31 personas |

---

## 🏛️ Estructura de Gobernanza del Empalme

```
┌─────────────────────────────────────────────────────────┐
│              MINISTERIO DE MINAS Y ENERGÍA               │
│                      (MME) — Elizabeth                   │
│              Supervisora del Contrato                    │
└──────────────────────┬──────────────────────────────────┘
                       │ Supervisa contractualmente
                       │ Recibe reportes quincenales
                       ▼
┌─────────────────────────────────────────────────────────┐
│              CI2 / IND TECH                              │
│         Luis Felipe Herrera                              │
│       Gerente de Proyecto CI2                            │
│    Recibe reportes de avance semanales                   │
│    Aprueba hitos y decisiones estratégicas               │
│    Reporta al MME quincenalmente                         │
└──────────────────────┬──────────────────────────────────┘
                       │
                       │ Reporta avances semanales
                       │ Coordina ejecución técnica
                       ▼
┌─────────────────────────────────────────────────────────┐
│              INNOVADATACO                                │
│      Jelkin Zair Carrillo Franco                         │
│    Director de Empalme / PM Ejecutivo                    │
│    Contratado por IND TECH para ejecutar el empalme      │
│    Gestiona equipo técnico CI2                           │
│    Controla calidad PM2                                  │
│    Documenta todo el proceso                           │
└──────────────────────┬──────────────────────────────────┘
                       │
                       │ Trabaja con
                       ▼
┌─────────────────────────────────────────────────────────┐
│              INTERNEXA S.A.                              │
│         Operador Saliente                                │
│    Entrega documentación, accesos, código                │
│    Soporte técnico durante el empalme                    │
│    Destruye datos post-cesión                            │
└─────────────────────────────────────────────────────────┘
```

---

## 📅 Cronograma del Empalme (Actualizado 12 Jun 2026)

| Fase | Periodo | Duración | Estado | Hitos |
|------|---------|----------|--------|-------|
| **F0: Preparación y Gobierno** | 19 may — 25 may | 1 semana | ✅ Completado | Gobierno instalado |
| **F1: Inventario y Documentación** | 26 may — 14 jun | 3 semanas | 🔄 En curso | Inventario técnico validado |
| **F2: Acceso y Validación** | 02 jun — 12 jun | ~2 semanas | 🔄 En curso | Accesos validados |
| **F3: Transferencia de Conocimiento** | 10 jun — 24 jun | ~2 semanas | ⏳ Pendiente | Shadowing iniciado |
| **F4: Replicación y Pruebas** | 17 jun — 30 jun | ~2 semanas | ⏳ Pendiente | Pruebas de aceptación |
| **F5: Corte y Migración** | 26 jun — 30 jun | 5 días | ⏳ Pendiente | Corte controlado |
| **F6: Operación y Estabilización** | 01 jul — 15 jul | 2 semanas | ⏳ Pendiente | Operación plena CI2 |
| **F7: Transferencia Final** | Nov 2026 | 1 mes | ⏳ Pendiente | Cierre contrato CI2 |

**Fecha actual:** 12 de junio de 2026 — **Día 25 de 42** (59% del empalme)

---

## 📁 Estructura de Documentos PM2

```
PROYECTO-002-2026-SICOM/
├── 00-META/
│   ├── 00-PORTADA.md
│   ├── 01-INDICE.md
│   ├── 02-GLOSARIO.md
│   └── 03-MAPA-FASES.md
├── 01-INICIO/
│   ├── 01-CASO-NEGOCIOS.md
│   ├── 02-FICHA-TECNICA.md
│   ├── 03-ACTA-CONSTITUCION.md
│   ├── 04-ACTA-KICKOFF.md
│   ├── 05-STAKEHOLDERS.md
│   └── 06-REQUISITOS-INICIALES.md
├── 02-PLANIFICACION/
│   ├── 01-PLAN-GESTION.md
│   ├── 02-PLAN-ALCANCE.md
│   ├── 03-PLAN-CALIDAD.md
│   ├── 04-PLAN-COMUNICACION.md
│   ├── 05-PLAN-RIESGOS.md
│   ├── 06-PLAN-RECURSOS.md
│   ├── 07-PLAN-ADQUISICIONES.md
│   ├── 08-PLAN-CRONOGRAMA.md
│   ├── 09-PLAN-COSTOS.md
│   ├── 10-PLAN-IMPLEMENTACION.md
│   ├── 11-PLAN-TRANSICION.md
│   └── 12-PLAN-VALOR.md
├── 03-EJECUCION/
│   ├── 01-REGISTROS-AVANCE.md
│   ├── 02-INFORMES-SEMANALES.md
│   ├── 03-ACTAS-REUNIONES.md
│   ├── 04-INCIDENCIAS.md
│   └── 05-DECISIONES.md
├── 04-CIERRE/
│   ├── 01-INFORME-FINAL.md
│   ├── 02-LECCIONES-APRENDIDAS.md
│   └── 03-INFORME-VALOR.md
├── 05-ENTREGABLES/
│   ├── E1-Informe-Empalme/
│   ├── E2-Informes-Mensuales/
│   ├── E3-Informe-Final/
│   └── E4-Transferencia-Conocimiento/
└── 06-EMPALME/          ← NUEVO — Documentos empalme Junio 2026
    ├── 01-PLAN-EMPALME.md
    ├── 02-INFORME-EMPALME-V2.md
    ├── 03-PLAN-EMPALME-CRONOGRAMA-REAL.md
    ├── 04-CHECKLIST-EMPALME-POR-COMPONENTE.md
    ├── 05-CRONOGRAMA-EMPALME-COMPLETO.xlsx
    ├── 06-CRONOGRAMA-EMPALME-COMPLETO-MULTIHOJA.xlsx
    └── 07-CRONOGRAMA-EMPALME-COMPLETO-V2.xlsx
```

---

## 📊 Nuevos Artefactos del Empalme (Junio 2026)

| Documento | Fecha | Descripción | Estado |
|-----------|-------|-------------|--------|
| 01-PLAN-EMPALME.md | 06 jun | Plan maestro del empalme | ✅ Completado |
| 02-INFORME-EMPALME-V2.md | 06 jun | Informe V2 del empalme | ✅ Completado |
| 03-PLAN-EMPALME-CRONOGRAMA-REAL.md | 06 jun | Cronograma real ajustado | ✅ Completado |
| 04-CHECKLIST-EMPALME-POR-COMPONENTE.md | 07 jun | Checklist por componente | ✅ Completado |
| 05-CRONOGRAMA-EMPALME-COMPLETO.xlsx | 07 jun | Cronograma Excel completo | ✅ Completado |
| 06-CRONOGRAMA-EMPALME-COMPLETO-MULTIHOJA.xlsx | 07 jun | Cronograma multi-hoja | ✅ Completado |
| 07-CRONOGRAMA-EMPALME-COMPLETO-V2.xlsx | 07 jun | Cronograma V2 final | ✅ Completado |

---

## 📊 Riesgos Principales (Actualizado 12 Jun 2026)

| ID | Riesgo | Probabilidad | Impacto | Estrategia | Estado |
|----|--------|--------------|---------|------------|--------|
| R001 | INTERNEXA no coopera con la entrega | Alta | Crítico | Escalar a Elizabeth (MME) contractualmente | 🔄 Mitigando |
| R002 | Documentación de INTERNEXA incompleta | Alta | Alto | Validar con pruebas técnicas | 🔄 En validación |
| R003 | Backups no restaurables | Media | Crítico | Validar restore en Semana 3, tener plan B | ⏳ Pendiente |
| R004 | Credenciales no transferibles | Media | Alto | Resetear credenciales | 🔄 En proceso |
| R005 | Dependencia de personas clave de INTERNEXA | Alta | Alto | Identificar y entrevistar ASAP | 🔄 En proceso |
| R006 | Infraestructura destino CI2 no está lista | Media | Alto | Plan B: cloud temporal | 🔄 Verificando |
| R007 | Pruebas de estrés revelan fallas | Media | Alto | Corregir antes del corte | ⏳ Pendiente |
| R008 | Brechas de seguridad no detectadas | Media | Crítico | Auditoría de seguridad en Semana 5 | ⏳ Pendiente |
| R009 | Retraso en contratación de 31 personas | Alta | Alto | Plan de contratación express | 🔄 En proceso |
| R010 | Plazo de empalme insuficiente (42 días) | Alta | Alto | Negociar extensión con MME | ⏳ Evaluando |

---

## 📋 Próximas Acciones Críticas (Semana 4)

1. ✅ Validar accesos a plataformas (F2)
2. ✅ Completar inventario técnico (F1)
3. 🔄 Iniciar shadowing con INTERNEXA (F3)
4. 🔄 Contratación de 31 personas — **URGENTE**
5. ⏳ Validar backups y restauración
6. ⏳ Pruebas de estrés en ambiente CI2
7. ⏳ Preparar corte controlado (F5)

---

## 🔗 Enlaces Relacionados

- [📘 PORTFOLIO.md](../PORTFOLIO.md) — Portafolio completo Innovadataco
- [📁 Documento Maestro del Empalme](./06-EMPALME/01-PLAN-EMPALME.md)
- [📋 Análisis Contractual INTERNEXA-SICOM](./Analisis_Contractual_INTERNEZA-SICOM.md) — Hallazgos de obligaciones contractuales y transición
- [🔴 Análisis de Riesgo de Migración](./Analisis_Riesgo_Migracion_SICOM.md) — Evaluación honesta de probabilidad de éxito
- [📊 Super Documento SICOM](./Super_Documento_SICOM.md) — Documento maestro completo (48 docs, 16 secciones, 8 anexos)

---

> **ZEUS — Sistema Operativo Empresarial**  
> *Innovadataco — Inteligencia Artificial para la Gestión de Proyectos*  
> *Última actualización: 2026-06-12 — Semana 4 del Empalme*
