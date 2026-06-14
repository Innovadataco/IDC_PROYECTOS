# PLAN DE TRABAJO — SETP Sincelejo

**Proyecto:** PROYECTO-003-2026-SETP-SINCELEJO  
**Cliente:** Metro Sabanas S.A.S.  
**Fecha:** 15 de junio de 2026  
**Versión:** 1.0

---

## 1. RESUMEN EJECUTIVO

| Aspecto | Detalle |
|---------|---------|
| **Objetivo** | Estructurar componentes tecnológicos ITS del SETP Sincelejo |
| **Duración** | 4 semanas (20 días hábiles) |
| **Presupuesto** | $39.000.000 COP (IVA incluido) |
| **Forma pago** | 3 hitos: 40% + 30% + 30% |
| **Cliente** | Metro Sabanas S.A.S. |
| **Ejecución** | Bogotá D.C. (remoto + reuniones virtuales/presenciales) |

---

## 2. ENTREGABLES Y CRONOGRAMA

### Hito 1 — Inicio y Planeación (40% — Semana 1)

| ID | Entregable | Actividades | Semana | Responsable |
|----|-----------|-------------|--------|-------------|
| **E1.1** | **Plan de Trabajo y Cronograma** | | | |
| | | PT-01: Revisión documental inicial | 1 | Innovadataco |
| | | PT-02: Identificación de actores y stakeholders | 1 | Innovadataco |
| | | PT-03: Mesa técnica inicial con Metro Sabana | 1 | Innovadataco |
| | | PT-04: Definición de metodología de trabajo | 1 | Innovadataco |
| | | PT-05: Elaboración del Plan de Trabajo | 1 | Innovadataco |
| | | PT-06: Validación del Plan con Metro Sabana | 1 | Innovadataco |

**Valor:** $15.600.000  
**Dependencias:** Ninguna (inicio del proyecto)

---

### Hito 2 — Diseño Conceptual (30% — Semanas 2-3)

| ID | Entregable | Actividades | Semana | Responsable |
|----|-----------|-------------|--------|-------------|
| **E2.1** | **Revisión y Clasificación Servicios ITS** | | | |
| | | ITS-01: Recopilación normativa ITS aplicable | 2-3 | Innovadataco |
| | | ITS-02: Revisión documentación técnica existente | 2-3 | Innovadataco |
| | | ITS-03: Identificación subsistemas ITS aplicables | 2-3 | Innovadataco |
| | | ITS-06: Documento de revisión y clasificación | 2-3 | Innovadataco |
| **E2.2** | **Arquitectura Tecnológica Conceptual** | | | |
| | | ARC-01: Definición principios arquitectónicos | 2-3 | Innovadataco |
| | | ARC-02: Diseño vista de componentes | 2-3 | Innovadataco |
| | | ARC-03: Documento de arquitectura conceptual | 2-3 | Innovadataco |
| **E3.1** | **Concepto de Operación Tecnológica** | | | |
| | | COP-01: Definición roles y responsabilidades operativos | 2-3 | Innovadataco |
| | | COP-02: Definición procesos operativos | 2-3 | Innovadataco |
| | | COP-03: Definición KPIs | 2-3 | Innovadataco |
| | | COP-04: Definición escenarios de operación | 2-3 | Innovadataco |
| | | COP-05: Documento de Concepto de Operación | 2-3 | Innovadataco |
| **E3.2** | **Diseño y Especificaciones Conceptuales** | | | |
| | | ESP-01: Especificación de subsistemas | 2-3 | Innovadataco |
| | | ESP-06: Especificación centro de control | 2-3 | Innovadataco |

**Valor:** $11.700.000  
**Dependencias:** E1.1 aprobado

---

### Hito 3 — Especificaciones y Cierre (30% — Semanas 3-4)

| ID | Entregable | Actividades | Semana | Responsable |
|----|-----------|-------------|--------|-------------|
| **E3.3** | **Requerimientos Funcionales y No Funcionales** | | | |
| | | REQ-01: Definición requerimientos funcionales | 3-4 | Innovadataco |
| | | REQ-02: Definición requerimientos no funcionales | 3-4 | Innovadataco |
| | | REQ-03: Validación requerimientos con Metro Sabana | 3-4 | Innovadataco |
| **E3.4** | **Apoyo en RFI y RFQ** | | | |
| | | RFI-01: Análisis mercado tecnológico | 3-4 | Innovadataco |
| | | RFI-02: Definición alcance RFI | 3-4 | Innovadataco |
| | | RFI-03: Elaboración RFI | 3-4 | Innovadataco |
| | | RFQ-01: Definición alcance RFQ | 3-4 | Innovadataco |
| | | RFQ-02: Elaboración RFQ | 3-4 | Innovadataco |
| | | RFQ-03: Validación RFI/RFQ con Metro Sabana | 3-4 | Innovadataco |

**Valor:** $11.700.000  
**Dependencias:** E2.1, E2.2, E3.1, E3.2 aprobados

---

## 3. CRONOGRAMA VISUAL

```
SEMANA:  [1]      [2]      [3]      [4]
         ├────────┼────────┼────────┤
HITO 1   ████████░│░░░░░░░░│░░░░░░░░│░░░░░░░░  40%
E1.1     ████████ │        │        │
         ├────────┼────────┼────────┤
HITO 2   ░░░░░░░░░│████████│████████│░░░░░░░░  30%
E2.1     │        │████████│████████│
E2.2     │        │████████│████████│
E3.1     │        │████████│████████│
E3.2     │        │████████│████████│
         ├────────┼────────┼────────┤
HITO 3   ░░░░░░░░░│░░░░░░░░│████████│████████  30%
E3.3     │        │        │████████│████████│
E3.4     │        │        │████████│████████│
         └────────┴────────┴────────┘
         
Total:   100% distribuido en 3 hitos de pago
```

---

## 4. DEPENDENCIAS ENTRE ENTREGABLES

```
E1.1 (Plan de Trabajo)
   │
   ▼
E2.1 (Revisión ITS) ──┐
E2.2 (Arquitectura) ──┤
E3.1 (ConOps) ────────┼──> Hitos 2 y 3 pueden solaparse parcialmente
E3.2 (Especificaciones)┘
   │
   ▼
E3.3 (RF/RNF)
E3.4 (RFI/RFQ)
```

---

## 5. PRÓXIMAS ACCIONES (TO-DO)

### Inmediatas (Esta semana)
- [ ] Firma de contrato con Metro Sabanas S.A.S.
- [ ] Identificar contacto técnico en Metro Sabanas
- [ ] Agendar kick-off meeting
- [ ] Solicitar documentación base al cliente

### Semana 1
- [ ] PT-01: Revisión documental inicial
- [ ] PT-02: Identificación actores
- [ ] PT-03: Mesa técnica inicial
- [ ] PT-04: Definición metodología
- [ ] PT-05: Elaborar Plan de Trabajo
- [ ] PT-06: Validar Plan con Metro Sabanas
- [ ] **Entregar E1.1 y facturar Hito 1**

### Semanas 2-3
- [ ] ITS-01 a ITS-06: Revisión normativa y subsistemas
- [ ] ARC-01 a ARC-03: Arquitectura conceptual
- [ ] COP-01 a COP-05: Concepto de Operación
- [ ] ESP-01, ESP-06: Especificaciones
- [ ] **Entregar E2.1, E2.2, E3.1, E3.2 y facturar Hito 2**

### Semanas 3-4
- [ ] REQ-01 a REQ-03: Requerimientos
- [ ] RFI-01 a RFI-03: Elaboración RFI
- [ ] RFQ-01 a RFQ-03: Elaboración RFQ
- [ ] **Entregar E3.3, E3.4 y facturar Hito 3**

---

## 6. CONDICIONES DE EJECUCIÓN

| Aspecto | Condición |
|---------|-----------|
| **Ubicación** | Bogotá D.C. (remoto) |
| **Reuniones** | Virtuales o presenciales (si las requiere Metro Sabanas) |
| **Desplazamientos** | Costos asumidos por Metro Sabanas S.A.S. |
| **Revisión entregables** | 5 días hábiles para observaciones |
| **Ajustes** | Sin costo adicional dentro del alcance |
| **Facturación** | Contra entrega de cada hito |

---

## 7. RIESGOS IDENTIFICADOS

| ID | Riesgo | Prob. | Impacto | Mitigación |
|----|--------|-------|---------|------------|
| R1 | Retraso en aprobación entregables | Media | Alto | Agregar buffer de 2 días |
| R2 | Falta de información del cliente | Media | Alto | Solicitar desde inicio |
| R3 | Cambios de alcance | Baja | Alto | Documentar versiones |
| R4 | Desplazamientos no presupuestados | Baja | Medio | Acordar previamente |

---

**Preparado por:** ZEUS (Innovadataco)  
**Fecha:** 15 de junio de 2026  
**Aprobado por:** [Pendiente firma]
