# PROYECTO-004-SETP-SINCELEJO — ACTUALIZACIÓN POST-REVISIÓN DOCUMENTAL
## Fecha de actualización: 30 de mayo de 2026
## Documentos revisados (10 archivos)

---

## DOCUMENTOS PROCESADOS

| # | Archivo | Tipo | Hallazgos Clave |
|---|---------|------|-----------------|
| 1 | `3._presupuesto_ITS_MetroSabanas.xlsx` | Excel | Plantilla con TODOS los valores en **$0**. Estructura definida pero sin costear. 34 unidades de cada componente de abordo confirmadas. |
| 2 | `Ane1.pdf` | PDF (Anexo Técnico) | Formato UMUS trimestral I-2026. Estado financiero y físico del proyecto. |
| 3 | `AYUDA_MEMORIA_REUNION_SEGUIMIENTO_15_ABRIL_2026.pdf` | PDF | Reunión de seguimiento UMUS. **93.4% desembolsos ejecutados**. Alerta crítica: aportes municipio pendientes = riesgo terminación anticipada. Infraestructura deteriorada. |
| 4 | `ENTREGABLE_5_ESPECIFICACIONES_AUTOBUSES.pdf` | PDF | Especificaciones técnicas microbuses (chasis, motor, carrocería). Normativa ambiental y técnica detallada. |
| 5 | `ENTREGABLE_7_ESTRUCTURACION_FINANCIERA.pdf` | PDF | Modelo financiero operador único. CAPEX/OPEX, WACC, flujo de caja, canasta de costo. |
| 6 | `Estudio_Economico_Sector_Transporte_Colombia.pdf` | PDF | Contexto macroeconómico. Transporte ~5% PIB. Costos logísticos ~14% PIB (vs 8-10% OCDE). |
| 7 | `Inf1enero-mar_2026.pdf` | PDF | **Informe trimestral I-2026**. Datos oficiales de ejecución: $172.45M de $190.61M ejecutados (91.97%). Saldo: $18.16M. Metas físicas: CAMIS 0%, Gestión Flota 0%, Patios 0%, Vehículos 0%. |
| 8 | `Informe_Integral_Estructuracion_SETP_Sincelejo.pdf` | PDF | Informe financiero integral actualizado septiembre 2025. Escenario 5 rutas. Tarifa técnica. Estados financieros. |
| 9 | `JUSTIFICACION_REDUCCION_MS-130-2025.pdf` | PDF | **MS-130-2025**: Reducción oficial a **5 rutas / 34 buses / 7.670 pasajeros/día**. Justificación técnica basada en encuestas 2021. |
| 10 | `Modelo_financiero_5_rutas` | Excel | Modelo financiero con múltiples hojas. Datos de operación para 5 rutas. |

---

## HALLAZGOS CRÍTICOS IDENTIFICADOS (v2.0)

### 🔴 H-01: PRESUPUESTO ITS INCOMPLETO — VALORES EN $0
**Archivo:** `3._presupuesto_ITS_MetroSabanas.xlsx`
**Severidad:** Crítica
**Descripción:** La plantilla de presupuesto ITS contiene la estructura completa (34 unidades por componente, licencias SaaS, centro de control, etc.) pero **TODOS los valores unitarios y totales están en $0**. Esto indica que no se ha realizado el estudio de mercado ni la cotización de ninguno de los 23 componentes identificados.
**Impacto:** No es posible estimar el CAPEX del componente tecnológico. Bloquea planificación financiera y licitación.
**Acción recomendada:** Ejecutar estudio de mercado urgente para los 23 ítems del presupuesto ITS y diligenciar valores unitarios.

### 🔴 H-02: METAS FÍSICAS CRÍTICAS EN 0% DE EJECUCIÓN
**Archivo:** `Inf1enero-mar_2026.pdf` (Informe Trimestral I-2026 UMUS)
**Severidad:** Crítica
**Descripción:** Al corte marzo 2026, los componentes esenciales para la operación del SETP reportan **0% de avance físico**:
- **CAMIS (Centro de Atención y Monitoreo Integral):** 0%
- **Gestión de Flota y Control de Flota:** 0%
- **Patios y Talleres:** 0%
- **Predios Patios y Talleres:** 0%
- **Vehículos Nuevos:** 0%

**Impacto:** Sin estos componentes no hay operación posible. El sistema no puede iniciar.
**Acción recomendada:** Activar procesos licitatorios urgentes para estos componentes o reasignar recursos del saldo disponible ($18.16M).

### 🔴 H-03: SALDO FINANCIERO CONCENTRADO EN COMPONENTES SIN EJECUTAR
**Archivo:** `Inf1enero-mar_2026.pdf`
**Severidad:** Crítica
**Descripción:** Del saldo total de **$33.301M** (CONPES 3637-2010), los componentes con mayor saldo son precisamente los que están en 0% físico:

| Componente | Saldo (M$) | % del Saldo |
|-----------|-----------|-------------|
| Gestión de Flota y Control de Flota | 5.015 | 15% |
| Terminal/Estación Central | 6.386 | 19% |
| Vehículos Nuevos | 7.511 | 23% |
| Patios y Talleres | 4.613 | 14% |
| Puentes Peatonales | 3.551 | 11% |
| CAMIS | 1.875 | 6% |

**Impacto:** $28.951M (87% del saldo) está concentrado en componentes sin ejecución física. Riesgo de no alcanzar la operación.

### 🟡 H-04: APORTES MUNICIPIO EN RIESGO — TERMINACIÓN ANTICIPADA
**Archivo:** `AYUDA_MEMORIA_REUNION_15_ABRIL_2026.pdf`
**Severidad:** Mayor
**Descripción:** La persistencia de aportes territoriales pendientes constituye riesgo de terminación anticipada del convenio. El municipio informó inclusión en presupuesto 2026 como vigencias expiradas, pero falta desembolso efectivo.
**Impacto:** Puede bloquear giros nacionales y afectar hitos críticos.
**Acción recomendada:** Gestionar certificación presupuestal y soportes de desembolso ante UMUS antes de junio 2026.

### 🟡 H-05: DEFICIT OPERACIONAL — TARIFA TÉCNICA vs TARIFA USUARIO
**Archivo:** `AYUDA_MEMORIA_REUNION_15_ABRIL_2026.pdf` + `ENTREGABLE_7_ESTRUCTURACION_FINANCIERA.pdf`
**Severidad:** Mayor
**Descripción:** Identificada diferencia entre tarifa técnica y tarifa al usuario que genera déficit operacional. Artículo 182 Ley 2128/2021 requiere fuentes de financiación complementarias.
**Impacto:** Sostenibilidad financiera del operador en riesgo.
**Acción recomendada:** Actualizar modelo financiero y estructurar fuentes FET (Fondo de Estabilización Tarifaria).

### 🟡 H-06: CERTIFICACIÓN 60% OPERACIÓN SIN CRITERIOS CLAROS
**Archivo:** `AYUDA_MEMORIA_REUNION_15_ABRIL_2026.pdf`
**Severidad:** Mayor
**Descripción:** No existen criterios técnicos y operativos unificados para certificar el 60% de entrada en operación requerido para habilitar recursos.
**Impacto:** Puede generar interpretaciones divergentes entre MME, UMUS y ente gestor.
**Acción recomendada:** Estructurar y presentar certificación con indicadores claros (capacidad institucional, equipo operativo, condiciones de prestación).

### 🟢 H-07: INFRAESTRUCTURA VIAL Y PARADEROS AVANZADOS
**Archivo:** `Inf1enero-mar_2026.pdf`
**Severidad:** Menor (positivo)
**Descripción:** Infraestructura vial al 83% (46.69/56.09 km), paraderos 100% (232/232 unidades), sistema semafórico 100%.
**Impacto:** Componente físico vial está avanzado. No es bloqueo para operación.

### 🟢 H-08: NORMATIVA AMBIENTAL ALINEADA
**Archivo:** `ENTREGABLE_5_ESPECIFICACIONES_AUTOBUSES.pdf`
**Severidad:** Informativo
**Descripción:** Especificaciones incluyen cumplimiento Protocolo Kioto, ODS, Acuerdo París, Ley 1955/2019, Ley 1964/2019, Ley 1972/2019, Ley 2128/2021, CONPES 3260, 3550, 3344, 3943, 3934.
**Impacto:** Marco normativo ambiental y de transición energética definido.

---

## DATOS CONFIRMADOS PARA DOCUMENTO 1 (ARQUITECTURA ITS)

### Cantidades de Equipamiento (del presupuesto Excel)

**Equipo a bordo (por bus × 34 buses):**
- Validador Mifare con QR y Certificado EMV L1 y L2: 34 unidades
- Unidad lógica / Router: 34 unidades
- Consola industrial de conductor: 34 unidades
- Torniquete electromecánico: 34 unidades
- Cámara conteo pasajeros puerta trasera: 34 unidades
- DVR o procesador de imagen: 34 unidades
- Cámara de video: 68 unidades (2 por bus)
- Botón de Pánico: 34 unidades
- Cables e instalación: 34 juegos

**Centro de Control (CCO):**
- Televisores industriales 55" o superior: 4 unidades
- Matriz para arreglo de video: 1 unidad
- Computador pantalla doble: 2 unidades
- Computador inicialización: 2 unidades
- Antenas inicialización: 4 unidades
- Computador programación: 1 unidad
- Escritorio para centro de control: 5 unidades
- Silla giratoria ergonómica: 5 unidades
- UPS 5KVA: 1 unidad
- Switch Gigabit y rack de comunicaciones: 1 unidad
- Instalación eléctricas y de datos en CC: 1 juego

**Software y Servicios:**
- Licencia y configuración SaaS SRC: 1
- Licencia y configuración SaaS SGCF: 1
- Licencia y configuración SaaS SIU: 1
- Licencia y configuración SaaS SST: 1
- APIs de Interoperabilidad: 2
- APP móvil para información al usuario y pagos QR: 1
- Diseño de mapping: 1
- Tarjetas Mifare Desfire o Plus: 20.000 unidades
- Módulos SAM: 60 unidades
- Solución de seguridad SAM en nube y llaves: 1

**Servicios de Implementación:**
- Gerencia de proyecto: 1
- Alojamiento de aplicaciones y datos: 1
- Comunicaciones (plan de datos - buses y CCO): 34
- Capacitación y transferencia de conocimiento: 1

### Parámetros Operativos Confirmados
- **Rutas:** 5 (Cecar-Pioneros, La Vega-Argelia, Bogotá 2-Salvador, Satélite-Cabrero, Villa Katy-Bogotá 1)
- **Buses:** 34 microbuses
- **Demanda:** 7.670 pasajeros/día
- **Presupuesto máximo flota:** $3.793.756.953 COP (estudios 2023)
- **Convenio:** 06/08/2010, 7 otrosíes (último 31/12/2025)
- **Valor total proyecto:** $190.611.797.341
- **Ejecutado:** $172.454.005.112 (91.97%)
- **Saldo:** $18.157.792.229

---

## RECOMENDACIONES EJECUTIVAS POST-REVISIÓN

1. **Prioridad 1 — Costear presupuesto ITS:** El CAPEX tecnológico es incalculable con valores en $0. Se requiere cotización urgente de 23 componentes para licitación.

2. **Prioridad 2 — Activar componentes 0%:** Gestión de flota, CAMIS, patios/talleres y vehículos están en 0%. Requieren procesos licitatorios inmediatos o reasignación del saldo ($18.16M).

3. **Prioridad 3 — Gestionar aportes municipio:** Riesgo de terminación anticipada. Certificación presupuestal y desembolso efectivo antes de junio 2026.

4. **Prioridad 4 — Estructurar FET:** El déficit tarifa técnica/usuario requiere fuentes de estabilización para sostenibilidad operativa.

5. **Prioridad 5 — Definir criterios 60% operación:** Evitar bloqueos en la habilitación de recursos por falta de criterios claros.

---

*Documento generado por ZEUS — Innovadataco*
*Clasificación: CONFIDENCIAL — USO INTERNO*
*Repositorio: Innovadataco/IDC_PROYECTOS/PROYECTO-004-2026-SETP-SINCELEJO*
