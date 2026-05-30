# HALLAZGOS CRÍTICOS — PROCESO DE ADQUISICIÓN FLOTA + ITS SETP SINCELEJO
## Análisis de 3 documentos adicionales: Observaciones al Proceso, Recomendaciones, RFI Autobuses
## Fecha: 30 de mayo de 2026
## Clasificación: CONFIDENCIAL — USO INTERNO INNOVADATACO

---

## 🔴 HALLAZGO CRÍTICO HC-01: INCONSISTENCIA EN TECNOLOGÍA DE BUSES — DIESEL vs GAS vs ELÉCTRICO

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** El proceso define vehículos como **microbús Diesel Euro VI**, pero:
- En otros anexos solicita tecnología a **gas**
- La carta de elegibilidad afirma priorizar **buses eléctricos** (coherencia PNETP)
- El gerente de MetroSabanas comunicó al Ministerio que la tipología es **GNV (gas natural vehicular)** bajo Euro VI
- No hay análisis documentado de la elección tecnológica

**Impacto:** Riesgo de licitación fallida, reclamaciones de oferentes, incumplimiento normativo ambiental.

**Acción:** Unificar criterio tecnológico antes de publicar pliego. Documentar análisis de elección (total cost of ownership, disponibilidad combustible en Sincelejo, infraestructura mantenimiento).

---

## 🔴 HALLAZGO CRÍTICO HC-02: VALOR ITS INTEGRADO SIN SUSTENTACIÓN — $84.635 POR UNIDAD

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** En las cotizaciones de los 3 oferentes, el valor del **ITS integrado (SGCF+SRC+SIU) es EXACTAMENTE $84.635 pesos por unidad** — mismo valor idéntico en los tres, sin sustentación real de mercado.

**Anomalías:**
- No se explica a qué corresponde este valor
- No se establece si es compra o alquiler de equipos
- No hay justificación de los valores totales mostrados
- No se encuentran cotizaciones de equipos ITS individuales

**Impacto:** Probable **colusión** entre oferentes o **error de transcripción** en el proceso. Valor irrisorio para un sistema ITS completo (debería ser millones, no miles).

**Acción:** Investigar urgente. Solicitar cotizaciones detalladas desglosadas por componente. Verificar si $84.635 corresponde a valor mensual, por transacción, o es error.

---

## 🔴 HALLAZGO CRÍTICO HC-03: EQUIPOS ITS DIMENSIONADOS PARA 40 VEHÍCULOS — PROCESO ES PARA 17

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** Se dimensionan equipos ITS para **40 vehículos** (validadores, routers, torniquetes, cámaras) cuando el proceso de selección es para **17 microbuses** en fase inicial.

**Inconsistencia:** Documento de MetroSabanas menciona que "la adquisición de 17 microbuses corresponde a una fase inicial" y que "la incorporación progresiva del resto de vehículos estará sujeta a condiciones del modelo operacional y financiero, así como a disponibilidad de recursos."

**Impacto:** Sobredimensionamiento que encarece el proceso, reduce competencia, y no responde a realidad operativa. Los 23 buses restantes no tienen origen claro ni justificación.

**Acción:** Ajustar dimensionamiento ITS a 17 buses (fase 1) con opción de escalabilidad contratual para fases posteriores.

---

## 🔴 HALLAZGO CRÍTICO HC-04: ANEXO TÉCNICO ITS EXIGE CBT + ABT SIMULTÁNEOS — COMPLEJIDAD DESPROPORCIONADA

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** El Anexo Técnico ITS exige implementar **simultáneamente**:
- **CBT** (Card Based Ticketing, Mifare Plus SL3) — tarjeta con saldo almacenado
- **ABT** (Account Based Ticketing, HSM en nube) — cuenta en nube

**Estas dos arquitecturas responden a lógicas de operación distintas.** Su coexistencia desde el arranque genera complejidad técnica y de costos desproporcionada para un sistema de **17 buses** sin operador de recaudo definido, sin red de puntos de carga, sin cultura de pago electrónico en Sincelejo.

**Práctica estándar:** Comenzar con una sola arquitectura de recaudo y escalar hacia la segunda en fase posterior una vez el sistema tenga demanda estabilizada.

**Impacto:** Costos innecesarios, complejidad operativa, riesgo de fallas en arranque, reducción de oferentes que puedan cumplir ambas arquitecturas.

**Acción:** Simplificar a una arquitectura inicial (recomendado: CBT/Mifare por robustez offline). Dejar ABT como roadmap fase 2.

---

## 🔴 HALLAZGO CRÍTICO HC-05: EMV NIVEL 2 SIN ACUERDO BANCARIO — COSTO SIN BENEFICIO INMEDIATO

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** Anexo exige validadores certificados **EMV Nivel 1 y 2** (pago con tarjetas bancarias crédito/débito), pero:
- Esta funcionalidad **solo se activará cuando el ente gestor logre acuerdos comerciales con banco/franquicia adquiriente**
- Negociación **NO está iniciada** a fecha del proceso
- Certificación EMV Nivel 2 tiene **costo significativo de laboratorio por modelo de equipo**

**Impacto:** Hardware más caro sin garantía de uso en primeros años. Ciudad con dominio de efectivo informal no justifica esta exigencia inmediata.

**Acción:** Dejar EMV Nivel 2 como requisito deseable/fase 2. Exigir EMV Nivel 1 como base para futura activación.

---

## 🔴 HALLAZGO CRÍTICO HC-06: SERVIDOR HSM 300ms — REQUERIMIENTO NO CUMPLIBLE EN COBERTURA VARIABLE

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** Anexo incluye servidor HSM para validación en nube con **tiempo máximo de validación de 300 milisegundos**. En condiciones de operación real con cobertura celular variable en Sincelejo, este requerimiento puede no ser cumplible consistentemente.

**Inconsistencia:** El mismo documento reconoce la limitación señalando que "si es necesario se debe hibridar el proceso", **sin definir cómo**. No hay justificación para requerir arquitectura de esta complejidad para las proporciones del sistema.

**Impacto:** Requisito irreal que limita proveedores o genera incumplimiento contractual post-adjudicación.

**Acción:** Ajustar SLA de validación a 500-800ms con fallback offline. Definir claramente mecanismo de hibridación (validación local + sincronización diferida).

---

## 🔴 HALLAZGO CRÍTICO HC-07: SISTEMA ITS DIMENSIONADO PARA ESCALA MAYOR A LA OPERACIÓN REAL

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** De forma general, el sistema ITS está dimensionado para una escala significativamente mayor a la implementación inicial. La cantidad de dispositivos en vehículo, equipos en centro de control y demás componentes no responden a la realidad del sistema de transporte de 17 buses.

**Impacto:** Desbalance entre infraestructura tecnológica y operación real. Costos inflados, mantenimiento de sistemas subutilizados, dificultad para demostrar retorno de inversión.

**Acción:** Redimensionar todo el sistema ITS a escala de 17 buses con opción de escalabilidad modular contratual.

---

## 🟡 HALLAZGO MAYOR HM-01: PROCESO VEHÍCULO + ITS UNIFICADO RESTRINGE PLURALIDAD

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** La unificación del proceso vehículo + ITS en un solo contrato restringe la pluralidad de oferentes:
- Fabricantes de microbuses no son proveedores de ITS, y viceversa
- Ninguno de los dos grupos tiene capacidades integrales individualmente
- No hay mecanismo claro en pliegos sobre cómo verificar indicadores financieros para cada integrante del consorcio vs. consorcio como unidad

**Impacto:** Reducción de competencia, posible exclusión de fabricantes nacionales o proveedores ITS especializados, riesgo de adjudicación a consorcio sin capacidad real integrada.

**Acción:** Evaluar separar proceso en: (a) adquisición flota, (b) contrato ITS con integrador responsable. O diseñar pliego que permita consorcios con claridad de responsabilidades.

---

## 🟡 HALLAZGO MAYOR HM-02: INDICADORES FINANCIEROS INCLUYEN EMPRESAS FUERA DEL OBJETO

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** Indicadores financieros del estudio de sector incluyen empresas que **no corresponden al objeto a contratar**:
- ZERO RIESGOS S.A.S
- VRAE S.A.S
- GESTIONES S.A.S

Estas empresas no se identifican como ensambladoras, importadoras o comercializadoras de buses.

**Impacto:** Análisis financiero sesgado, posible exlusión de empresas reales del sector, riesgo de impugnación.

**Acción:** Revisar y ajustar estudio de sector. Incluir solo empresas con objeto social de comercialización, ensamblaje o importación de vehículos de transporte público.

---

## 🟡 HALLAZGO MAYOR HM-03: PONDERACIÓN TÉCNICA DESEQUILIBRADA — ITS PESA MÁS QUE EL VEHÍCULO

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:** Distribución de 1.000 puntos:
- Factor económico: 390
- Factor técnico: 500
- Industria nacional: 100
- Discapacidad: 10

Dentro del factor técnico (500):
- Desempeño energético vehículo: 150 pts
- Disponibilidad (tiempos entrega): 150 pts
- **Calidad ITS: 100 pts**
- **Experiencia sistemas transporte: 99 pts**

Los criterios tecnológicos pueden pesar hasta **40% del puntaje total**. Para una ciudad sin transporte público formal, la confiabilidad operativa del vehículo debería tener mayor peso.

**Impacto:** Favorece a grandes proveedores de ITS con muchos validadores/vehículos equipados, excluyendo operadores regionales con experiencia práctica en SETP.

**Acción:** Reequilibrar factores. Dar mayor peso a garantía extendida, disponibilidad repuestos región, tiempo respuesta mantenimiento, vida útil.

---

## 🟡 HALLAZGO MAYOR HM-04: UMBRAL PYMES DESACTUALIZADO — NO INCORPORA DECRETO 0287/2026

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:**
- Valor del umbral para PYMES está desactualizado
- No se han incorporado criterios diferenciales para MIPYME, emprendimientos de mujeres, emprendimientos de personas con discapacidad conforme al **Decreto 0287 de 2026**

**Impacto:** Posible vulneración de normativa vigente, exclusión de pequeños proveedores, riesgo de nulidad del proceso.

**Acción:** Actualizar umbral PYMES y criterios de inclusión conforme Decreto 0287/2026.

---

## 🟡 HALLAZGO MAYOR HM-05: ESTUDIO DE MERCADO INSUFICIENTE

**Documento:** `Observaciones_proceso_flota.docx`

**Problema:**
- Datos sin temporalidad unificada (mezcla 2022 y 2024)
- Solo 2 licitaciones consideradas para análisis de demanda
- No hay presupuesto desagregado con valor unitario de cada bus y componentes
- No se adjuntan cotizaciones reales, solo cuadro Excel
- Precios en Sincelejo mayores que otras ciudades para tipologías menores
- No se presenta análisis de elección de tecnología (Diesel vs Gas vs Eléctrico)

**Impacto:** Falta de base objetiva para fijar presupuesto y criterios de evaluación.

**Acción:** Fortalecer estudio de mercado con: cotizaciones desglosadas, análisis elección tecnología, datos actualizados 2025-2026, comparación interciudades, presupuesto desagregado vehículo + ITS por separado.

---

## 🟢 HALLAZGO POSITIVO HP-01: RFI DEFINE CLARAMENTE REQUISITOS DE HOMOLOGACIÓN

**Documento:** `RFI_Autobuses.pdf`

**Descripción:** El RFI solicita claramente:
- Ficha técnica de homologación del chasis (Ministerio de Transporte)
- Ficha técnica de homologación de la carrocería (Ministerio de Transporte)
- Ficha técnica del chasis suministrada por marca
- Ficha técnica de la carrocería suministrada por marca
- Plano en PDF del chasis

**Impacto:** Garantiza trazabilidad y cumplimiento normativo.

---

## 🟢 HALLAZGO POSITIVO HP-02: RECOMENDACIONES DEL PROYECTO SON CONSISTENTES

**Documento:** `Recomendaciones.docx`

**Descripción:** Recomendaciones estratificadas en corto, mediano y largo plazo:
- **Corto:** Organizar paraderos, personal idóneo, cultura ciudadana, terminar estación central, cumplir aportes municipio
- **Mediano:** Puesta en operación formal después de 15 años, integración empresarial, actualizar Plan Maestro Movilidad
- **Largo:** Migración progresiva flota eléctrica, infraestructura carga, integrar municipios cercanos

**Críticas constructivas:** No combatir mototaxismo sino restringir áreas del sistema, tarifa única sin excepciones, ampliar cobertura, nuevos liderazgos con capacidad institucional + legitimidad política + soporte técnico + participación ciudadana.

---

## 📊 SÍNTESIS DEL ESTADO DEL PROCESO DE ADQUISICIÓN

| Aspecto | Estado | Severidad |
|:---|:---|:---|
| Tecnología buses | Inconsistente (Diesel/Gas/Eléctrico) | 🔴 Crítico |
| Valor ITS | $84.635 idéntico en 3 oferentes — sin sustentación | 🔴 Crítico |
| Dimensionamiento ITS | 40 vehículos vs proceso 17 | 🔴 Crítico |
| Arquitectura recaudo | CBT + ABT simultáneos | 🔴 Crítico |
| EMV Nivel 2 | Sin acuerdo bancario, costo sin beneficio | 🔴 Crítico |
| HSM 300ms | Requerimiento irreal en cobertura variable | 🔴 Crítico |
| Escala ITS | Dimensionado para escala mayor a operación | 🔴 Crítico |
| Unificación proceso | Vehículo + ITS restringe pluralidad | 🟡 Mayor |
| Indicadores financieros | Empresas fuera del objeto | 🟡 Mayor |
| Ponderación técnica | ITS pesa 40%, más que vehículo | 🟡 Mayor |
| Umbral PYMES | Desactualizado, sin Decreto 0287/2026 | 🟡 Mayor |
| Estudio mercado | Sin cotizaciones reales, datos desactualizados | 🟡 Mayor |
| RFI homologación | Bien estructurado | 🟢 Positivo |
| Recomendaciones estratégicas | Consistentes y accionables | 🟢 Positivo |

---

## CONCLUSIÓN EJECUTIVA

El proceso de adquisición de flota + ITS del SETP Sincelejo (mayo 2026) presenta **7 hallazgos críticos y 6 mayores** que ponen en riesgo la viabilidad del proceso y la calidad del sistema tecnológico a implementar. Las inconsistencias van desde la definición tecnológica de los buses (Diesel/Gas/Eléctrico) hasta el dimensionamiento del ITS (40 vehículos cuando se compran 17, CBT+ABT simultáneos, EMV Nivel 2 sin acuerdo bancario, HSM 300ms irreal).

**Recomendación INNOVADATACO:** Antes de continuar con el proceso de adquisición, Metro Sabanas debe:
1. Unificar criterio tecnológico de flota con análisis de TCO
2. Corregir dimensionamiento ITS a 17 buses (fase 1) con escalabilidad modular
3. Simplificar arquitectura de recaudo a CBT inicial, ABT como fase 2
4. Postergar EMV Nivel 2 hasta tener acuerdo bancario
5. Ajustar SLA HSM a realidad de cobertura celular en Sincelejo
6. Separar o aclarar proceso vehículo vs ITS para no restringir pluralidad
7. Actualizar estudio de mercado con cotizaciones reales desglosadas
8. Reequilibrar ponderación técnica para dar más peso a confiabilidad vehículo
9. Actualizar umbrales PYMES conforme Decreto 0287/2026
10. Incluir en análisis financiero solo empresas del sector automotriz/transporte

---

*Documento elaborado por ZEUS — Innovadataco*
*Responsable técnico: Jelkin Zair Carrillo Franco, CEO Estratégico*
*Fecha de elaboración: 30 de mayo de 2026*
*Clasificación: CONFIDENCIAL — USO INTERNO*
*Repositorio: Innovadataco/IDC_PROYECTOS/PROYECTO-004-2026-SETP-SINCELEJO*
