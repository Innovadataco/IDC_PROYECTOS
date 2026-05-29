# ACTA DE CONSTITUCIÓN DEL PROYECTO
## PROYECTO 004-2026-SETP-SINCELEJO

---

## 1. INFORMACIÓN GENERAL

| Campo | Valor |
|-------|-------|
| **Nombre del Proyecto** | Sistema Estratégico de Transporte Público (SETP) Sincelejo — Componente Tecnológico |
| **Código** | PROYECTO-004-2026-SETP-SINCELEJO |
| **Patrocinador** | METRO SABANAS S.A.S. |
| **Gerente de Proyecto** | Jelkin Zair Carrillo Franco (INNOVADATACO) |
| **Fecha de emisión** | 2026-05-29 |
| **Versión** | 1.0 |

---

## 2. JUSTIFICACIÓN DEL PROYECTO

### 2.1 Contexto
Sincelejo no cuenta con un sistema de transporte público formal estructurado. El deterioro progresivo post-COVID, la competencia desleal del mototaxismo y la ausencia de sistemas de control y recaudo modernos hacen imperativa la implementación de un SETP con componente tecnológico robusto.

### 2.2 Problemática
- Ausencia de flota adecuada y sistemas de control
- No existe recaudo electrónico ni control de flota
- Competencia desleal del mototaxismo (documentada en estudios)
- Deterioro de ingresos de operadores informales
- Necesidad de cumplir Decreto 482 de 2023

### 2.3 Oportunidad
La consultoría 2022 (A4 ASOCIADOS) completó el modelo de transporte y la estructuración financiera. Los estudios previos de tecnología 2023 definieron el presupuesto (~$3.800M COP). El RFI 2025 validó el interés del mercado. **INNOVADATACO** tiene la oportunidad de estructurar y acompañar el componente tecnológico ITS.

---

## 3. OBJETIVOS DEL PROYECTO

### 3.1 Objetivo General
Estructurar, diseñar y acompañar la implementación del componente tecnológico ITS del SETP Sincelejo, integrando recaudo, control de flota, información al usuario y seguridad de transacciones.

### 3.2 Objetivos Específicos
1. Revisar documentación técnica existente (consultoría 2022 + estudios previos 2023 + RFI 2025)
2. Diseñar arquitectura ITS de referencia para Sincelejo
3. Estructurar especificaciones técnicas para contratación
4. Definir modelo de contratación, hitos y riesgos
5. Acompañar licitación y selección de proveedor tecnológico
6. Transferir conocimiento a METRO SABANAS

---

## 4. ALCANCE

### 4.1 Dentro del Alcance (IN-SCOPE)
- Revisión exhaustiva documentación tecnológica existente
- Diseño arquitectura ITS (5 capas: campo, comunicaciones, procesamiento, aplicación, presentación)
- Especificaciones técnicas detalladas (SRC, SGCF, SIU, SST)
- Modelo de contratación y forma de pago
- Presupuesto detallado CAPEX/OPEX
- Plan de implementación 15 meses
- Acompañamiento licitación y evaluación ofertas
- Transferencia de conocimiento

### 4.2 Fuera del Alcance (OUT-OF-SCOPE)
- Contratación y adquisición de flota vehicular (75 microbuses)
- Construcción de infraestructura física (patios, talleres, estaciones)
- Operación del SETP (rutas, conductores, mantenimiento)
- Implementación física de sistemas (instalación a bordo)
- Gestión de permisos y trámites regulatorios

### 4.3 Supuestos
- METRO SABANAS dispondrá del presupuesto aprobado ($3.800M COP fase 1)
- La flota de 46 buses (fase 1) será adquirida por proceso separado
- El entorno regulatorio no cambiará sustancialmente
- La conectividad celular 4G/5G es viable en Sincelejo

### 4.4 Restricciones
- Presupuesto máximo: $3.793.756.953 COP (fase 1)
- Plazo de ejecución contrato tecnología: 9 meses
- Flota fase 1: 46 buses
- Cumplimiento Decreto 482 de 2023 y Resolución 20203040034065

---

## 5. REQUERIMIENTOS DE ALTO NIVEL

| ID | Requerimiento | Categoría | Prioridad |
|:--:|:-------------|:----------|:---------:|
| R1 | Sistema de Recaudo Centralizado (SRC) con Mifare/QR/EMV | Funcional | ALTA |
| R2 | Sistema de Gestión y Control de Flota (SGCF) con GPS | Funcional | ALTA |
| R3 | Sistema de Información al Usuario (SIU) con app móvil | Funcional | MEDIA |
| R4 | Sistema de Seguridad de Transacciones (SST) con SAM/HSM | Funcional | ALTA |
| R5 | Arquitectura cloud-first con microservicios | Técnico | ALTA |
| R6 | APIs abiertas para interoperabilidad | Técnico | ALTA |
| R7 | Comunicaciones seguras (TLS/SSL, VPN) | Técnico | ALTA |
| R8 | Licencias de uso perpetuas | Legal | ALTA |
| R9 | Transferencia completa de conocimiento | Gestión | ALTA |
| R10 | Capacitación mínima 40 horas personal Metro Sabanas | Gestión | MEDIA |

---

## 6. RIESGOS INICIALES

| ID | Riesgo | Probabilidad | Impacto | Estrategia |
|:--:|:-------|:------------:|:-------:|:-----------|
| R1 | Demanda real < proyectada (20.724 pax/día) | ALTA | CRÍTICO | Mitigar: piloto gradual, ajuste frecuencias |
| R2 | Dependencia conectividad celular 4G/5G | ALTA | ALTO | Mitigar: redundancia comunicaciones |
| R3 | Ciberataque a sistema recaudo | MEDIA | CRÍTICO | Mitigar: HSM, segmentación, auditoría |
| R4 | Retraso adquisición flota (46 buses) | MEDIA | ALTO | Mitigar: cronograma integrado |
| R5 | Falta interoperabilidad futura | MEDIA | MEDIO | Mitigar: estándares abiertos desde diseño |
| R6 | Dependencia FEST (subsidio) | ALTA | ALTO | Mitigar: acuerdo financiación estable |
| R7 | Escasez proveedores locales ITS | BAJA | MEDIO | Aceptar: licitación nacional |

---

## 7. HITOS PRINCIPALES

| Hito | Descripción | Fecha Estimada |
|:----:|:------------|:---------------|
| M1 | Aprobación Acta Constitución | 2026-05-30 |
| M2 | Entrega diagnóstico documentación | 2026-06-15 |
| M3 | Aprobación arquitectura ITS | 2026-07-15 |
| M4 | Entrega especificaciones técnicas | 2026-08-30 |
| M5 | Aprobación modelo contratación | 2026-09-15 |
| M6 | Entrega estructuración completa | 2026-10-30 |
| M7 | Cierre proyecto estructuración | 2026-11-15 |

---

## 8. PRESUPUESTO ESTIMADO (INNOVADATACO)

| Fase | Descripción | Valor Estimado (COP) |
|:-----|:------------|:--------------------:|
| Diagnóstico | Revisión docs, gap analysis | $15.000.000 — $25.000.000 |
| Diseño | Arquitectura ITS, TDRs | $30.000.000 — $45.000.000 |
| Estructuración | Presupuesto, cronograma, riesgos | $25.000.000 — $40.000.000 |
| Acompañamiento | Soporte licitación | $15.000.000 — $25.000.000 |
| **TOTAL** | | **$85.000.000 — $135.000.000** |

---

## 9. CRITERIOS DE ÉXITO

| Criterio | Métrica | Meta |
|:---------|:--------|:----:|
| Cobertura documentación | % docs revisados | 100% |
| Cumplimiento normativo | Checklist Decreto 482/2023 | 100% |
| Claridad especificaciones | Índice ambigüedad | < 5% |
| Viabilidad presupuesto | % ajuste a presupuesto oficial | ± 10% |
| Satisfacción cliente | Encuesta METRO SABANAS | ≥ 4.5/5 |
| Transferencia conocimiento | % personal capacitado | 100% |

---

## 10. APROBACIONES

| Rol | Nombre | Firma | Fecha |
|:----|:-------|:------|:------|
| Patrocinador | Oscar Iván Viana Gómez (Metro Sabanas) | _________ | _______ |
| Gerente Proyecto | Jelkin Zair Carrillo Franco | _________ | _______ |
| Asesor Tecnología | ZEUS / INNOVADATACO | _________ | _______ |

---

**Documento generado por ZEUS — Agente IA Estratégico INNOVADATACO**
**Fecha:** 2026-05-29
**Versión:** 1.0

---

> **"ZEUS online. La empresa está operando."** ⚡
