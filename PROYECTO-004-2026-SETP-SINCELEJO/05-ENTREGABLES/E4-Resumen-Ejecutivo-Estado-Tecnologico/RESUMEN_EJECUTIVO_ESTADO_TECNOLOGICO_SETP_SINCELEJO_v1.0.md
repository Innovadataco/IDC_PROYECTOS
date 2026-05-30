# RESUMEN EJECUTIVO — ESTADO TECNOLÓGICO DEL SETP SINCELEJO

**Proyecto:** PROYECTO-004-2026-SETP-SINCELEJO — Componente Tecnológico ITS  
**Elaborado por:** INNOVADATACO — Dirección de Asesoría Técnica  
**Responsable:** Jelkin Zair Carrillo Franco, CEO Estratégico  
**Fecha:** 30 de mayo de 2026  
**Clasificación:** CONFIDENCIAL — USO INTERNO / Presentación Metro Sabanas S.A.S. y UMUS  
**Versión:** 1.0  

---

## 1. RESUMEN EJECUTIVO

El Sistema Estratégico de Transporte Público (SETP) de Sincelejo, operado por Metro Sabanas S.A.S., presenta un **déficit crítico en el componente tecnológico ITS** (Sistemas Inteligentes de Transporte) que bloquea su entrada en operación. Mientras la infraestructura vial (83%) y los paraderos (100%) reportan avances significativos, los sistemas de recaudo, control de flota, gestión de operaciones y seguridad vial **registran 0% de ejecución física** al corte del primer trimestre de 2026.

El Ministerio de Transporte, a través de la UMUS (Unidad de Movilidad Urbana Sostenible), ha identificado en su reunión de seguimiento del 15 de abril de 2026 que la **certificación del 60% de entrada en operación no puede completarse sin definir criterios técnicos claros para los componentes tecnológicos**. Esto representa un riesgo regulatorio que puede afectar los desembolsos nacionales pendientes ($15.827 millones COP) y la continuidad del convenio de cofinanciación.

Desde INNOVADATACO, proponemos un plan de asesoría de **4 semanas** para cerrar los vacíos técnicos, estructurar el presupuesto ITS (hoy sin costear), definir la arquitectura de integración y garantizar que Metro Sabanas cuente con un roadmap tecnológico ejecutable para licitación e implementación.

---

## 2. ESTADO DEL COMPONENTE TECNOLÓGICO ITS — ¿QUÉ ESTÁ BIEN?

### ✅ Infraestructura vial y paraderos avanzados
- **Infraestructura vial:** 46,69 km de 56,09 km previstos (**83% de avance**).  
  *Fuente: Informe Trimestral I-2026, Anexo 1 UMUS, sección 3.2.*
- **Paraderos:** 232 unidades construidas de 232 previstas (**100% de avance**).  
  *Fuente: Informe Trimestral I-2026, sección 3.2.*
- **Sistema semafórico:** 100% instalado.  
  *Fuente: Informe Trimestral I-2026, Tabla de Metas Físicas.*

### ✅ Marco normativo definido
- Especificaciones técnicas de vehículos alineadas con normativa ambiental internacional (Protocolo Kioto, Acuerdo de París, ODS) y nacional (Leyes 1955/2019, 1964/2019, 1972/2019, 2128/2021; CONPES 3260, 3550, 3344, 3943, 3934).  
  *Fuente: ENTREGABLE 5 — Especificaciones de Autobuses, sección 1.1.*

### ✅ Modelo financiero estructurado
- Modelo financiero del operador único y del recaudo con CAPEX, OPEX, WACC, flujo de caja libre y canasta de costo definidos. Escenario validado para 5 rutas.  
  *Fuente: ENTREGABLE 7 — Estructuración Financiera; Informe Integral de Estructuración SETP Sincelejo, sección 3.*

### ✅ Reducción operacional justificada técnicamente
- Reducción de 15 rutas originales (CONPES 3637/2010) a **5 rutas / 34 microbuses / 7.670 pasajeros/día**, con base en encuestas de hogares 2021 y actualización de demanda.  
  *Fuente: MS-130-2025, Justificación Técnica a la Reprogramación de Aportes.*

---

## 3. ESTADO DEL COMPONENTE TECNOLÓGICO ITS — ¿QUÉ ESTÁ MAL Y QUÉ FALTA?

### 🔴 Crítico: 5 componentes esenciales para la operación en 0% de ejecución

| Componente | Meta CONPES | Avance I-Trim 2026 | Saldo Pendiente (M$) | Impacto si no se ejecuta |
|:---|:---|:---|:---|:---|
| **CAMIS** (Centro de Atención y Monitoreo Integral) | 1 G | **0%** | 1.875 | No hay centro de control operativo para monitorear flota y recaudo en tiempo real. |
| **Gestión de Flota y Control de Flota** | 1 G | **0%** | 5.015 | Sin sistema de seguimiento GPS, planificación de rutas ni control de conductores. |
| **Sistema de Recaudo Centralizado** | 1 G | **0%** | 664 | No hay medio de pago electrónico validado ni integración bancaria. |
| **Patios y Talleres** | 1 Und | **0%** | 4.613 | Sin infraestructura de mantenimiento preventivo y correctivo de la flota. |
| **Vehículos Nuevos** | — | **0%** | 7.511 | Sin flota no hay sistema que operar. |
| **Predios Patios y Talleres** | 1 | **0%** | 458 | Sin predio legalizado no hay dónde operar patios. |

**Total saldo concentrado en componentes sin ejecutar: $19.176 millones COP (57,6% del saldo total del proyecto).**  
*Fuentes: Informe Trimestral I-2026, secciones 3.1 y 3.2; Ayuda de Memoria Reunión 15 abril 2026.*

### 🔴 Crítico: Presupuesto ITS sin costear (valores en $0)

La plantilla de presupuesto ITS (`3._presupuesto_ITS_MetroSabanas.xlsx`) contiene la estructura completa de 23 componentes tecnológicos con cantidades definidas (34 unidades por componente de abordo, centro de control, licencias SaaS, comunicaciones, etc.), pero **TODOS los valores unitarios y totales están en $0**.

**Esto significa que:**
- No se ha realizado estudio de mercado para cotizar hardware (validadores, routers, cámaras, torniquetes, botones de pánico).
- No se han cotizado licencias de software (SaaS SRC, SGCF, SIU, SST, APIs de interoperabilidad).
- No se ha presupuestado conectividad (plan de datos para 34 buses + CCO).
- No se ha estimado servicios de implementación (gerencia de proyecto, capacitación, transferencia de conocimiento).

*Fuente: `3._presupuesto_ITS_MetroSabanas.xlsx`, hojas SRC y SST, SGCF y SIU, ITS INTEGRADO.*

### 🔴 Crítico: Sin criterios técnicos para certificación del 60% de operación

La UMUS exige certificar el 60% de entrada en operación para habilitar recursos. Sin embargo:
- **No existen indicadores técnicos y operativos consensuados** entre MinTransporte, UMUS y Metro Sabanas.
- No está definido qué porcentaje del componente tecnológico debe estar implementado para contar como "operación".
- No hay matriz de trazabilidad entre metas físicas, metas financieras y criterios de certificación.

*Fuente: Ayuda de Memoria Reunión 15 abril 2026, Aspectos Críticos #3.*

### 🟡 Mayor: Déficit operacional tarifa técnica vs tarifa usuario

El modelo financiero muestra una brecha entre la tarifa técnica (costo real de operación) y la tarifa al usuario. Sin el componente tecnológico ITS (recaudo electrónico), esta brecha se amplía porque:
- El recaudo manual (efectivo) tiene mayores costos operativos y riesgo de evasión.
- No hay datos de demanda en tiempo real para ajustar frecuencias y rutas.
- No hay mecanismo de compensación automática (FET — Fondo de Estabilización Tarifaria) sin sistema de recaudo centralizado.

*Fuente: ENTREGABLE 7 — Estructuración Financiera, sección 6.2; Ayuda de Memoria Reunión 15 abril 2026, Aspectos Críticos #8 y #9.*

### 🟡 Mayor: Aportes municipio pendientes — Riesgo de terminación anticipada

El municipio de Sincelejo debe desembolsar aportes territoriales pendientes que fueron incluidos en el presupuesto 2026 como vigencias expiradas. Si no se ejecutan, existe **cláusula de terminación anticipada del convenio**.  
Saldo aportes municipio: **$2.330 millones COP (96% ejecutado, 4% pendiente).**

*Fuente: Informe Trimestral I-2026, sección 6.1.2; Ayuda de Memoria Reunión 15 abril 2026, Aspectos Críticos #1.*

---

## 4. ANÁLISIS DEL INFORME DEL MINISTERIO (UMUS) — ESTADO DE LOS COMPONENTES TECNOLÓGICOS E ITS

### Reunión de Seguimiento UMUS — 15 de abril de 2026

La UMUS identificó los siguientes problemas críticos que afectan directamente el componente tecnológico:

#### 4.1. Fortalecimiento institucional — Equipo técnico
**Compromiso:** Gestionar un modelo corporativo que mantenga el equipo técnico básico.  
**Fecha límite:** Junio de 2026.  
**Estado:** En proceso.  
**Impacto tecnológico:** Sin equipo técnico especializado (DBA, desarrolladores, ingenieros de redes), no hay quién diseñe, implemente ni opere los sistemas ITS.

#### 4.2. Implementación operativa e infraestructura tecnológica
**Compromiso:** Contratación de personal especializado para estructuración jurídica de procesos de operación y tecnología.  
**Fecha límite:** Diciembre de 2025 (vencido).  
**Estado:** No reportado como cumplido.  
**Impacto tecnológico:** Procesos de licitación tecnológica no han iniciado. No hay contratos para adquirir ni instalar sistemas ITS.

#### 4.3. Inicio de operación proyectado
**Compromiso:** Adelantar actividades para puesta en operación del SETP.  
**Fecha límite:** Diciembre de 2026.  
**Estado:** Riesgo de incumplimiento por bloqueos tecnológicos.  
**Impacto tecnológico:** Sin los 5 componentes en 0% ni el presupuesto ITS costeado, es improbable alcanzar operación en diciembre 2026.

#### 4.4. Distribución de recursos para procesos licitatorios
**Compromiso:** Revisar procesos de redistribución de componentes del convenio según ajustes operacionales.  
**Fecha límite:** Septiembre de 2026.  
**Estado:** Pendiente.  
**Impacto tecnológico:** Los recursos del saldo ($18.157 millones) deben redistribuirse para incluir explícitamente el componente tecnológico ITS, que hoy no tiene asignación presupuestal definida en el convenio.

#### 4.5. Gestión de la demanda
**Compromiso:** Estructurar medidas para control de ilegalidad e informalidad en zonas de influencia del SETP una vez entre en operación.  
**Fecha límite:** Junio de 2026.  
**Impacto tecnológico:** El control de informalidad (mototaxismo) requiere sistemas de monitoreo, cámaras de video, botones de pánico y alertas en tiempo real — todos componentes del ITS que están en 0%.

*Fuentes: Ayuda de Memoria Reunión 15 abril 2026, secciones de compromisos y alertas; Informe Trimestral I-2026, Anexo 1, sección 2.2.*

---

## 5. IMPACTO Y RIESGOS DE LAS FALLAS TECNOLÓGICAS

### Si no se cierran los vacíos tecnológicos en los próximos 6 meses:

| Riesgo | Probabilidad | Impacto | Efecto |
|:---|:---|:---|:---|
| No se alcanza certificación 60% operación | Alta | 🔴 Crítico | Bloqueo de desembolsos nacionales ($15.827M pendientes). |
| Terminación anticipada del convenio | Media | 🔴 Crítico | Pérdida de cofinanciación, proyecto paralizado. |
| No hay recaudo electrónico | Alta | 🔴 Crítico | Operación con efectivo = evasión, costos altos, déficit tarifario. |
| Sin monitoreo de flota | Alta | 🔴 Crítico | No hay control de rutas, frecuencias, tiempos de recorrido. |
| Sin centro de control (CAMIS/CCO) | Alta | 🔴 Crítico | Respuesta a emergencias lenta, sin visibilidad operativa. |
| Incumplimiento Ley 2128/2021 | Media | 🟡 Mayor | Obligaciones de recaudo electrónico y transparencia no cumplidas. |
| Sostenibilidad financiera del operador | Alta | 🟡 Mayor | Déficit operativo sin datos para optimización. |
| Competitividad frente a informalidad | Alta | 🟡 Mayor | Mototaxismo sigue sin alternativa formal atractiva. |

---

## 6. PROPUESTA INNOVADATACO — PLAN DE TRABAJO DE ASESORÍA TECNOLÓGICA

### Objetivo
Estructurar el componente tecnológico ITS del SETP Sincelejo para que Metro Sabanas cuente en 4 semanas con:
1. Presupuesto ITS costeado y listo para licitación.
2. Arquitectura técnica de integración (SRC, SGCF, SIU, SST, CCO).
3. Especificaciones técnicas detalladas de 23 componentes.
4. Plan de implementación por fases (licitación → instalación → pruebas → operación).
5. Recomendaciones para redistribución de recursos del convenio.

### Alcance confirmado
**INCLUIDO:** Equipamiento ITS embarcado en 34 microbuses + Centro de Control y Operaciones (CCO) + red de conectividad celular/plan de datos + software SaaS + capacitación.  
**EXCLUIDO:** Paraderos inteligentes (ya construidos, 100%), infraestructura EtB (no aplica en Sincelejo), flota y operación (competencia de operador único).

### Fases del plan de asesoría

| Fase | Semana | Entregable | Actividad |
|:---|:---|:---|:---|
| **Fase 1: Diagnóstico y Costeo** | 1 | Presupuesto ITS costeado (23 componentes) | Estudio de mercado, cotización de hardware/software, definición de licencias SaaS, conectividad. |
| **Fase 2: Arquitectura e Integración** | 2 | Documento técnico de arquitectura ITS | Diseño de arquitectura (física, lógica, comunicaciones), diagramas de integración, APIs, flujo de datos recaudo. |
| **Fase 3: Especificaciones y Licitación** | 3 | Pliego de condiciones + EETT detalladas | Fichas técnicas de 23 componentes, requerimientos funcionales/no funcionales, indicadores KPI, criterios de aceptación. |
| **Fase 4: Roadmap y Recomendaciones** | 4 | Plan de implementación + Informe ejecutivo | Cronograma fases 0-4, matriz RACI, recomendaciones redistribución recursos, presentación a UMUS/Metro Sabanas. |

### Entregables específicos

| ID | Entregable | Formato | Destinatario |
|:---|:---|:---|:---|
| E4.1 | Presupuesto ITS costeado con valores unitarios y totales | Excel + DOCX | Metro Sabanas — Área Financiera |
| E4.2 | Arquitectura ITS completa (física, lógica, comunicaciones, servicios) | DOCX + Diagramas | Metro Sabanas — Área Técnica |
| E4.3 | Especificaciones técnicas detalladas de 23 componentes | DOCX (fichas individuales) | Metro Sabanas — Proceso Licitatorio |
| E4.4 | Pliego de condiciones y requerimientos funcionales/no funcionales | DOCX | Metro Sabanas — Área Jurídica/Contractual |
| E4.5 | Plan de implementación por fases (0-4) con hitos y RACI | DOCX + MS Project/Excel | Metro Sabanas + UMUS |
| E4.6 | Informe ejecutivo de recomendaciones para redistribución de recursos | DOCX + PPT | UMUS / MinTransporte |

### Valoración propuesta

| Concepto | Valor estimado | Nota |
|:---|:---|:---|
| Asesoría tecnológica ITS (4 semanas, 6 entregables) | **Por definir en propuesta formal** | A convenir con Metro Sabanas según complejidad final. |
| Referencia mercado: consultorías ITS similares en Colombia | $80M — $150M COP | Según alcance y número de componentes. |

---

## 7. CONCLUSIONES Y RECOMENDACIONES EJECUTIVAS

### Conclusiones

1. **El SETP Sincelejo tiene un cuello de botella tecnológico severo.** La infraestructura vial está avanzada, pero sin sistemas ITS no hay operación posible. Los 5 componentes en 0% (CAMIS, Gestión Flota, Recaudo, Patios, Vehículos) concentran $19.176 millones COP (57,6% del saldo).

2. **El presupuesto ITS es una plantilla vacía.** Tiene estructura pero no tiene precios. Esto bloquea cualquier proceso de licitación y adquisición. Es la primera acción que debe cerrarse.

3. **La UMUS no puede certificar 60% operación sin criterios tecnológicos claros.** Metro Sabanas necesita una propuesta de indicadores técnicos (qué % de implementación de ITS cuenta como "operación") para negociar con el Ministerio.

4. **El riesgo de terminación anticipada del convenio es real.** Los aportes municipio pendientes ($2.330M) y la falta de ejecución en componentes críticos ponen en jaque la cofinanciación nacional ($15.827M pendientes).

5. **INNOVADATACO puede estructurar el vacío tecnológico en 4 semanas.** Tenemos la metodología PM2, el análisis de 10 documentos fuente, la arquitectura de referencia de la APP Chía-Girardot, y la experiencia con proyectos de transporte público digital.

### Recomendaciones Ejecutivas

| # | Recomendación | Prioridad | Responsable sugerido | Fecha límite |
|---|:---|:---|:---|:---|
| 1 | **Costear el presupuesto ITS de 23 componentes** con valores unitarios de mercado y presentarlo a UMUS como requisito para licitación. | 🔴 Crítica | INNOVADATACO (Semana 1) | 15 jun 2026 |
| 2 | **Definir criterios técnicos de certificación 60% operación** que incluyan % de implementación del componente ITS. | 🔴 Crítica | Metro Sabanas + INNOVADATACO | 30 jun 2026 |
| 3 | **Redistribuir recursos del saldo ($18.157M)** para asignar explícitamente línea presupuestal al componente tecnológico ITS en el convenio. | 🔴 Crítica | Metro Sabanas + UMUS | 15 jul 2026 |
| 4 | **Gestionar desembolso de aportes municipio pendientes** ($2.330M) para evitar terminación anticipada. | 🟡 Alta | Municipio de Sincelejo | 30 jun 2026 |
| 5 | **Adelantar proceso licitatorio de flota y CAMIS/CCO** en paralelo al diseño ITS, dado que tienen los mayores saldos y tiempos de entrega. | 🟡 Alta | Metro Sabanas | 31 ago 2026 |
| 6 | **Contratar asesoría técnica especializada** (INNOVADATACO o similar) para cerrar arquitectura, especificaciones y plan de implementación ITS en 4 semanas. | 🟢 Media | Metro Sabanas | 15 jun 2026 |

---

## 8. FUENTES DOCUMENTALES CONSULTADAS

| # | Documento | Tipo | Institución / Autor | Hallazgo principal |
|---|-----------|------|---------------------|-------------------|
| 1 | `3._presupuesto_ITS_MetroSabanas.xlsx` | Excel — Plantilla | Metro Sabanas S.A.S. | Presupuesto ITS con 23 componentes, cantidades definidas (34 unidades), **valores en $0**. |
| 2 | `Ane1.pdf` | PDF — Anexo Técnico UMUS | Ministerio de Transporte — UMUS | Formato trimestral I-2026. Estado financiero y físico del proyecto. |
| 3 | `AYUDA_MEMORIA_REUNION_SEGUIMIENTO_15_ABRIL_2026.pdf` | PDF — Acta de reunión | UMUS | 93,4% desembolsos ejecutados. Alerta: aportes municipio pendientes = riesgo terminación anticipada. Infraestructura deteriorada. |
| 4 | `ENTREGABLE_5_ESPECIFICACIONES_AUTOBUSES.pdf` | PDF — Informe técnico | A4 Asociados S.A.S. — Ing. Boris Eduardo Barreto Alzate | Especificaciones técnicas microbuses (chasis, motor, carrocería). Normativa ambiental. |
| 5 | `ENTREGABLE_7_ESTRUCTURACION_FINANCIERA.pdf` | PDF — Informe financiero | A4 Asociados S.A.S. — Esp. Moisés Elías Angarita Pinto | Modelo financiero operador único y recaudo. CAPEX/OPEX, WACC, canasta de costo. |
| 6 | `Estudio_Economico_Sector_Transporte_Colombia.pdf` | PDF — Estudio macroeconómico | Carolina Malagón Robayo — Contrato PAS039-2025 | Transporte ~5% PIB. Costos logísticos ~14% PIB (vs 8-10% OCDE). Contexto sectorial. |
| 7 | `Inf1enero-mar_2026.pdf` | PDF — Informe trimestral | Metro Sabanas S.A.S. — Trimestre I-2026 | $172,45M ejecutados de $190,61M (91,97%). Saldo $18,16M. Metas físicas CAMIS 0%, Gestión Flota 0%, Patios 0%, Vehículos 0%. |
| 8 | `Informe_Integral_Estructuracion_SETP_Sincelejo.pdf` | PDF — Informe integral | Carolina Malagón Robayo — Contrato PAS039-2025 | Escenario 5 rutas actualizado septiembre 2025. Tarifa técnica. Estados financieros. |
| 9 | `JUSTIFICACION_REDUCCION_MS-130-2025.pdf` | PDF — Justificación técnica | Metro Sabanas S.A.S. — MS-130-2025 | Reducción oficial a **5 rutas / 34 buses / 7.670 pasajeros/día**. Base encuestas 2021. |
| 10 | `Modelo_financiero_5_rutas` | Excel — Modelo financiero | Metro Sabanas S.A.S. / A4 Asociados | Datos operativos y financieros para 5 rutas. Múltiples hojas de análisis. |

---

**Documento elaborado por:** ZEUS — Innovadataco  
**Responsable técnico:** Jelkin Zair Carrillo Franco, CEO Estratégico  
**Fecha de elaboración:** 30 de mayo de 2026  
**Clasificación:** CONFIDENCIAL — USO INTERNO INNOVADATACO / Presentación Metro Sabanas S.A.S. y UMUS  
**Versión:** 1.0  
**Repositorio:** Innovadataco/IDC_PROYECTOS/PROYECTO-004-2026-SETP-SINCELEJO/05-ENTREGABLES/E4-Resumen-Ejecutivo-Estado-Tecnologico/

---

*Este informe se basa en la revisión exhaustiva de 10 documentos oficiales del proyecto SETP Sincelejo y en el análisis comparativo con la arquitectura ITS de la APP Chía-Girardot (PROYECTO-001-2026-APP-CHIA-GIRARDOT).*  
*La información contenida es de uso exclusivo de INNOVADATACO y sus aliados estratégicos. No debe distribuirse sin autorización escrita del CEO.*
