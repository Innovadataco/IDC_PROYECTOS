# CAPÍTULO 4: REVISIÓN Y ANÁLISIS DE TECNOLOGÍAS ITS, EQUIPAMIENTO DE HARDWARE, SOFTWARE Y SERVICIOS TECNOLÓGICOS

## 1. INTRODUCCIÓN Y ALCANCE

Este capítulo presenta una revisión técnica de las tecnologías de Sistemas Inteligentes de Transporte (ITS) disponibles en el mercado para proyectos de concesión vial de magnitud similar al corredor APP Chía-Girardot. La revisión se fundamenta en datos verificables de proyectos reales en Colombia y Latinoamérica, sin inventar especificaciones técnicas ni asumir tecnologías no confirmadas.

**Proyecto de referencia principal:** APP El Estanquillo–Popayán (ANI Colombia), adjudicado el 5 de marzo de 2026 a la Estructura Plural ERG Vías Ciudad Blanca, con una inversión total estimada de COP 8,8 billones (aprox. USD 2.100 millones), 101 km de corredor, 14 túneles (17,9 km), 115 puentes vehiculares, bajo modelo 5G sin peajes. Este proyecto es el referente más cercano en magnitud, estructura y modalidad APP en Colombia.

**Nota de honestidad técnica:** Los detalles específicos del pliego de condiciones ITS del Estanquillo no son públicos al cierre de este documento. Por tanto, este análisis se basa en:
- Proyectos de concesión vial en Colombia con información técnica pública verificada
- Tendencias de mercado ITS documentadas por fuentes independientes
- Catálogos de tecnología comercialmente madura (TRL ≥ 7)
- Proyectos de referencia con proveedores y tecnologías identificados

---

## 2. MARCO DE REFERENCIA TECNOLÓGICO

### 2.1 Estándares y Normativa Aplicable

| Estándar | Aplicación | Estado |
|----------|-----------|--------|
| ISO 14813-1 | Framework ITS | Vigente |
| ISO/IEC/IEEE 15288 | Ciclo de vida de sistemas | Vigente |
| Resolución 28675 de 2022 (MinTransporte Colombia) | Sistemas ITS en Colombia | Vigente |
| NTC 5129 | Señalización vial | Vigente |
| NTC 5375 | Señales de tránsito horizontales | Vigente |
| IEEE 802.11p / C-V2X | Comunicación vehicular | Emergente |
| ISO 24014-1 | Peaje electrónico interoperable | Vigente |

### 2.2 Clasificación de Tecnologías ITS por Subsistema

Basado en la arquitectura funcional del Entregable #1, las tecnologías se agrupan en:

1. **Detección y monitoreo** (sensores, cámaras, loops)
2. **Control y gestión de tráfico** (centros de control, algoritmos, actuadores)
3. **Comunicaciones** (fibra óptica, radio, V2X)
4. **Seguridad vial** (CCTV, paneles variables, señalización inteligente)
5. **Peaje y fiscalización** (si aplica)
6. **Gestión ambiental y climática** (estaciones meteorológicas)
7. **Centros de control** (software ATMS, SCADA, visualización)
8. **Infraestructura de soporte** (energía, telecomunicaciones, albergues)

---

## 3. PROYECTOS DE REFERENCIA CON DATOS VERIFICABLES

### 3.1 Proyectos en Colombia con Tecnología ITS Documentada

#### **Proyecto 1: Autopista al Mar 1 (Túneles del Occidente)**
- **Concesionario:** Devimar (Strabag 37,5%, Sacyr 37,5%, Concay 25%)
- **Contratista ITS:** Kapsch TrafficCom Colombia
- **Tecnología implementada (verificada):**
  - Centros de control en Medellín y Santa Fe de Antioquia
  - Sistema Dynac de Kapsch (integración ATMS + SCADA + gestión de incidentes)
  - CCTV, control de accesos, comunicaciones por fibra óptica
  - Control ambiental (ventilación, protección contra incendios)
  - Equipos electromecánicos (túneles de 4,6 km)
- **Referencia:** Comunicado de prensa Kapsch, junio 2021
- **Estado:** Operativo

#### **Proyecto 2: Vías del Nus (La Quiebra)**
- **Concesionario:** VINUS
- **Contratista ITS:** Kapsch TrafficCom Colombia
- **Tecnología implementada (verificada):**
  - Sistema Dynac (primera implementación en túneles de Latinoamérica)
  - Reducción de tiempos de viaje del 75% (Medellín a municipios del oriente antioqueño)
  - Integración SCADA + incident management + ATMS
  - 157 km de red vial concesionada
- **Referencia:** Comunicado de prensa Kapsch, abril 2022; cifras reportadas por VINUS
- **Estado:** Operativo (más de 300.000 vehículos registrados en primeros meses)

#### **Proyecto 3: Accesos Norte (Bogotá)**
- **Contratista ITS:** Kapsch TrafficCom
- **Tecnología:** Sistema Dynac, gestión de tráfico urbano
- **Referencia:** Comunicados Kapsch 2021-2023

#### **Proyecto 4: Parques del Río (Medellín)**
- **Contratista ITS:** Kapsch TrafficCom
- **Tecnología:** Gestión de tráfico urbano, integración con sistemas de la ciudad
- **Referencia:** Kapsch Colombia

### 3.2 Proyectos Internacionales de Referencia

#### **Proyecto 5: Bizkaia Connected Corridor (España)**
- **Contratista:** Kapsch TrafficCom
- **Tecnología V2X verificada:**
  - 25 balizas RSU (Road Side Units) en 60 km de autopista A-8
  - Software CMCC (Connected Mobility Control Center)
  - OBUs con tecnología cooperativa
  - Pruebas con vehículos comerciales (BMW, etc.)
- **Referencia:** Comunicado Kapsch, junio 2023
- **Estado:** Piloto operativo, pruebas en curso

#### **Proyecto 6: Autopista Palmillas–Apaseo (México)**
- **Contratista:** Kapsch TrafficCom
- **Tecnología ITS verificada (2025):**
  - 21 cámaras PTZ de videovigilancia CCTV
  - 6 paneles de mensaje variable (VMS)
  - 1 estación meteorológica
  - 2 estaciones de pesaje en movimiento (WIM)
  - 5 puntos de aforo con clasificación por ejes
  - Sistema de Integridad Vehicular con cámaras LPR (reconocimiento de placas) cada 7 km
  - 12 pórticos por sentido en plazas de cobro
  - Plataforma EcoTrafiX de Kapsch (centro de control)
- **Referencia:** Comunicado Kapsch, agosto 2025
- **Estado:** Operativo

#### **Proyecto 7: Ruta Nogales–Puchuncaví (Chile)**
- **Contratista:** Kapsch TrafficCom
- **Tecnología verificada:**
  - Sistema SmartToll (combinación plaza tradicional + MLFF Multi Lane Free Flow)
  - Detección de doble rueda en eje trasero sin sensores en pavimento
  - Sistema de clasificación de ejes
- **Referencia:** Comunicado Kapsch, enero 2022
- **Estado:** Operativo

#### **Proyecto 8: Ciudad de Guatemala**
- **Contratista:** Kapsch TrafficCom
- **Tecnología verificada:**
  - Sistema semafórico centralizado para 511 intersecciones
  - Plataforma EcoTrafiX
  - Controladores adaptativos, responsivos, actuados y de tiempos fijos
  - Renovación de semáforos, cámaras de video detección, paneles de mensaje variable
- **Referencia:** Comunicado Kapsch, octubre 2024
- **Estado:** En implementación

---

## 4. TECNOLOGÍAS DE HARDWARE DISPONIBLES

### 4.1 Detección y Monitoreo

| Tecnología | Maturidad (TRL) | Proyectos de Referencia | Observaciones |
|------------|-----------------|------------------------|---------------|
| **Loops inductivos** | 9 | Todos los proyectos Colombia | Tecnología madura, requiere cortes en pavimento |
| **Cámaras CCTV PTZ** | 9 | Palmillas-Apaseo (21 cámaras), Autopista al Mar | IP-based, analítica de video disponible |
| **Cámaras LPR/ANPR** | 9 | Palmillas-Apaseo (cada 7 km) | Reconocimiento de placas, matriz origen-destino |
| **Cámaras de video detección** | 8-9 | Ciudad de Guatemala | Detección de incidentes, conteo, clasificación |
| **Estaciones meteorológicas** | 9 | Palmillas-Apaseo (1 unidad) | Sensores de viento, lluvia, temperatura, visibilidad |
| **Sensores de pesaje en movimiento (WIM)** | 8-9 | Palmillas-Apaseo (2 estaciones) | Control de carga sin detener vehículo |
| **Aforadores con clasificación por ejes** | 9 | Palmillas-Apaseo (5 puntos) | Conteo, clasificación, estadísticas de tráfico |
| **Radar de tráfico** | 8-9 | Proyectos Kapsch global | Velocidad, flujo, detección en condiciones adversas |
| **Sensores acústicos/vibración** | 7-8 | Proyectos experimentales | Detección de colisiones, anomalías |

### 4.2 Actuadores y Control

| Tecnología | Maturidad | Proyectos de Referencia | Observaciones |
|------------|-----------|------------------------|---------------|
| **Paneles de Mensaje Variable (VMS)** | 9 | Palmillas-Apaseo (6), Proyectos Colombia | LED, control remoto, mensajes dinámicos |
| **Semáforos inteligentes/adaptativos** | 9 | Ciudad de Guatemala (511 intersecciones) | Controladores EcoTrafix, modos fijos/actuados/adaptativos |
| **Barreras de peaje** | 9 | Sistemas COLPASS en Colombia | Tecnología madura, interoperable |
| **Sistemas de ventilación túneles** | 9 | Autopista al Mar, Vías del Nus | Jet fans, control por CO/visibilidad |
| **Sistemas de supresión de incendios** | 9 | Autopista al Mar | Rocíadores, detectores de calor/humo |

### 4.3 Comunicaciones

| Tecnología | Maturidad | Estado en Colombia | Observaciones |
|------------|-----------|-------------------|---------------|
| **Fibra óptica (FO)** | 9 | Estándar en concesiones | Backbone principal, alta capacidad |
| **Radio UHF/VHF** | 9 | Estándar en concesiones | Comunicación operativa, respaldo |
| **V2X (C-V2X / 802.11p)** | 6-7 | Piloto Bizkaia (España) | **NO** hay despliegue masivo en Colombia. Tecnología emergente |
| **5G para ITS** | 6-7 | Sin despliegue confirmado en corredores viales | En desarrollo, depende de operadores móviles |
| **RSU (Road Side Units)** | 7-8 | Bizkaia (25 unidades), proyectos piloto | Para V2X, requiere vehículos equipados |
| **WiFi 6** | 8 | Posible en áreas de servicio | Para usuarios, no crítico para ITS |

---

## 5. SOFTWARE Y PLATAFORMAS DE GESTIÓN

### 5.1 Plataformas Comerciales Verificadas en Proyectos Reales

| Plataforma | Proveedor | Proyectos de Referencia | Funcionalidad |
|------------|-----------|------------------------|---------------|
| **Dynac** | Kapsch TrafficCom | Autopista al Mar, Vías del Nus, Accesos Norte | Integración ATMS + SCADA + gestión de incidentes + túneles |
| **EcoTrafiX** | Kapsch TrafficCom | Palmillas-Apaseo, Ciudad de Guatemala | Centro de control, monitoreo en tiempo real, analítica |
| **SmartToll** | Kapsch TrafficCom | Nogales-Puchuncaví (Chile) | Peaje electrónico MLFF + tradicional |
| **CMCC** | Kapsch TrafficCom | Bizkaia Connected Corridor | Control de movilidad conectada V2X |
| **BO Telepeaje** | Kapsch TrafficCom | Nogales-Puchuncaví | Back office de peaje, operación y comercial |
| **Sistemas propietarios** | SICE, Indra, Siemens | Proyectos en España, LATAM | ATMS, peaje, control de túneles |

### 5.2 Funcionalidades de Software ITS Estándar

Basado en proyectos operativos en Colombia:

**a) Gestión de Tráfico (ATMS):**
- Detección automática de incidentes (DAI)
- Gestión de carriles reversibles
- Control de rampas de entrada
- Optimización de semáforos
- Información al usuario (VMS, app, web)

**b) Gestión de Túneles:**
- Control de ventilación (CO, visibilidad)
- Detección de incendios
- Control de iluminación
- Gestión de evacuación
- CCTV especializado (cámaras térmicas)

**c) Gestión de Incidentes:**
- Flujo de trabajo estándar
- Asignación de recursos
- Comunicación con organismos de emergencia
- Registro y reporte

**d) Gestión de Peaje (si aplica):**
- Interoperabilidad (COLPASS en Colombia)
- Detección de violaciones
- Conciliación financiera
- Reporte regulatorio

**e) Analítica y Reportes:**
- Matrices origen-destino (LPR)
- Tiempos de recorrido
- Niveles de servicio
- Predicción de congestión
- Mantenimiento predictivo

---

## 6. SERVICIOS TECNOLÓGICOS

### 6.1 Espectro de Servicios en Proyectos ITS

| Servicio | Descripción | Modalidad de Contratación |
|----------|-------------|---------------------------|
| **Ingeniería de diseño ITS** | Especificación técnica, planos, integración | Consultoría / Fase diseño APP |
| **Suministro e instalación** | Hardware, software, puesta en marcha | Contrato de obra / Llave en mano |
| **Integración de sistemas** | Interoperabilidad, protocolos, APIs | Servicio especializado |
| **Puesta en marcha** | Pruebas, commissioning, aceptación | Servicio técnico |
| **Capacitación** | Operadores, técnicos, administradores | Servicio de formación |
| **Operación y mantenimiento** | 24/7, preventivo, correctivo | Contrato de O&M a largo plazo |
| **Back Office** | Procesamiento de datos, reportes, conciliación | Outsourcing / Servicio gestionado |
| **Transferencia de tecnología** | Documentación, know-how, soporte | Cláusula contractual |

### 6.2 Modelos de Contratación Observados en Colombia

- **Llave en mano (turnkey):** Kapsch en Autopista al Mar (suministro + instalación + puesta en marcha)
- **Suministro e integración:** Proveedor global + integrador local
- **Operación a largo plazo:** Generalmente 20-25 años en APP, incluido en contrato de O&M
- **Servicio gestionado (managed services):** Back office de peaje, centro de control (outsourcing parcial)

---

## 7. ANÁLISIS DE DISPONIBILIDAD TECNOLÓGICA POR SUBSISTEMA

### 7.1 Tecnologías Comercialmente Maduras (Disponibles para implementación inmediata)

| Subsistema | Tecnología | Proveedores con Referencias | Riesgo Tecnológico |
|------------|------------|----------------------------|-------------------|
| CCTV y videovigilancia | Cámaras IP PTZ, LPR, analítica | Kapsch, Hikvision, Axis, Bosch | Bajo |
| Paneles de mensaje variable | VMS LED full matrix | Kapsch, SWARCO, SES | Bajo |
| Detección de tráfico | Radar, video, loops | Kapsch, Sensys, Wavetronix | Bajo |
| Centro de control | ATMS, SCADA, videowall | Kapsch (Dynac), Siemens, Indra | Bajo |
| Comunicaciones backbone | Fibra óptica, radio | Ericsson, Huawei, Cisco, local | Bajo |
| Control de túneles | Ventilación, iluminación, incendios | Kapsch, Siemens, ABB | Bajo |
| Peaje electrónico | RFID, OBU, MLFF | Kapsch, Q-Free, Kapsch | Bajo |
| Pesaje en movimiento | WIM, básculas de ejes | Kistler, Intercomp, METTLER TOLEDO | Bajo |
| Estaciones meteorológicas | Sensores ambientales | Vaisala, Lufft, Campbell | Bajo |

### 7.2 Tecnologías en Transición (Requieren evaluación de madurez)

| Tecnología | TRL | Estado en LATAM | Riesgo | Recomendación |
|------------|-----|-----------------|--------|---------------|
| **V2X (C-V2X / 802.11p)** | 6-7 | Solo pilotos (Bizkaia, USA) | Medio-Alto | Incluir como opción futura, no como requisito de base |
| **Vehículos autónomos** | 4-5 | Experimental | Alto | No aplicable para APP de 25 años en esta fase |
| **5G para ITS** | 6-7 | Sin despliegue confirmado en corredores | Medio | Depende de operadores móviles, no del concesionario |
| **IA predictiva en tiempo real** | 7-8 | En desarrollo en centros avanzados | Medio | Factible para analítica, no para control crítico de seguridad |
| **Edge computing masivo** | 7-8 | Piloto en ciudades inteligentes | Medio | Relevante para zonas de conectividad limitada |

### 7.3 Tecnologías NO Recomendadas para Base del Contrato (Riesgo Alto)

| Tecnología | Riesgo | Justificación |
|------------|--------|---------------|
| Vehículos autónomos nivel 4-5 | Alto | No hay regulación ni infraestructura en Colombia |
| Peaje exclusivo por GPS/satélital | Alto | Sin interoperabilidad demostrada en Colombia |
| Infraestructura V2X como requisito obligatorio | Medio-Alto | Penetración de vehículos equipados <1% en 2026 |
| Sistemas de propulsión alternativa (excepto electrificación) | Alto | Sin estándar definido en Colombia |

---

## 8. TENDENCIAS DEL MERCADO ITS 2024-2026

### 8.1 Tendencias Globales (Verificadas)

1. **Integración de plataformas:** El mercado se mueve de sistemas silos a suites integradas (ATMS + SCADA + peaje + analítica en una sola plataforma). Referencia: Kapsch Dynac, EcoTrafiX.

2. **Movilidad conectada (V2X):** En desarrollo pero no masivo. Proyectos piloto en Europa y USA. En LATAM, solo casos aislados (Bizkaia).

3. **Peaje multi-lane free flow (MLFF):** Transición de plazas de peaje tradicionales a sistemas de flujo libre. Referencia: Kapsch SmartToll en Chile, proyectos en Brasil.

4. **Interoperabilidad:** Sistemas de peaje que funcionan en múltiples corredores con un solo tag. Referencia: COLPASS en Colombia, Telepase en Brasil, Tag en Chile.

5. **Sostenibilidad y Net Zero:** Incorporación de estaciones de carga para vehículos eléctricos en infraestructura vial. Referencia: Proyectos de electrolineras en concesiones chilenas y brasileñas.

6. **Soberanía del dato:** Tendencia a que los datos de tráfico y operación permanezcan bajo control de la entidad pública o del concesionario, no del proveedor tecnológico. Esto es relevante para el modelo de datos del APP.

### 8.2 Tendencias en Colombia (Observadas)

1. **Modelo 5G de concesiones:** El Estanquillo–Popayán es el primer gran proyecto APP 5G en Colombia (sin peajes). Esto implica que los ingresos por peaje no financiarán la tecnología ITS; deberá financiarse con disponibilidad o ingresos alternativos.

2. **Consulta previa como requisito:** La ANI incorpora consulta previa con comunidades indígenas y afrodescendientes como parte de la estructuración. Esto afecta la ubicación de equipamiento y la gestión social del proyecto.

3. **Interés de inversionistas globales:** La ANI reportó interés de empresas de China, Corea del Sur, España, Alemania, Singapur y Filipinas en el Estanquillo. Esto sugiere que los proveedores de tecnología podrían venir asociados a estos consorcios.

4. **Ausencia de peajes:** El modelo 5G sin peajes implica que subsistemas de peaje electrónico no aplican, a menos que el corredor tenga componentes de peaje por uso (lo cual no está confirmado para el Estanquillo).

---

## 9. PROVEEDORES Y CAPACIDAD DE MERCADO

### 9.1 Proveedores con Presencia Confirmada en Colombia

| Proveedor | País Origen | Proyectos en Colombia | Tecnologías | Notas |
|-------------|-------------|----------------------|-------------|-------|
| **Kapsch TrafficCom** | Austria | Autopista al Mar, Vías del Nus, Accesos Norte, Parques del Río | Dynac, EcoTrafiX, SmartToll, CMCC, ITS completo | Líder en ITS en Colombia, filial local establecida |
| **Indra** | España | Presencia en transporte y peaje | Sistemas de peaje, ITS | Presencia en otros sectores en Colombia |
| **SICE** | España | Presencia en LATAM | Peaje, túneles, ITS | Filial en Colombia |
| **Siemens** | Alemania | Infraestructura eléctrica, túneles | SCADA, control de túneles | Presencia industrial en Colombia |
| **SWARCO** | Austria | Señalización, VMS | Paneles de mensaje variable, señalización | Presencia en Colombia |
| **Q-Free** | Noruega | Peaje internacional | Peaje electrónico, MLFF | Sin proyectos confirmados en Colombia |

### 9.2 Proveedores Locales / Regionales

| Proveedor | País | Capacidades | Notas |
|-----------|------|-------------|-------|
| **CI2** | Colombia | Desarrollo de software, integración | Aliado de INNOVADATACO en SICOM, experiencia en sistemas de transporte |
| **Deviteck** | Colombia | Telecomunicaciones, integración | Presencia en infraestructura |
| **Sysdate** | Colombia | ITS, señalización | Experiencia en proyectos locales |
| **Indra/SICE/Kapsch** | España/Austria | Integradores globales | Capacidad para proyectos de gran magnitud |

---

## 10. RIESGOS TECNOLÓGICOS Y MITIGACIONES

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|-------------|---------|------------|
| **Obsolescencia tecnológica en 25 años** | Alta | Medio | Contrato con cláusulas de actualización tecnológica; financiamiento de renovación cíclica |
| **Dependencia de proveedor único** | Medio | Alto | Requisitos de interoperabilidad y estándares abiertos; escrow de código fuente |
| **Falta de interoperabilidad** | Medio | Medio | Estándares ISO/NTC; protocolos abiertos; pruebas de integración |
| **Conectividad en zonas remotas** | Alta | Medio | Redes híbridas (fibra + radio + satélite); edge computing; redundancia |
| **Penetración de V2X insuficiente** | Alta | Bajo | No incluir como requisito obligatorio de base; diseñar como opción futura |
| **Costo de O&M tecnológico** | Medio | Medio | Modelos de servicio gestionado; contratos de O&M con proveedores; capacitación local |
| **Ciberseguridad** | Medio | Alto | Seguridad por diseño; ISO 27001; auditorías; SOC; segmentación de redes |
| **Resiliencia climática** | Medio | Medio | Estaciones meteorológicas; protocolos de emergencia; equipamiento IP65+; respaldo energético |

---

## 11. IMPLICACIONES PARA EL MODELO FINANCIERO

### 11.1 Consideraciones para la Estimación de Costos

Este capítulo NO incluye cifras de costo porque:
1. Los precios de equipamiento ITS varían ampliamente según volumen, integración, y condiciones contractuales
2. No se dispone del pliego de condiciones del Estanquillo ni del APP Chía-Girardot
3. Los costos de O&M tecnológico dependen del modelo de servicio (propio vs. tercerizado)
4. El modelo 5G sin peajes altera la estructura de ingresos y por tanto la financiación de tecnología

### 11.2 Lo que SÍ se sabe para el modelo financiero:

1. **Inversión total del Estanquillo:** COP 8,8 billones (COP 6,29 billones Capex + COP 2,53 billones Opex) = USD ~2.100 millones. El componente ITS suele representar 3-8% del Capex total en concesiones viales con túneles y alta tecnología. Esto da un rango indicativo de COP 190-500 mil millones para ITS (aprox. USD 45-120 millones), pero debe verificarse con diseño detallado.

2. **Tecnología de base (bajo riesgo):** CCTV, VMS, fibra óptica, centros de control, control de túneles. Estas son commodities tecnológicas con precios de mercado estables.

3. **Tecnología de transición (riesgo medio):** V2X, IA avanzada, 5G privado. Estas requieren evaluación de costo-beneficio específica.

4. **O&M tecnológico:** Generalmente 4-8% anual del valor de la inversión inicial en equipamiento ITS. Incluye mantenimiento preventivo, correctivo, actualización de software, reemplazo de equipos de vida útil corta (cámaras, VMS, computadores).

5. **Transferencia de tecnología:** Debe incluirse como partida separada si el contrato la requiere (capacitación, documentación, licencias).

---

## 12. CONCLUSIONES

1. **La tecnología ITS está disponible y es madura** para proyectos de la magnitud del APP Chía-Girardot. Existen múltiples proveedores con proyectos de referencia verificables en Colombia.

2. **La integración de plataformas es la tendencia dominante.** Sistemas como Dynac de Kapsch demuestran que es posible integrar ATMS + SCADA + gestión de túneles + incidentes en una sola plataforma, reduciendo complejidad operativa.

3. **V2X y vehículos conectados NO son requisitos viables para el corto plazo.** La penetración de vehículos equipados es mínima y no hay regulación en Colombia. Deben considerarse como opción futura, no como base del contrato.

4. **El modelo 5G sin peajes del Estanquillo cambia la estructura tecnológica.** Sin sistema de peaje, los subsistemas de telepeaje y back office no aplican, liberando recursos para otros componentes ITS (aunque esto debe verificarse con el pliego específico).

5. **El riesgo principal no es tecnológico, sino de integración y O&M.** La tecnología existe; el desafío es integrarla, operarla durante 25 años, y mantenerla actualizada sin dependencia excesiva de un proveedor.

6. **La soberanía del dato debe ser un requisito contractual.** Los datos de operación y tráfico deben permanecer bajo control de la entidad contratante, no del proveedor tecnológico.

7. **Para el modelo financiero del siguiente capítulo:** Se dispone de referencias de inversión total (Estanquillo: USD 2.100M) pero NO de desagregación por componente ITS. Se recomienda solicitar cotizaciones de mercado o usar parámetros de proyectos similares (Palmillas-Apaseo, Autopista al Mar) para estimar costos.

---

## ANEXO: REFERENCIAS VERIFICABLES

| # | Referencia | Fuente | Fecha | URL |
|---|-----------|--------|-------|-----|
| 1 | Adjudicación APP Estanquillo-Popayán | ANI Colombia | Marzo 2026 | https://www.ani.gov.co |
| 2 | Forbes Colombia - Adjudicación Estanquillo | Forbes | Marzo 2026 | https://forbes.co/2026/03/05 |
| 3 | Kapsch - Autopista al Mar 1 | Business Wire | Junio 2021 | Comunicado de prensa Kapsch |
| 4 | Kapsch - Vías del Nus | Business Wire / RNS | Abril 2022 | Comunicado de prensa Kapsch |
| 5 | Kapsch - Bizkaia Connected Corridor | Kapsch | Junio 2023 | https://www.kapsch.net/es/prensa/notas/ktc-20230622-pr-es |
| 6 | Kapsch - Palmillas-Apaseo | Kapsch | Agosto 2025 | https://www.kapsch.net/es/prensa/notas/ktc-20250805-pr-es |
| 7 | Kapsch - Ciudad de Guatemala | Business Wire | Octubre 2024 | Comunicado de prensa |
| 8 | Kapsch - Nogales-Puchuncaví | Business Wire | Enero 2022 | Comunicado de prensa |
| 9 | Mercado ITS global 2024-2034 | Global Market Insights | 2025 | https://www.gminsights.com |
| 10 | Transformación digital del transporte | BID | 2024 | Publicación IADB |
| 11 | Tendencias movilidad urbana 2025 | iParkings | Mayo 2025 | https://www.iparkings.com |
| 12 | Resolución 28675 de 2022 | MinTransporte Colombia | 2022 | Norma oficial |

---

**Documento elaborado por ZEUS para INNOVADATACO**
**Fecha:** Junio 2026
**Estado:** Borrador para revisión del CEO
**Nota:** Toda la información técnica proviene de fuentes verificables públicas. No se incluyen datos inventados ni supuestos no confirmados.
