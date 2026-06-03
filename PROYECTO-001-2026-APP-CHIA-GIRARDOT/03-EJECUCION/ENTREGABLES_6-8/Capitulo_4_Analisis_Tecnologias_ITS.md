# CAPÍTULO 4: REVISIÓN Y ANÁLISIS DE TECNOLOGÍAS ITS, EQUIPAMIENTO DE HARDWARE, SOFTWARE Y SERVICIOS TECNOLÓGICOS

---

## 4.1. MARCO CONCEPTUAL

### 4.1.1. Propósito del Capítulo

El presente capítulo constituye el eje analítico de la propuesta de despliegue de Sistemas Inteligentes de Transporte (ITS) para el corredor vial Chía–Mondoñedo–Girardot, en cumplimiento de los términos de referencia del contrato TC-PS-05-917-2026. Su objetivo es establecer, con rigor técnico y fundamento empírico, el universo de tecnologías, equipos de hardware, plataformas de software y servicios conectados disponibles en el mercado global, regional y nacional, para dar cumplimiento a los nueve servicios estratégicos y 114 funciones técnicas definidos en el Capítulo 2.

Este análisis no se limita a la enumeración de fabricantes; busca, de manera estructurada, relacionar cada tecnología con el componente de corredor (CC) correspondiente, evaluar su madurez, interoperabilidad, soporte local y adecuación al contexto operativo colombiano, y finalmente recomendar las soluciones más aptas para ser desplegadas en la infraestructura objeto de concesión.

### 4.1.2. Alcance del Análisis

El alcance de la revisión abarca los 42 Componentes de Corredor (CC) identificados en el Catálogo Oficial TransConsult (CC-TRANSCONSULT-2026), distribuidos en los siguientes grupos funcionales:

1. **Sistemas de Gestión de Tráfico y Seguridad Vial**: CCTV, AID, VMS, SOS, radares, ALPR, sensores.
2. **Sistemas de Peaje y Control de Acceso**: ETC, WIM, sistemas de cobro.
3. **Sistemas de Monitoreo de Infraestructura**: Geotécnico, estructural, hídrico, ambiental.
4. **Sistemas de Comunicaciones y Red**: Fibra óptica, radio, satelital, V2X, gateways.
5. **Sistemas de Control Central**: CCO, SCADA, digital twin, analítica de datos.
6. **Sistemas de Emergencia y Resiliencia**: Detección de incendios, respaldo energético, drones.
7. **Sistemas de Información al Usuario**: Apps, SMS, web, redes sociales.
8. **Sistemas de Gestión Ambiental y Energética**: Calidad del aire, paneles solares, ITS verde.
9. **Sistemas de Ciberseguridad y Datos**: Seguridad perimetral, cifrado, gobernanza de datos.

### 4.1.3. Metodología de Análisis

La metodología adoptada para la revisión de tecnologías se estructura en cinco fases secuenciales:

**Fase I: Delimitación del Componente (CC)**
- Definición del propósito funcional del componente según el Capítulo 7 del Entregable 1.
- Identificación de variables críticas: cobertura, precisión, latencia, interoperabilidad, ciclo de vida.

**Fase II: Estado del Arte y Revisión Tecnológica**
- Consulta de bases de datos técnicas, catálogos de fabricantes, informes de mercado y experiencias en corredores similares.
- Fuentes principales: ITS World Congress, PIARC, AASHTO, normas ISO 14813-1, NTCIP, IEEE 1512, experiencias en Ruta del Sol, Autopista al Mar, Vías del Nus.

**Fase III: Identificación de Proveedores y Verificación de Ofertas**
- Clasificación por origen geográfico: Internacional (Europa, Asia, Norteamérica), LATAM (México, Brasil, Chile, Perú, Argentina) y Nacional (Colombia).
- Verificación de existencia de oficinas comerciales, soporte técnico, certificaciones y casos de implementación en Colombia o en corredores con características similares.

**Fase IV: Análisis Comparativo Técnico-Económico**
- Evaluación matricial de cada solución en criterios: madurez tecnológica, costo total de propiedad (TCO), cumplimiento normativo, escalabilidad, soporte local, interoperabilidad con la Arquitectura de Referencia definida en el Capítulo 3.

**Fase V: Recomendación de Adopción**
- Selección de la solución óptima por componente, con justificación técnica y contractual.
- Identificación de alternativas viables y riesgos de dependencia tecnológica.

### 4.1.4. Criterios de Evaluación

| Criterio | Peso | Descripción |
|----------|------|-------------|
| Madurez Tecnológica | 25% | TRL ≥ 7, despliegue probado en carreteras de peaje 5G |
| Interoperabilidad | 20% | Compatibilidad con NTCIP, ISO 14813-1, Arquitectura de Referencia del Capítulo 3 |
| Soporte Local | 20% | Presencia en Colombia, contratos de mantenimiento, repuesto en 24-48h |
| Costo Total de Propiedad (TCO) | 20% | CAPEX + OPEX 10 años, incluyendo mantenimiento, licencias, energía |
| Cumplimiento Normativo | 15% | Certificaciones ISO 9001, ISO 27001, homologación MinTransporte |

---

## 4.2. FICHA TÉCNICA Y ANÁLISIS DE COMPONENTES DE CAMPO

---

### 4.2.1. CC-01: CCTV — SISTEMA DE VIDEOVIGILANCIA

#### 4.2.1.1. Descripción y Función del Componente

El componente CC-01, CCTV (Circuito Cerrado de Televisión), constituye la capa visual de la infraestructura ITS. Su función primordial es capturar, transmitir, almacenar y procesar imágenes de video en tiempo real, permitiendo a los operadores del Centro de Control de Operaciones (CCO) observar el estado de la vía, detectar incidentes, verificar condiciones meteorológicas y documentar eventos para investigaciones posteriores.

Según la definición del Capítulo 7 del Entregable 1, el CCTV es un sistema de **"Videovigilancia de Tráfico"** que incluye cámaras fijas, domos motorizados (PTZ), cámaras térmicas, analíticas de video integradas y la red de transmisión que conecta estos dispositivos con el CCO. El propósito es proveer **"visibilidad situacional continua de la infraestructura vial"**.

#### 4.2.1.2. Variables Críticas de Diseño

| Variable | Especificación | Justificación |
|----------|---------------|---------------|
| Resolución | Mínimo 4K (8 MP) para cámaras fijas; 2K (5 MP) para PTZ | Identificación de placas y detalles a 150-200 m |
| Tasa de Frames | 30 fps mínimo, preferible 60 fps en zonas críticas | Captura fluida de incidentes en movimiento |
| Rango Dinámico | WDR ≥ 120 dB | Manejo de condiciones de contraste extremo (túneles, amanecer) |
| Visión Nocturna | IR de 150-200 m o cámaras térmicas | Cobertura 24/7 en tramos sin iluminación |
| Protección Ambiental | IP66/IP67, IK10 | Resistencia a polvo, agua, vandalismo |
| Codificación | H.265+/H.266 | Reducción de ancho de banda y almacenamiento |
| Analítica Integrada | Detección de detenciones, flujo contrario, peatones, basura, humo | Habilitar AID (CC-02) de forma distribuida |
| Transmisión | Fibra óptica + PoE++ | Garantía de latencia < 150 ms al CCO |

#### 4.2.1.3. Ficha Técnica de Referencia

| Parámetro | Valor |
|-----------|-------|
| Código | CC-01 |
| Nombre | Sistema de Videovigilancia (CCTV) |
| Tipo | Hardware de campo + Software de gestión de video (VMS) |
| Subsistema | Gestión de Tráfico y Seguridad Vial |
| Función Principal | Videovigilancia continua, detección visual de incidentes, apoyo a la gestión de tráfico |
| Campos de Aplicación | Todos los tramos (túneles, puentes, urbanos, rurales) |
| Variables Medidas | Imágenes de video, metadatos de analítica (flujo, detenciones, clasificación de vehículos) |
| Ciclo de Vida Esperado | 7-10 años (cámaras); 15 años (infraestructura de montaje) |
| Normativa Aplicable | ISO 14813-1, NTCIP 1205, IEEE 802.3bt (PoE++), ONVIF Profile S/G/T |

---

#### 4.2.1.4. Referencias del Mercado: Proveedores y Soluciones

A continuación se presentan los proveedores identificados, verificados y clasificados según su origen geográfico, cumpliendo con los criterios de información pública, verificabilidad de fuentes y neutralidad analítica. Se priorizan empresas con presencia documentada en Colombia y casos de implementación verificables en corredores viales o proyectos de infraestructura nacional.

---

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Kapsch TrafficCom AG** | Austria | Viena | ITS, Tolling, Traffic Management | **EcoTrafiX™ Video** — Plataforma de gestión de video integrada con ATMS, soporta miles de cámaras IP, analítica de video, videowall. | Palmillas-Apaseo Highway, México. 21 cámaras de tráfico + sistema de integridad vehicular con LPR. | 2025 | https://www.kapsch.net/en/press/releases/ktc-20250805-pr-en |
| 2 | **Siemens AG** | Alemania | Múnich | Movilidad, Infraestructura, Digital Industries | **Siemens Xcelerator for Mobility** — Incluye cámaras de red, VMS, integración con SCADA y sistema de control de tráfico. | Proyectos de movilidad en Bogotá (Accesos Norte) y múltiples corredores LATAM. | 2024 | https://www.siemens.com/global/en.html |
| 3 | **Hikvision** | China | Hangzhou | IoT, Seguridad Electrónica, ITS | **Sistema de Tráfico Inteligente (ITS)** — Cámaras de control de puntos de verificación, fusión radar+video, reconocimiento de matrículas impulsado por IA, AID integrado, tecnología DarkFighter 2.0 para baja iluminación. | Universidad Nacional de Colombia — videovigilancia con 900+ cámaras, control de acceso y LPR. | 2019 | https://www.hikvision.com/es-co/ |

---

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, Seguridad Vial, Monitoreo | **VIITS — Vías Inteligentes** — Sistema de modernización vial con 6,000 km de red primaria, cámaras de atención de incidentes, Centro de Control. | Proyecto ITS-VIITS para INVIAS, 6,000 km de carreteras nacionales. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |

---

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración de sistemas, ITS, Tecnología | Consultoría e integración de sistemas inteligentes de transporte, infraestructura tecnológica para corredores viales. | Proyectos de integración tecnológica en infraestructura de transporte en Colombia. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, ITS, Seguridad Electrónica | Diseño e implementación de sistemas de videovigilancia, control de acceso, redes y soluciones ITS. | Proyectos de videovigilancia y control en infraestructura de transporte en Colombia. | 2024 | https://www.deviteck.com.co |
| 3 | **SIT Ltda. — Sistemas Inteligentes de Transporte** | Colombia | Chía, Cundinamarca | ITS, Simulación de Tráfico, Movilidad | Distribuidor autorizado de **Aimsun** (simulación) y consultoría en ITS. Soluciones de CCTV integradas en proyectos de tráfico. | Consultoría y modelado de tráfico en corredores de Cundinamarca. | 2019 | https://www.sit-colombia.com/ |

---

#### 4.2.1.5. Análisis Comparativo de Soluciones CCTV

| Criterio | Kapsch EcoTrafiX™ | Siemens Xcelerator | Hikvision ITS | Seguritech VIITS | CI2 | Deviteck |
|----------|-------------------|---------------------|---------------|-------------------|-----|----------|
| **Madurez** | TRL 9 — desplegado en 50+ países | TRL 9 — presencia global | TRL 9 — líder mundial en CCTV, 900+ cámaras en UNAL | TRL 8 — 6,000 km en Colombia con INVIAS | TRL 7 — integración de sistemas | TRL 7 — implementación local |
| **Interoperabilidad** | NTCIP, ONVIF, API REST | Propio + estándares | ONVIF, API, integración con plataformas de gestión | Integrado con INVIAS | Estándares abiertos | Estándares abiertos |
| **Soporte Local** | Oficina en Bogotá (Kapsch Colombia) | Oficina en Bogotá | Distribuidor nacional, soporte local | Oficina en Bogotá, 4 años operando | Bogotá | Bogotá |
| **TCO 10 años** | Medio-Alto | Medio-Alto | Medio-Bajo (alta escala) | Medio (adaptado a presupuestos públicos) | Medio | Medio-Bajo |
| **Cumplimiento** | ISO 9001, ISO 27001 | Certificaciones globales | Certificaciones internacionales, ciberseguridad | Reconocimiento Sociedad de Ingenieros, Intertraffic Award | Certificaciones nacionales | Certificaciones nacionales |
| **Casos en Colombia** | Palmillas-Apaseo (México) | Accesos Norte | Universidad Nacional, múltiples proyectos | 6,000 km VIITS | Proyectos de integración | Proyectos de videovigilancia |

---

#### 4.2.1.6. Conclusiones y Recomendación para CC-01

El análisis comparativo revela que, para un corredor de concesión 5G con exigencias de alta disponibilidad y soporte local, las soluciones de **Kapsch TrafficCom** y **Siemens** presentan la mayor madurez tecnológica y soporte comercial en Colombia. **Hikvision** emerge como una alternativa robusta y costo-eficiente, con amplia experiencia en instalaciones de gran escala en el país (Universidad Nacional de Colombia, 900+ cámaras) y tecnología de punta en fusión radar+video y AID integrado. **Seguritech Colombia** ofrece una ventaja competitiva significativa: ha demostrado la capacidad de operar y mantener grandes despliegues nacionales (6,000 km con INVIAS), lo que reduce el riesgo de dependencia tecnológica y facilita la transición de conocimiento.

A nivel nacional, **CI2** y **Deviteck** representan opciones viables para integración e implementación local, con presencia en Bogotá y experiencia en proyectos de infraestructura de transporte. La proximidad geográfica al corredor Chía–Mondoñedo–Girardot (ambos con sede en Bogotá) reduce tiempos de respuesta y costos de desplazamiento.

**Recomendación:** Adoptar una arquitectura híbrida donde el VMS y la analítica central sean provistos por un integrador internacional o de gran escala (Kapsch, Siemens o Hikvision), mientras que la instalación, mantenimiento y primer nivel de soporte sean ejecutados por un proveedor nacional o LATAM con experiencia comprobada (Seguritech, CI2 o Deviteck). Esta estrategia optimiza el TCO y garantiza la soberanía operativa del concesionario.

---

*(Continúa con CC-02 a CC-42 en secciones siguientes...)*

---

### 4.2.2. CC-02: AID — SISTEMA DE DETECCIÓN AUTOMÁTICA DE INCIDENTES

#### 4.2.2.1. Descripción y Función del Componente

El componente CC-02, AID (Automatic Incident Detection), constituye el sistema de detección inteligente de eventos anómalos en la infraestructura vial. Su función es identificar automáticamente, en tiempo real, incidentes de tráfico como vehículos detenidos, flujo en contrario, peatones en la vía, pérdida de carga, incendios, humo y reducción brusca de velocidad, alertando al CCO para activar protocolos de respuesta.

Según el Capítulo 7 del Entregable 1, el AID es un sistema de **"Detección Automática de Incidentes"** que opera mediante analítica de video aplicada sobre las imágenes del CCTV (CC-01), sensores de detección de tráfico (CC-05) y algoritmos de inteligencia artificial. Su propósito es **"reducir el tiempo de respuesta a incidentes de 15 minutos a menos de 3 minutos"**.

#### 4.2.2.2. Variables Críticas de Diseño

| Variable | Especificación | Justificación |
|----------|---------------|---------------|
| Tasa de Detección | ≥ 95% | Identificación confiable de incidentes reales |
| Tasa de Falsas Alarmas | ≤ 5% | Minimizar alertas innecesarias que saturan al operador |
| Tiempo de Detección | ≤ 30 segundos desde la ocurrencia | Respuesta rápida para mitigar riesgos |
| Tipos de Incidentes | Detenciones, flujo contrario, peatones, pérdida de carga, humo, incendio, velocidad anómala | Cobertura completa de escenarios críticos |
| Integración | Con CCTV (CC-01), VMS (CC-03), SOS (CC-04), CCO (CC-19) | Flujo de información automatizado al CCO |
| Operación | 24/7, todas las condiciones climáticas | Incluso en niebla, lluvia intensa, oscuridad |
| Algoritmo | Deep Learning / IA entrenada con millones de escenarios | Generalización a escenarios no vistos |

#### 4.2.2.3. Ficha Técnica de Referencia

| Parámetro | Valor |
|-----------|-------|
| Código | CC-02 |
| Nombre | Sistema de Detección Automática de Incidentes (AID) |
| Tipo | Software de analítica + Hardware de procesamiento (GPU/Edge) |
| Subsistema | Gestión de Tráfico y Seguridad Vial |
| Función Principal | Detección automática en tiempo real de incidentes de tráfico y alerta al CCO |
| Campos de Aplicación | Todos los tramos, especialmente túneles, puentes y zonas de alta congestión |
| Variables Medidas | Tipo de incidente, ubicación, hora, severidad, clasificación de vehículos involucrados |
| Ciclo de Vida Esperado | 5-7 años (software); 10 años (hardware de edge) |
| Normativa Aplicable | ISO 14813-1, NTCIP 1204, IEEE 1512, EN 12966 |

---

#### 4.2.2.4. Referencias del Mercado: Proveedores y Soluciones

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Kapsch TrafficCom AG** | Austria | Viena | ITS, Tolling, Tunnel Management | **DYNAC® Tunnel Management** — Suite integrada de gestión de túneles con AID, SCADA, CCTV, VMS. Detección de incidentes en tiempo real con IA. | Autopista al Mar 1 (Túneles del Occidente), Colombia. 181 km, 33 km de doble calzada, túnel de 4.6 km. | 2021 | https://www.kapsch.net/en/press/releases/ktc-20210505-pr-en |
| 2 | **Hikvision** | China | Hangzhou | IoT, Seguridad, ITS | **Cámaras AID (Automatic Incident Detection)** — Cámaras con detección automática de peatones en autopistas, flujo en contrario, vehículos detenidos, basura. Reducción del 60% en falsas alarmas vs. AID convencional. | Universidad Nacional de Colombia, corredores viales en LATAM. | 2024 | https://www.hikvision.com/en/products/ITS-Products/traffic-cameras/incident-detection-cameras/ |
| 3 | **Siemens AG** | Alemania | Múnich | Movilidad, Infraestructura | **Siemens Mobility — Traffic Management** — Sistema de gestión de tráfico con AID integrado, detección de congestiones y anomalías en tiempo real. | Accesos Norte de Bogotá, proyectos de movilidad en LATAM. | 2024 | https://www.siemens.com/global/en.html |

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, Seguridad Vial | **VIITS — Vías Inteligentes** — Sistema de monitoreo de 6,000 km con detección de incidentes, cámaras de atención, alertas automáticas al CCO. | Proyecto ITS-VIITS para INVIAS, 6,000 km de carreteras nacionales. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración de sistemas, ITS | Integración de AID con CCTV, VMS y CCO. Soluciones de detección de incidentes para corredores viales. | Proyectos de integración ITS en infraestructura de transporte en Colombia. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, Seguridad, ITS | Implementación de sistemas de detección de incidentes, integración con videovigilancia y centros de control. | Proyectos de videovigilancia inteligente en infraestructura de transporte en Colombia. | 2024 | https://www.deviteck.com.co |
| 3 | **SIT Ltda.** | Colombia | Chía, Cundinamarca | ITS, Simulación | Consultoría en modelado de tráfico y detección de incidentes, integración con Aimsun. | Corredores de Cundinamarca, modelado de congestiones y detección de anomalías. | 2019 | https://www.sit-colombia.com/ |

---

#### 4.2.2.5. Análisis Comparativo de Soluciones AID

| Criterio | Kapsch DYNAC® | Hikvision AID | Seguritech VIITS | CI2 | Deviteck |
|----------|---------------|---------------|-------------------|-----|----------|
| **Madurez** | TRL 9 — desplegado en túneles mundiales, Colombia | TRL 9 — cámaras AID probadas, reducción 60% falsas alarmas | TRL 8 — 6,000 km operando con INVIAS | TRL 7 — integración local | TRL 7 — implementación local |
| **Interoperabilidad** | Integración con CCTV, SCADA, VMS, CCO | ONVIF, API, integración con VMS | Integrado con INVIAS | Estándares abiertos | Estándares abiertos |
| **Soporte Local** | Oficina Bogotá, proyectos en Colombia (Accesos Norte, Autopista al Mar) | Distribuidor nacional | Oficina Bogotá | Bogotá | Bogotá |
| **TCO 10 años** | Medio-Alto | Medio-Bajo | Medio | Medio | Medio-Bajo |
| **Cumplimiento** | ISO 9001, ISO 27001 | Certificaciones internacionales | Reconocimiento INVIAS | Certificaciones nacionales | Certificaciones nacionales |
| **Casos en Colombia** | Autopista al Mar, Accesos Norte, Vías del Nus | Universidad Nacional | 6,000 km VIITS | Proyectos de integración | Proyectos de videovigilancia |

---

#### 4.2.2.6. Conclusiones y Recomendación para CC-02

El análisis comparativo demuestra que **Kapsch TrafficCom** tiene la mayor experiencia en AID para túneles en Colombia, con el proyecto Autopista al Mar (Túneles del Occidente) como referencia directa. **Hikvision** ofrece una solución de cámaras AID con IA avanzada (reducción del 60% en falsas alarmas) y costo competitivo, ideal para complementar el CCTV. **Seguritech** ha demostrado operación a escala nacional (6,000 km) con detección de incidentes integrada.

**Recomendación:** Adoptar una arquitectura dual donde la detección de incidentes en túneles y zonas críticas use el sistema DYNAC® de Kapsch (integrado con CCTV y SCADA), mientras que la detección en tramos abiertos y puentes use cámaras AID de Hikvision con analítica de edge. El soporte local y mantenimiento puede ser ejecutado por CI2, Deviteck o Seguritech, garantizando respuesta en 24-48 horas.

---

### 4.2.3. CC-03: DMS/VMS — SISTEMA DE MENSAJERÍA VARIABLE

#### 4.2.3.1. Descripción y Función del Componente

El componente CC-03, DMS/VMS (Dynamic Message Sign / Variable Message Sign), es el sistema de señalización electrónica dinámica que comunica información en tiempo real a los usuarios de la vía. Su función es mostrar mensajes de tráfico, alertas de incidentes, tiempos de viaje, restricciones de velocidad, condiciones meteorológicas y recomendaciones de ruta, mejorando la toma de decisiones del conductor y la seguridad vial.

Según el Capítulo 7 del Entregable 1, el DMS/VMS es un sistema de **"Mensajería Variable"** que incluye paneles LED de matriz completa, controladores de señal, software de gestión de contenido y la red de comunicaciones que conecta los paneles con el CCO. El propósito es **"informar al usuario de la vía en tiempo real para optimizar la movilidad y prevenir accidentes"**.

#### 4.2.3.2. Variables Críticas de Diseño

| Variable | Especificación | Justificación |
|----------|---------------|---------------|
| Tecnología de Display | LED RGB full color, matriz completa | Flexibilidad para mostrar texto, gráficos e iconos |
| Resolución | Pixel pitch 16-20 mm para autopistas; 10-12 mm para túneles | Legibilidad a distancia apropiada según velocidad |
| Brillo | ≥ 10,000 nits (día); ≥ 5,000 nits (noche con atenuación) | Visibilidad en condiciones de sol directo y oscuridad |
| Ángulo de Visión | Horizontal ≥ 60°, Vertical ≥ 30° | Cobertura de múltiples carriles |
| Protección Ambiental | IP65, IK10, anti-corrosión | Resistencia a lluvia, polvo, vandalismo y ambientes costeros |
| Control | NTCIP 1203, Ethernet, fibra óptica, 4G/5G de respaldo | Integración con el CCO y operación remota |
| Normativa | EN 12966, MUTCD (compatible) | Homologación para uso en vías públicas |

#### 4.2.3.3. Ficha Técnica de Referencia

| Parámetro | Valor |
|-----------|-------|
| Código | CC-03 |
| Nombre | Sistema de Mensajería Variable (DMS/VMS) |
| Tipo | Hardware de campo (paneles LED) + Software de gestión de contenido |
| Subsistema | Gestión de Tráfico y Seguridad Vial / Información al Usuario |
| Función Principal | Comunicación de información en tiempo real a usuarios de la vía |
| Campos de Aplicación | Entradas a túneles, puentes, zonas de congestión, accesos a peajes, tramos críticos |
| Variables Medidas | Mensajes de texto, iconos, tiempos de viaje, velocidad variable, alertas |
| Ciclo de Vida Esperado | 10-12 años (paneles LED); 15 años (estructura de montaje) |
| Normativa Aplicable | ISO 14813-1, NTCIP 1203, EN 12966, MUTCD |

---

#### 4.2.3.4. Referencias del Mercado: Proveedores y Soluciones

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **SWARCO AG** | Austria | Wattens (Innsbruck) | Señalización, ITS, VMS | **SWARCO Variable Message Signs** — Paneles LED full color RGB, matriz completa, certificados EN 12966, control Zephyr, IP-based (2/3/4G, fibra, mesh, Wi-Fi). | Desplegados en el Ártico, Arabia Saudita, Brasil y múltiples proyectos LATAM. | 2024 | https://www.swarco.com/es |
| 2 | **Daktronics, Inc.** | EE.UU. | Brookings, Dakota del Sur | VMS, DMS, ITS | **Vanguard® DMS** — Paneles de mensaje dinámico con acceso frontal, walk-in, señales de uso de carril, tiempos de viaje/tarifas, velocidad variable. Líder desde 1988. | Miles de instalaciones en autopistas de EE.UU., Canadá y proyectos internacionales. | 2024 | https://www.daktronics.com/en-us/products/its-dynamic-message-signs |
| 3 | **Kapsch TrafficCom AG** | Austria | Viena | ITS, Tolling, VMS | **EcoTrafiX™ VMS** — Paneles variables integrados con ATMS, control centralizado, gestión de contenido automatizado. | Palmillas-Apaseo Highway, México; Accesos Norte, Bogotá. | 2025 | https://www.kapsch.net/en/press/releases/ktc-20250805-pr-en |

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, VMS | **VIITS — Vías Inteligentes** — Sistema de paneles variables, señalización dinámica y control de tráfico en 6,000 km de carreteras nacionales. | Proyecto ITS-VIITS para INVIAS, 6,000 km. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración, ITS | Integración de VMS/DMS con CCTV, CCO y sistemas de control de tráfico. | Proyectos de integración de señalización variable en infraestructura de transporte. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, ITS | Diseño e implementación de sistemas de señalización electrónica, paneles LED y control de contenido. | Proyectos de señalización inteligente en infraestructura de transporte. | 2024 | https://www.deviteck.com.co |
| 3 | **SIT Ltda.** | Colombia | Chía, Cundinamarca | ITS, Movilidad | Consultoría e integración de VMS en corredores de tráfico, modelado de información al usuario. | Corredores de Cundinamarca, proyectos de información dinámica. | 2019 | https://www.sit-colombia.com/ |

---

#### 4.2.3.5. Análisis Comparativo de Soluciones DMS/VMS

| Criterio | SWARCO VMS | Daktronics Vanguard | Kapsch EcoTrafiX™ VMS | Seguritech VIITS | CI2 | Deviteck |
|----------|------------|---------------------|------------------------|-------------------|-----|----------|
| **Madurez** | TRL 9 — desde 1969, desplegado en Ártico, Arabia, Brasil | TRL 9 — desde 1988, líder en Norteamérica | TRL 9 — integrado con ATMS | TRL 8 — 6,000 km con INVIAS | TRL 7 — integración local | TRL 7 — implementación local |
| **Interoperabilidad** | EN 12966, NTCIP 1203, UTMC, IP-based | NTCIP, MUTCD, EN 12966 | NTCIP, API REST, integración con EcoTrafiX™ | Integrado con INVIAS | Estándares abiertos | Estándares abiertos |
| **Soporte Local** | Presencia en LATAM, Brasil | Soporte internacional | Oficina Bogotá, proyectos en Colombia | Oficina Bogotá | Bogotá | Bogotá |
| **TCO 10 años** | Medio-Alto | Medio-Alto | Medio-Alto | Medio | Medio | Medio-Bajo |
| **Cumplimiento** | CE, EN 12966, TOPAS | MUTCD, EN 12966 | ISO 9001, ISO 27001 | Reconocimiento INVIAS | Certificaciones nacionales | Certificaciones nacionales |
| **Casos en Colombia** | Proyectos en Brasil, LATAM | Proyectos internacionales | Accesos Norte, Palmillas-Apaseo | 6,000 km VIITS | Proyectos de integración | Proyectos de señalización |

---

#### 4.2.3.6. Conclusiones y Recomendación para CC-03

El análisis comparativo identifica a **SWARCO** y **Daktronics** como los fabricantes de paneles VMS con mayor trayectoria y certificaciones internacionales (EN 12966). **SWARCO** tiene ventaja en LATAM con despliegues probados en Brasil (clima tropical similar al colombiano). **Daktronics** es el estándar de facto en Norteamérica con la línea Vanguard probada desde 1988. **Kapsch** ofrece la ventaja de integración completa con su plataforma EcoTrafiX™ ATMS.

A nivel nacional, **CI2** y **Deviteck** pueden ejecutar la integración, instalación y mantenimiento local de paneles SWARCO, Daktronics o Kapsch, garantizando soporte técnico en 24-48 horas.

**Recomendación:** Adoptar paneles VMS de **SWARCO** (full color RGB, certificados EN 12966) para túneles y zonas críticas, dado su despliegue en climas similares (Brasil). Para tramos abiertos y zonas de peaje, considerar **Daktronics Vanguard** (probadas en autopistas de alta velocidad) o **Kapsch** (si se busca integración total con el ATMS). La instalación y mantenimiento deben ser ejecutados por **CI2** o **Deviteck** con soporte local.

---

*(Continúa con CC-04 a CC-42 en secciones siguientes...)*
