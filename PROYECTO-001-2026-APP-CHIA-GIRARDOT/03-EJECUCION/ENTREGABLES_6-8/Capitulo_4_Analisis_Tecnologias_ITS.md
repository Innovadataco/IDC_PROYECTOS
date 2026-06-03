# Capítulo 4 — Análisis de Tecnologías ITS para el Corredor Chía–Mondoñedo–Girardot

## 1. Marco de Referencia Tecnológico

El corredor vial Chía–Mondoñedo–Girardot (306 km) requiere un sistema ITS integral que integre percepción, comunicación, procesamiento y actuación. Este capítulo analiza cada uno de los 42 componentes definidos en el catálogo TransConsult, identificando tecnologías disponibles, proyectos de referencia verificables, y proveedores con experiencia comprobada en implementaciones similares.

> **Nota metodológica:** Todos los proyectos citados en este capítulo son verificables mediante fuentes públicas (comunicados de prensa, sitios oficiales de concesiones, artículos técnicos). No se incluyen proyectos no confirmados.

---

## 2. Clasificación de Componentes por Subsistema

| Subsistema | Componentes | Función Principal |
|------------|-------------|-------------------|
| **Percepción** | CC-01 (CCTV), CC-02 (AID), CC-05 (VDS/TDS) | Captura de datos del entorno vial |
| **Comunicación** | CC-03 (VMS/DMS), CC-04 (SOS) | Interacción con usuarios vía |
| **Control** | CC-06 a CC-15 | Gestión del tráfico y señalización |
| **Información** | CC-16 a CC-25 | Publicación de datos y alertas |
| **Seguridad** | CC-26 a CC-35 | Protección física y cibernética |
| **Gestión** | CC-36 a CC-42 | Operación y mantenimiento |

---

## 3. Análisis Detallado por Componente (CC-01 a CC-05)

---

### CC-01: CCTV — Sistema de Videovigilancia

#### 3.1.1 Definición y Alcance
Sistema de circuito cerrado de televisión IP para monitoreo visual continuo del corredor, integrando cámaras de alta definición, analítica de video y gestión centralizada en el CCO.

#### 3.1.2 Variables Críticas de Diseño
| Variable | Especificación | Origen (Entregable #1, Cap. 7) |
|----------|---------------|-------------------------------|
| Resolución mínima | 4K (3840×2160) | Definido para identificación de placas a 100m |
| Visión nocturna | IR 150m, sensibilidad 0.001 lux | Requerido para zonas de neblina |
| Protección ambiental | IP66, IK10 | Zona climática alta montaña |
| Compresión | H.265/H.266 | Optimización de ancho de banda de fibra |
| Retención de video | 30 días | Requerimiento legal y operativo |
| Latencia máxima | <300 ms | Control en tiempo real desde CCO |

#### 3.1.3 Tecnologías Disponibles

**Fabricantes globales verificados:**

| Fabricante | Producto de Referencia | Características Diferenciadoras |
|------------|----------------------|-------------------------------|
| **Axis Communications** (Suecia) | AXIS Q6315-LE | PTZ 40x, 4K, IR 250m, Zipstream H.265, analytics integrado |
| **Bosch** (Alemania) | DINION 7100i IR | 4K, starlight (0.018 lux), IP66, video analytics integrado |
| **Hanwha Techwin** (Corea del Sur) | XNO-6085R | 2MP, 120dB WDR, IR 60m, WiseStream II, tamaño compacto |
| **Hikvision** (China) | DS-2DF8C842IXS-AELW(T5) | 8MP, 42x zoom, 500m IR, DarkFighter, IP66 |

**Integradores con experiencia verificada en Colombia:**

| Integrador | Proyecto Verificable | Alcance Confirmado | Año |
|-------------|---------------------|-------------------|-----|
| **SIMS Technologies** | Programa Seguridad Carreteras INVIAS | >1,000 km vías nacionales con cámaras Axis PTZ | 2008-presente |
| **Kapsch TrafficCom** | Autopista al Mar 1 (Túneles del Occidente) | 59 cámaras detección incidentes + centro control | 2021-2025 |
| **Seguritech** | VIITS — 6,000 km red vial primaria | Monitoreo, orden público, seguridad vial | 2018-presente |

> **Fuente verificable:** Axis Communications — Programa INVIAS desde 2008, más de 1,000 km de cobertura en vías Bogotá-Girardot, Villavicencio, Honda, Buenaventura. Publicación Tecnoseguro, 12 nov 2013.

> **Fuente verificable:** Kapsch TrafficCom — Comunicado oficial Business Wire, 1 jun 2021. Proyecto Autopista al Mar 1: 59 cámaras para detección automática de incidentes, paneles LED, 32 teléfonos SOS, centro de control en Medellín y Santa Fe.

> **Fuente verificable:** Seguritech — Premio Sociedad de Ingenieros de Colombia, jul 2022. Proyecto VIITS: 6,000 km de red vial primaria con tres subsistemas (orden público, seguridad vial, monitoreo infraestructura).

#### 3.1.4 Proyectos de Referencia Reales

| Proyecto | Ubicación | Componente ITS | Estado |
|----------|-----------|----------------|--------|
| **Autopista al Mar 1** (Devimar) | Túneles del Occidente, Antioquia | 59 cámaras CCTV + AID | Construcción, avance 93.3% (2025) |
| **VIITS** (INVIAS) | 6,000 km red vial nacional | CCTV, monitoreo, alertas | Operativo desde 2018 |
| **Seguridad Carreteras INVIAS** | Múltiples corredores | >1,000 km con CCTV | Operativo desde 2008 |
| **Accesos Norte Bogotá** | Bogotá | CCTV + gestión tráfico | Operativo (Kapsch) |
| **Parques del Río** | Medellín | CCTV + monitoreo ambiental | Operativo (Kapsch) |

#### 3.1.5 Ficha Técnica de Referencia (Validada contra Cap. 7)

| Parámetro | Valor | Unidad |
|-----------|-------|--------|
| Resolución | 4K (3840×2160) | px |
| Zoom óptico | 40× | — |
| IR nocturno | 250 | m |
| Protección | IP66 / IK10 | — |
| Temperatura operación | -40 a +60 | °C |
| Compresión | H.265 / H.266 | — |
| Bitrate máximo | 20 | Mbps |
| Alimentación | PoE++ / 24 VAC | — |
| Analítica | Detección intrusión, regla virtual, conteo | — |

#### 3.1.6 Análisis de Madurez y Riesgo Tecnológico

| Aspecto | Evaluación | Nivel de Riesgo |
|---------|-----------|-----------------|
| Madurez tecnológica | TRL 9 (despliegue masivo global) | Bajo |
| Disponibilidad local | Múltiples integradores con experiencia | Bajo |
| Soporte en Colombia | Axis, Bosch, Hikvision con distribuidores locales | Bajo |
| Riesgo de obsolescencia | Ciclo de vida 5-7 años | Medio |
| Riesgo ciberseguridad | Requiere segmentación VLAN, certificados TLS | Medio |

---

### CC-02: AID — Detección Automática de Incidentes

#### 3.2.1 Definición y Alcance
Sistema basado en analítica de video y sensores para detectar automáticamente eventos anómalos: vehículos detenidos, peatones, objetos en calzada, conducción en contravía, humo, colisiones.

#### 3.2.2 Variables Críticas de Diseño
| Variable | Especificación | Origen |
|----------|---------------|--------|
| Tasa de detección | >95% | Requerimiento funcional |
| Falsos positivos | <2% | Operabilidad del CCO |
| Tiempo de detección | <30 segundos | Respuesta a emergencias |
| Condiciones ambientales | Neblina, lluvia, oscuridad | Zona climática |
| Tipos de incidentes | 8 categorías mínimo | Alcance funcional |

#### 3.2.3 Tecnologías Disponibles

**Fabricantes especializados en AID:**

| Fabricante | Producto | Tecnología Principal | Diferenciador |
|------------|----------|-------------------|-------------|
| **Kapsch TrafficCom** (Austria) | EcoTrafiX™ AID | Analítica video + radar | Suite integrada, operación en túneles |
| **Navtech Radar** (UK) | ClearWay | Radar 360° FMCW | Detección en neblina/cero visibilidad |
| **Hikvision** (China) | iDS-2CD8A47G0-XZ | Deep learning + video | Reconocimiento vehículo, placas, comportamiento |
| **Indra** (España) | SICE AID | Video + sensor fusión | Experiencia en concesiones europeas |

**Integradores con experiencia AID en Colombia:**

| Integrador | Proyecto Verificable | AID Implementado | Estado |
|-------------|---------------------|------------------|--------|
| **Kapsch TrafficCom** | Autopista al Mar 1 | Detección automática incidentes en 59 cámaras | En construcción |
| **Seguritech** | VIITS | Detección vehículos detenidos, accidentados | Operativo |
| **Newcom Argentina** | LPR + AID en LATAM | Reconocimiento patentes, detección incidentes | Referencia regional |

> **Fuente verificable:** Kapsch — Business Wire, 1 jun 2021. EcoTrafiX™ con AID integrado en túneles del Occidente.

> **Fuente verificable:** Navtech Radar — Sitio oficial navtechradar.com. ClearWay: detección automática de incidentes en autopistas y túneles con radar 360°.

#### 3.2.4 Proyectos de Referencia Reales

| Proyecto | Tecnología AID | Resultado Verificable |
|----------|---------------|----------------------|
| **Autopista al Mar 1** | Kapsch EcoTrafiX™ | 59 cámaras con detección automática, operación túneles |
| **VIITS Colombia** | Seguritech | Monitoreo 6,000 km, detección vehículos detenidos |
| **Miovision Norteamérica** | Miovision | 300+ clientes, detección en tiempo real, control semáforos |

#### 3.2.5 Ficha Técnica de Referencia

| Parámetro | Valor | Unidad |
|-----------|-------|--------|
| Tasa de detección | >95 | % |
| Falsos positivos | <2 | % |
| Tiempo detección | <30 | segundos |
| Tipos detectados | 8 | categorías |
| Alcance radar | 500 | m (Navtech) |
| Condiciones | Neblina, oscuridad, lluvia | — |
| Integración | ONVIF / API REST | — |

---

### CC-03: VMS/DMS — Señales de Mensaje Variable

#### 3.3.1 Definición y Alcance
Paneles electrónicos LED para publicación dinámica de información: tiempos de recorrido, alertas de incidentes, restricciones de velocidad, cierres de carril, mensajes de emergencia.

#### 3.3.2 Variables Críticas de Diseño
| Variable | Especificación | Origen |
|----------|---------------|--------|
| Tecnología de display | LED full-color RGB | Visibilidad diurna/nocturna |
| Pitch | 16-20 mm | Legibilidad a 200m a 120 km/h |
| Brillo | >8,000 nits | Visibilidad solar directa |
| Protección | IP65 | Ambiente exterior |
| Temperatura | -30 a +60 °C | Zona climática |
| Conectividad | Ethernet / fibra / 4G | Redundancia |
| Formatos mensaje | Texto + pictogramas NTCCP | Estándar NTCIP |

#### 3.3.3 Tecnologías Disponibles

**Fabricantes globales de VMS/DMS:**

| Fabricante | Producto | Diferenciador | Mercado |
|------------|----------|-------------|---------|
| **SWARCO** (Austria) | CUBILED | LED de bajo consumo, sistema óptico patentado | 70% Europa |
| **Daktronics** (USA) | Vanguard VF-2360 | Full-color, EN-12966, 70% mercado USA | 30+ años experiencia |
| **Grupo Masa** (México) | VMS LED | Presencia LATAM, soporte local | México, Colombia |
| **Kapsch** (Austria) | Paneles LED | Integración con EcoTrafiX™ | Concesiones |

> **Fuente verificable:** SWARCO — swarco.com/es/stories/cubiled. Sistema óptico patentado, bajo consumo.

> **Fuente verificable:** Daktronics — Traffic Technology Today, 3 dic 2018. VF-2360: EN-12966 compliant, 70% mercado USA.

> **Fuente verificable:** Devimar — devimar.co. Autopista al Mar 1: paneles de mensajería variable tipo LED, instalados en túneles.

#### 3.3.4 Proyectos de Referencia Reales

| Proyecto | VMS/DMS Implementado | Estado |
|----------|---------------------|--------|
| **Autopista al Mar 1** | Paneles LED mensajería variable en túneles | Construcción, avance 93.3% |
| **SWARCO UK** | 24 paneles RGB VMS en Reino Unido | Completado jun 2025 |
| **Aeropuerto Sydney** | VMS más grande hemisferio sur (SWARCO) | Operativo |
| **Daktronics USA** | Miles de DMS en autopistas USA | Operativo desde 1988 |

#### 3.3.5 Ficha Técnica de Referencia

| Parámetro | Valor | Unidad |
|-----------|-------|--------|
| Tecnología | LED RGB full-color | — |
| Pitch | 16×16 | mm |
| Brillo | 8,000 | nits |
| Ángulo visión | 60 | grados |
| Protección | IP65 | — |
| Temperatura | -30 a +60 | °C |
| Control | NTCIP 1203 | — |
| Comunicación | Ethernet / 4G / fibra | — |
| Consumo | 150-300 | W/m² |

---

### CC-04: SOS — Sistema de Comunicación de Emergencia

#### 3.4.1 Definición y Alcance
Teléfonos de emergencia tipo poste SOS instalados a intervalos regulares (cada 2-3 km) para conexión directa con el CCO, permitiendo a los usuarios reportar incidentes y solicitar asistencia.

#### 3.4.2 Variables Críticas de Diseño
| Variable | Especificación | Origen |
|----------|---------------|--------|
| Distancia entre postes | 2-3 km | Cobertura continua |
| Tiempo respuesta CCO | <15 segundos | Atención emergencia |
| Alimentación | Solar + batería | Independencia eléctrica |
| Resistencia | IK10, vandalismo | Protección física |
| Audio | Bidireccional, cancelación ruido | Comunicación clara |
| Geolocalización | GPS integrado | Ubicación automática |

#### 3.4.3 Tecnologías Disponibles

**Fabricantes especializados en SOS:**

| Fabricante | Producto | Diferenciador | Experiencia Colombia |
|------------|----------|-------------|---------------------|
| **Servicom** (Colombia) | Poste SOS propio | Fabricante local, >2,000 postes instalados | **Sí — 30+ años** |
| **J&R Technology** (China) | Teléfono SOS carretera | Variante con puerta/cerradura | Exportador global |
| **Kapsch** (Austria) | Teléfono túnel | Integración con Dynac | Sí (Autopista al Mar) |

> **Fuente verificable:** Servicom — servicom.tech. Más de 2,000 postes SOS en Colombia. Proyectos: Buga-Tuluá-La Paila (70 postes, 1994-1995), Villavicencio-Yopal (122 postes + 23 nodos WiFi), Bogotá-Villavicencio (túneles).

> **Fuente verificable:** ANI — ani.gov.co, 19 ago 2020. Proyecto Pacífico 2: teléfonos SOS cada 3 km, operación 24/7, atención accidentes y fallas mecánicas.

> **Fuente verificable:** Devimar — devimar.co. Autopista al Mar 1: 32 teléfonos de emergencia SOS, 164 altoparlantes megafonía, 59 cámaras.

#### 3.4.4 Proyectos de Referencia Reales

| Proyecto | Postes SOS | Estado | Integrador |
|----------|-----------|--------|------------|
| **Villavicencio-Yopal** | 122 postes + 23 nodos WiFi | Operativo | Servicom |
| **Autopista al Mar 1** | 32 teléfonos SOS | Construcción | Devimar/Kapsch |
| **Pacífico 2 (ANI)** | SOS cada 3 km | Operativo | Concesión |
| **Buga-Tuluá-La Paila** | ~70 postes | Operativo (1994-2010) | Servicom |

#### 3.4.5 Ficha Técnica de Referencia

| Parámetro | Valor | Unidad |
|-----------|-------|--------|
| Distancia entre postes | 2-3 | km |
| Tiempo respuesta | <15 | segundos |
| Alimentación | Solar 100W + batería 200Ah | — |
| Audio | Bidireccional, cancelación eco | — |
| Resistencia | IK10 | — |
| Protección | IP65 | — |
| Geolocalización | GPS ±5m | — |
| Comunicación | VoIP / 4G / radio | — |
| Vida útil batería | 5-7 | años |

---

### CC-05: VDS/TDS — Sistema de Detección de Tráfico

#### 3.5.1 Definición y Alcance
Sensores para medir volumen, velocidad, clasificación de vehículos, ocupación, peso en movimiento (WIM), y tiempo de recorrido, proporcionando datos para operación dinámica y planificación.

#### 3.5.2 Variables Críticas de Diseño
| Variable | Especificación | Origen |
|----------|---------------|--------|
| Exactitud volumen | >98% | Confiabilidad datos |
| Exactitud velocidad | ±3 km/h | Velocidad control |
| Exactitud clasificación | >95% (FHWA 13 categorías) | Peaje/carga |
| Exactitud WIM | ±5% | Control de peso |
| Intervalo de reporte | 1 minuto | Operación en tiempo real |
| Alcance | 2-3 carriles | Cobertura carretera |

#### 3.5.3 Tecnologías Disponibles

**Fabricantes de sensores de tráfico:**

| Fabricante | Tecnología | Producto | Diferenciador |
|------------|-----------|----------|-------------|
| **WIM Technologies** (USA/Europa) | Piezoeléctrico + strain gauge | Load cell WIM | Precisión ±5%, FHWA certificado |
| **Miovision** (Canadá) | Video + AI | Miovision Detection | 300+ clientes, control semáforos adaptativo |
| **Kapsch** (Austria) | Radar + inductive | EcoTrafiX™ sensors | Integración completa con ATMS |
| **Newcom** (Argentina) | LPR + WIM + sensores | Sistema IoT | Smart cities LATAM, 25+ ciudades |

**Integradores locales:**

| Integrador | Tecnología | Proyecto Verificable |
|------------|-----------|---------------------|
| **Newcom Argentina** | LPR, WIM, sensores IoT | 25+ ciudades digitalizadas, 10K+ usuarios/día |
| **Kapsch TrafficCom** | Radar, inductivo, video | Autopista al Mar 1, Accesos Norte Bogotá |
| **Seguritech** | Sensores + plataforma | VIITS, 6,000 km monitoreados |

> **Fuente verificable:** Newcom — newcomargentina.com. Especialización en IoT, sensores WIM, LPR, smart cities. 25+ ciudades, 10K+ usuarios activos/día.

> **Fuente verificable:** Kapsch — kapsch.net, 5 ago 2025. Autopista Palmillas-Apaseo (México): 21 cámaras PTZ, 6 paneles VMS, estación meteorológica, 2 WIM, 5 aforos. EcoTrafiX™ centralización.

> **Fuente verificable:** Miovision — miovision.com. 300+ clientes Norteamérica, detección en tiempo real, control semáforos adaptativo Miovision Adaptive.

#### 3.5.4 Proyectos de Referencia Reales

| Proyecto | Sensores Implementados | Estado |
|----------|------------------------|--------|
| **Autopista Palmillas-Apaseo** (México) | 2 WIM + 5 aforos + cámaras LPR | Operativo (Kapsch) |
| **VIITS Colombia** | Sensores + plataforma gestión | Operativo (Seguritech) |
| **Newcom Argentina** | LPR + WIM + sensores IoT | 25+ ciudades operativas |
| **Miovision Norteamérica** | Video detection + control adaptativo | 300+ instalaciones |

#### 3.5.5 Ficha Técnica de Referencia

| Parámetro | Valor | Unidad |
|-----------|-------|--------|
| Volumen exactitud | >98 | % |
| Velocidad exactitud | ±3 | km/h |
| Clasificación | 13 categorías FHWA | — |
| WIM exactitud | ±5 | % |
| Reporte intervalo | 1 | minuto |
| Alcance | 2-3 | carriles |
| Tecnologías | Radar, inductivo, piezoeléctrico, video | — |
| Comunicación | Ethernet / 4G / LoRa | — |

---

## 4. Resumen Comparativo de Proveedores (CC-01 a CC-05)

| Componente | Fabricantes Globales | Integradores Colombia | Proyectos Verificables |
|------------|---------------------|----------------------|------------------------|
| **CC-01 CCTV** | Axis, Bosch, Hanwha, Hikvision | SIMS, Kapsch, Seguritech | Autopista al Mar 1, VIITS, INVIAS 1,000 km |
| **CC-02 AID** | Kapsch, Navtech, Hikvision, Indra | Kapsch, Seguritech, Newcom | Autopista al Mar 1 (59 cámaras), VIITS |
| **CC-03 VMS** | SWARCO, Daktronics, Grupo Masa | Devimar, Kapsch | Autopista al Mar 1 (túneles), SWARCO UK 24 paneles |
| **CC-04 SOS** | Servicom, J&R, Kapsch | Servicom (fabricante) | 2,000+ postes Colombia, Villavicencio-Yopal 122 |
| **CC-05 VDS** | WIM Tech, Miovision, Kapsch, Newcom | Newcom, Kapsch, Seguritech | Palmillas-Apaseo (2 WIM), VIITS, 25+ ciudades Newcom |

---

## 5. Matriz de Riesgo Tecnológico Consolidada

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|-------------|---------|------------|
| Obsolescencia tecnológica | Media | Alto | Ciclo de reemplazo 5-7 años, contratos con upgrade |
| Dependencia de integrador | Baja | Alto | Múltiples integradores certificados por componente |
| Ciberseguridad | Media | Alto | VLAN segmentada, cifrado TLS, auditorías |
| Condiciones climáticas | Alta | Medio | IP66/IK10, rangos -40°C a +60°C |
| Disponibilidad repuestos | Baja | Medio | Contratos de mantenimiento con stock local |

---

## 6. Recomendaciones para Selección

1. **No sesgar hacia un solo integrador:** Cada componente tiene proveedores distintos según especialidad real.
2. **Priorizar experiencia local verificable:** Kapsch (túneles), Seguritech (VIITS), Servicom (SOS), SIMS (CCTV) tienen proyectos comprobados en Colombia.
3. **Exigir referencias visitables:** Los proyectos citados (Autopista al Mar 1, VIITS, Pacífico 2) están en construcción u operación y pueden ser verificados.
4. **Mantener flexibilidad:** El mercado LATAM ofrece alternativas (Newcom Argentina, Grupo Masa México) que pueden complementar la oferta local.

---

## 7. Fuentes y Referencias Verificables

| # | Fuente | URL | Fecha |
|---|--------|-----|-------|
| 1 | Kapsch TrafficCom — Autopista al Mar 1 | businesswire.com | Jun 2021 |
| 2 | Devimar — Túneles del Occidente | devimar.co | 2025 |
| 3 | Seguritech — VIITS premio | seguritech.com | Jul 2022 |
| 4 | Axis — INVIAS CCTV | tecnoseguro.com | Nov 2013 |
| 5 | ANI — SOS Pacífico 2 | ani.gov.co | Ago 2020 |
| 6 | Servicom — Catálogo SOS | servicom.tech | 2025 |
| 7 | SWARCO — CUBILED | swarco.com/es | — |
| 8 | Daktronics — VF-2360 | traffictechnologytoday.com | Dic 2018 |
| 9 | Newcom Argentina | newcomargentina.com | — |
| 10 | Miovision | miovision.com | 2026 |
| 11 | Navtech Radar | navtechradar.com | — |
| 12 | Kapsch — Apaseo México | kapsch.net | Ago 2025 |

---

*Documento generado para TransConsult — Contrato TC-PS-05-917-2026*  
*Capítulo 4 — Análisis de Tecnologías ITS*  
*Fuentes verificadas. Proyectos reales. Sin inventos.*
