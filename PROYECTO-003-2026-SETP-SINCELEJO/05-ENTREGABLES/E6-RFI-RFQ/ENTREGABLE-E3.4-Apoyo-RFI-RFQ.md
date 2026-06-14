# ENTREGABLE 3.4 — APOYO EN ELABORACIÓN DE RFI Y RFQ

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E3.4  
**Versión:** 1.0  
**Fecha:** 15 de junio de 2026

---

## 1. RESUMEN EJECUTIVO

Este documento contiene el apoyo en la elaboración de la Solicitud de Información (RFI) y la Solicitud de Cotización (RFQ) para la adquisición de los componentes tecnológicos del SETP Sincelejo, basado en los **4 sistemas definidos desde 2015** (SRC, SGCF, SIU, SST) y el proceso de contratación 2023 con el MinTransporte.

**Antecedentes de contratación:**
- **2015:** Estructuración tecnológica (Steer Davies Gleave + GSD+) definiendo SRC, SGCF, SIU y 3 escenarios institucionales
- **2022:** Actualización del modelo (Contrato CM-001-2022, A4 Asociados)
- **2023:** MinTransporte lanzó proceso de contratación ITS para 46 vehículos (9 meses, pago condicionado a validación)
- **2025:** Metro Sabanas lanzó **RFI que integra 3 contratos** (flota + tecnología + operación), no una adquisición por lotes tradicional
- **2026:** Esta consultoría apoya la estructuración de los requerimientos para la contratación

**⚠️ Nota importante:** El RFI 2025 de Metro Sabanas NO es una adquisición por lotes tradicional (Lote 1, 2, 3...). Es un **RFI de integración de 3 contratos** que permite a la empresa operadora proponer modelos integrados de flota + tecnología + operación. Esta consultoría apoya la estructuración de los requerimientos técnicos para ese proceso.

**Escala:** 46 vehículos (proceso 2023, RFI 2025)

---

## 2. MARCO DE ADQUISICIÓN

### 2.1 Estrategia de Contratación

| Fase | Documento | Objetivo |
|------|-----------|----------|
| 1 | **RFI** | Conocer el mercado, tecnologías disponibles, proveedores potenciales |
| 2 | **RFQ** | Solicitar cotizaciones formales basadas en especificaciones técnicas |
| 3 | **Evaluación** | Comparar ofertas técnicas y económicas |
| 4 | **Adjudicación** | Seleccionar proveedor y firmar contrato |

### 2.2 Lotes de Adquisición Propuestos

| Lote | Descripción | Estimación de Inversión |
|------|-------------|------------------------|
| **Lote 1** | Unidades Onboard (GPS, validadores, pantallas) | Por definir |
| **Lote 2** | Infraestructura Centro de Control (servidores, red, CCTV) | Por definir |
| **Lote 3** | Software de gestión (plataforma, app, backoffice) | Por definir |
| **Lote 4** | Sistema de pago electrónico (validadores, backoffice, pasarela) | Por definir |
| **Lote 5** | Implementación e integración | Por definir |

---

## 3. RFI — SOLICITUD DE INFORMACIÓN

### 3.1 Datos Generales del RFI

| Campo | Descripción |
|-------|-------------|
| **Entidad convocante** | Metro Sabanas S.A.S. |
| **Objeto** | Información sobre tecnologías ITS para SETP Sincelejo |
| **Fecha de publicación** | [Por definir] |
| **Fecha límite respuestas** | [Por definir] |
| **Idioma** | Español |
| **Forma de respuesta** | Documento digital (PDF) + presentación opcional |

### 3.2 Información Solicitada a Proveedores

#### A. Información de la Empresa

1. Razón social, NIT, años de operación
2. Certificaciones de calidad (ISO 9001, ISO 27001, etc.)
3. Experiencia en proyectos ITS o transporte público (mínimo 3 referencias)
4. Capacidad financiera (estados financieros últimos 2 años)
5. Presencia y soporte técnico en Colombia

#### B. Información Tecnológica

| Tema | Preguntas |
|------|-----------|
| **Onboard** | ¿Ofrecen unidades GPS con comunicación 4G, conteo de pasajeros, validación NFC? |
| **Plataforma** | ¿Su plataforma es cloud-native, on-premise o híbrida? |
| **Pagos** | ¿Integran con pasarelas de pago colombianas (Redeban, ACH)? |
| **Interoperabilidad** | ¿Cumplen con la Resolución 20203040034065 del MinTransporte? |
| **Seguridad** | ¿Cumplen con PCI DSS para pagos? ¿Ofrecen cifrado end-to-end? |
| **Escalabilidad** | ¿Cuántos vehículos soportan su plataforma? ¿Es escalable? |

#### C. Modelo de Negocio

1. ¿Ofrecen modelo SaaS, licencia perpetua, o ambos?
2. ¿Cuál es el costo de implementación inicial?
3. ¿Cuál es el costo mensual/anual de mantenimiento?
4. ¿Incluyen capacitación? ¿En qué modalidad?
5. ¿Ofrecen SLA de disponibilidad? ¿Cuál?

### 3.3 Formato de Respuesta RFI

```
1. Portada y carta de presentación
2. Perfil de la empresa (máx. 3 páginas)
3. Descripción de solución propuesta (máx. 10 páginas)
4. Respuestas a preguntas (punto por punto)
5. Referencias de proyectos similares (mínimo 3)
6. Anexos técnicos opcionales
```

---

## 4. RFQ — SOLICITUD DE COTIZACIÓN

### 4.1 Datos Generales del RFQ

| Campo | Descripción |
|-------|-------------|
| **Entidad convocante** | Metro Sabanas S.A.S. |
| **Objeto** | Adquisición e implementación de sistema ITS para SETP Sincelejo |
| **Plazo de ejecución** | 12 meses desde firma de contrato |
| **Garantía técnica** | Mínimo 24 meses |
| **Soporte** | Mínimo 12 meses post-implementación |
| **Moneda** | Pesos colombianos (COP) |
| **Forma de pago** | Contra entregables mensuales |

### 4.2 Especificaciones Técnicas del RFQ

#### Lote 1 — Unidades Onboard (46 vehículos)

| Ítem | Cantidad | Especificación mínima |
|------|----------|----------------------|
| Rastreador GPS 4G | 46 | ARM 4 núcleos, 4GB RAM, 64GB, GPS multi-GNSS, 4G Cat-4 |
| Validador NFC | 46 | Pantalla 5", NFC ISO 14443, 4G, Android |
| Pantalla conductor | 46 | LCD 7", resistente a vibraciones |
| Sensor conteo pasajeros | 46 | IR/ToF, precisión > 95% |
| Sensor puertas | 68 | Reed switch / IR |
| Instalación y configuración | 46 | Incluido |

#### Lote 2 — Centro de Control

| Ítem | Cantidad | Especificación mínima |
|------|----------|----------------------|
| Servidor aplicación | 2 | 8 vCPU, 32GB RAM, 500GB SSD |
| Servidor base de datos | 2 | 8 vCPU, 32GB RAM, 1TB SSD |
| Storage NAS | 1 | 4TB, RAID 5 |
| Firewall | 1 | 1 Gbps, UTM |
| Switch administrable | 2 | 24 puertos, PoE |
| UPS | 1 | 2 kVA, 30 min |
| Rack 19" | 1 | 42U con PDU |
| Estaciones de trabajo | 3 | Monitor 27", i5/Ryzen 5, 16GB RAM |
| NVR CCTV | 1 | 32 canales, 30 días retención |
| Cámaras IP | 10 | 4MP, IR, IP66 |

#### Lote 3 — Software y Plataforma

| Ítem | Licencia | Descripción |
|------|----------|-------------|
| Plataforma de gestión de flota | SaaS / On-premise | Monitoreo GPS, rutas, reportes |
| App móvil usuarios | Incluida | iOS + Android |
| Backoffice de pagos | Incluido | Conciliación, tarifas, reportes |
| Dashboard BI | Incluido | Visualización, KPIs, analytics |
| API de integración | Incluida | REST/GraphQL, documentada |

#### Lote 4 — Implementación y Servicios

| Ítem | Descripción |
|------|-------------|
| Ingeniería de implementación | Diseño de red, instalación, configuración |
| Migración de datos | Si aplica |
| Capacitación | 40 horas presenciales + material online |
| Documentación | Técnica, operativa, de usuario |
| Soporte nivel 1 y 2 | Primer año incluido |
| Actualizaciones | Parches de seguridad y mejoras |

### 4.3 Criterios de Evaluación RFQ

| Criterio | Peso | Descripción |
|----------|------|-------------|
| **Cumplimiento técnico** | 40% | Cumplimiento de especificaciones mínimas |
| **Experiencia y referencias** | 20% | Proyectos similares en Colombia/LATAM |
| **Precio total** | 20% | Valor total de propuesta (menor es mejor) |
| **Soporte y garantía** | 10% | SLAs, tiempos de respuesta, garantía |
| **Innovación y valor agregado** | 10% | Funcionalidades adicionales propuestas |

### 4.4 Formato de Propuesta RFQ

```
ANEXO TÉCNICO
1. Carta de presentación y compromiso
2. Constitución legal y poder
3. Certificaciones de calidad
4. Hoja de vida empresa (HV)
5. Experiencia (mínimo 3 proyectos similares)
6. Propuesta técnica detallada
7. Plan de trabajo y cronograma
8. Plan de capacitación
9. Garantías ofrecidas
10. Anexos técnicos adicionales

ANEXO FINANCIERO
1. Propuesta económica detallada (por lotes)
2. Desglose de costos (hardware, software, servicios)
3. Forma de pago propuesta
4. Vigencia de oferta (mínimo 90 días)
```

---

## 5. CALENDARIO DE ADQUISICIÓN

| Actividad | Duración | Dependencia |
|-----------|----------|-------------|
| Publicación RFI | 1 día | Aprobación entregables E2.1, E2.2, E3.1, E3.2 |
| Recepción respuestas RFI | 15 días hábiles | Publicación RFI |
| Análisis RFI y preselección | 5 días hábiles | Cierre RFI |
| Elaboración RFQ | 5 días hábiles | Análisis RFI |
| Publicación RFQ | 1 día | Aprobación RFQ |
| Recepción propuestas RFQ | 20 días hábiles | Publicación RFQ |
| Evaluación técnica | 10 días hábiles | Cierre RFQ |
| Evaluación financiera | 5 días hábiles | Evaluación técnica |
| Negociación y adjudicación | 10 días hábiles | Evaluación financiera |
| Firma de contrato | 5 días hábiles | Adjudicación |

**Duración total estimada:** ~76 días hábiles (~3.5 meses)

---

## 6. RIESGOS EN ADQUISICIÓN

| ID | Riesgo | Mitigación |
|----|--------|------------|
| RA-01 | Falta de proveedores en mercado colombiano | Ampliar búsqueda a LATAM, considerar importación |
| RA-02 | Propuestas técnicamente insuficientes | RFI previo para calificar mercado |
| RA-03 | Precios superan presupuesto | Definir escenarios must-have vs nice-to-have |
| RA-04 | Retrasos en entrega de equipos | Contratos con penalidades por retraso |
| RA-05 | Fallas en integración | Requerir POC (Proof of Concept) antes de compra |

---

## 7. MODELO DE EVALUACIÓN

### 7.1 Matriz de Puntaje Técnico (100 puntos)

| Aspecto | Puntos | Criterio de evaluación |
|---------|--------|----------------------|
| Cumplimiento especificaciones | 40 | 1 punto por cada % de cumplimiento |
| Arquitectura y escalabilidad | 15 | 0-15 según robustez propuesta |
| Seguridad | 15 | 0-15 según controles de seguridad |
| Experiencia | 15 | 5 pts por proyecto similar en Colombia |
| Soporte y capacitación | 10 | 0-10 según plan propuesto |
| Innovación | 5 | 0-5 por funcionalidades adicionales |

### 7.2 Fórmula de Puntaje Total

```
Puntaje Total = (Puntaje Técnico × 0.60) + (Puntaje Financiero × 0.40)

Donde:
- Puntaje Financiero = (Precio menor / Precio propuesta) × 100
```

---

**Preparado por:** Innovadataco  
**Fecha:** 15 de junio de 2026  
**Aprobado por:** _________________________
