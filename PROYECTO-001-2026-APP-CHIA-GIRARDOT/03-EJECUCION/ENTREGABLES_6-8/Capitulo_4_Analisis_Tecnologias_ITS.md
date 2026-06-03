# CAPÍTULO 4: REVISIÓN Y ANÁLISIS DE TECNOLOGÍAS ITS, EQUIPAMIENTO DE HARDWARE, SOFTWARE Y SERVICIOS TECNOLÓGICOS

---

## 4.1. MARCO CONCEPTUAL

### 4.1.1. Propósito del Capítulo

El presente capítulo constituye el eje analítico de la propuesta de despliegue de Sistemas Inteligentes de Transporte (ITS) para el corredor vial Chía–Mondoñedo–Girardot, en cumplimiento de los términos de referencia del contrato TC-PS-05-917-2026. Su objetivo es establecer, con rigor técnico y fundamento empírico, el universo de tecnologías, equipos de hardware, plataformas de software y servicios conectados disponibles en el mercado global, regional y nacional, para dar cumplimiento a los nueve servicios estratégicos y 114 funciones técnicas definidos en el Capítulo 2.

Este análisis no se limita a la enumeración de fabricantes; busca, de manera estructurada, relacionar cada tecnología con el componente de corredor (CC) correspondiente, evaluar su madurez, interoperabilidad, soporte local y adecuación al contexto operativo colombiano, y finalmente documentar las soluciones disponibles para su despliegue en la infraestructura objeto de concesión.

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

**Fase V: Documentación de Alternativas**
- Presentación de las soluciones disponibles por componente, con sus características, ventajas y consideraciones.
- Identificación de alternativas viables y riesgos de dependencia tecnológica, sin emitir recomendaciones de compra o adjudicación.

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

El componente CC-01, CCTV (Circuito Cerrado de Televisión), constituye la infraestructura de percepción visual que permite el monitoreo continuo de los 306 km de vía del corredor Chía–Girardot. Según la definición del Capítulo 7 del Entregable 1, el sistema integra cámaras IP de alta definición (4K) con capacidad de visión nocturna infrarroja para operación en zonas de neblina persistente. Transmite video en tiempo real al Centro de Control de Operaciones (CCO) mediante red de fibra óptica redundante, con latencias inferiores a 300 ms y grabación continua de 30 días. Incluye capacidades analíticas de video para detección de incidentes, integración con subsistemas ITS (AID, DMS, SOS), y cumplimiento normativo con Resolución 1090 de 2020 del Ministerio de Transporte de Colombia.

El propósito es proveer **"visibilidad situacional continua de la infraestructura vial"**, permitiendo a los operadores del CCO observar el estado de la vía, detectar incidentes, verificar condiciones meteorológicas y documentar eventos para investigaciones posteriores.

#### 4.2.1.2. Variables Críticas de Diseño (según Capítulo 7, Entregable 1)

| Variable | Especificación | Justificación (Capítulo 7) |
|----------|---------------|---------------------------|
| Resolución | 4K (alta definición) | Identificación de detalles a distancia, evidencia para investigaciones |
| Visión Nocturna | Infrarroja | Operación en zonas de neblina persistente y baja iluminación |
| Distancia entre Cámaras | 500 m en vía abierta; mayor densidad en puentes críticos y zonas de alta siniestralidad | Cobertura continua de 306 km con énfasis en puntos críticos |
| Transmisión | Fibra óptica monomodo con topología redundante | Garantía de disponibilidad ante cortes de fibra |
| Latencia | < 300 ms | Transmisión en tiempo real al CCO |
| Respaldo de Comunicaciones | 4G/5G en puntos críticos | Continuidad operativa ante falla de fibra óptica |
| Almacenamiento | 30 días de grabación continua en 4K | Evidencia para investigaciones de siniestros y análisis operativo |
| Compresión | H.265 | Optimización del espacio de almacenamiento sin pérdida de calidad |
| Escalabilidad | Hasta 600 cámaras | Crecimiento futuro del corredor sin degradación de rendimiento |
| Integración | Con AID, DMS, SOS | Flujo de información automatizado entre subsistemas ITS |
| Cumplimiento | Resolución 1090 de 2020 (MinTransporte) | Requisito obligatorio para corredores de alta concesión en Colombia |

#### 4.2.1.3. Ficha Técnica de Referencia (validada contra Capítulo 7)

| Parámetro | Valor |
|-----------|-------|
| Código | CC-01 |
| Nombre | Sistema de Videovigilancia (CCTV) |
| Tipo | Hardware de campo (cámaras IP) + Software de gestión de video (VMS) |
| Subsistema | Gestión de Tráfico y Seguridad Vial |
| Función Principal | Monitoreo continuo de 306 km, detección visual de incidentes, apoyo a gestión de tráfico y operaciones de mantenimiento |
| Campos de Aplicación | Todos los tramos: vía abierta (cada 500 m), puentes críticos (mayor densidad), zonas de alta siniestralidad, túneles |
| Variables Medidas | Imágenes de video en 4K, metadatos de analítica (detección de incidentes, clasificación de vehículos) |
| Ciclo de Vida Esperado | 7-10 años (cámaras); 15 años (infraestructura de montaje) |
| Normativa Aplicable | Resolución 1090 de 2020 (MinTransporte de Colombia), ISO 14813-1, NTCIP 1205, IEEE 802.3bt, ONVIF Profile S/G/T |

---

#### 4.2.1.4. Referencias del Mercado: Proveedores y Soluciones

A continuación se presentan los proveedores identificados, verificados y clasificados según su origen geográfico, cumpliendo con los criterios de información pública, verificabilidad de fuentes y neutralidad analítica. Se priorizan empresas con presencia documentada en Colombia y casos de implementación verificables en corredores viales o proyectos de infraestructura nacional. **Este documento es un estudio de tecnologías disponibles; no constituye recomendación de compra ni adjudicación a proveedores específicos.**

---

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Kapsch TrafficCom AG** | Austria | Viena | ITS, Tolling, Traffic Management | **EcoTrafiX™ Video** — Plataforma de gestión de video integrada con ATMS, soporta miles de cámaras IP, analítica de video, videowall. | Palmillas-Apaseo Highway, México. 21 cámaras de tráfico + sistema de integridad vehicular con LPR. | 2025 | https://www.kapsch.net/en/press/releases/ktc-20250805-pr-en |
| 2 | **Hikvision** | China | Hangzhou | IoT, Seguridad Electrónica, ITS | **Sistema de Tráfico Inteligente (ITS)** — Cámaras de control de puntos de verificación, fusión radar+video, reconocimiento de matrículas impulsado por IA, AID integrado, tecnología DarkFighter 2.0 para baja iluminación. | Universidad Nacional de Colombia — videovigilancia con 900+ cámaras, control de acceso y LPR. | 2019 | https://www.hikvision.com/es-co/ |
| 3 | **Bosch Security Systems** | Alemania | Gerlingen | Seguridad, Videovigilancia, ITS | **Bosch Video Management System (VMS)** — Sistema de gestión de video con analítica integrada, cámaras IP de alta definición, interoperabilidad con sistemas de tráfico. | Proyectos de videovigilancia en infraestructura crítica y corredores viales en Europa y LATAM. | 2024 | https://www.boschsecurity.com |

---

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, Seguridad Vial, Monitoreo | **VIITS — Vías Inteligentes** — Sistema de modernización vial con 6,000 km de red primaria, cámaras de atención de incidentes, Centro de Control. | Proyecto ITS-VIITS para INVIAS, 6,000 km de carreteras nacionales. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |
| 2 | **Grupo Masa** | México | Ciudad de México | ITS, Construcción, Infraestructura | Sistemas de videovigilancia y control de tráfico para corredores viales, integración con centros de control. | Corredores viales en México y proyectos de infraestructura en LATAM. | 2024 | https://www.grupomasa.com.mx |

---

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración de sistemas, ITS, Tecnología | Consultoría e integración de sistemas inteligentes de transporte, infraestructura tecnológica para corredores viales. | Proyectos de integración tecnológica en infraestructura de transporte en Colombia. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, ITS, Seguridad Electrónica | Diseño e implementación de sistemas de videovigilancia, control de acceso, redes y soluciones ITS. | Proyectos de videovigilancia y control en infraestructura de transporte en Colombia. | 2024 | https://www.deviteck.com.co |
| 3 | **SIT Ltda. — Sistemas Inteligentes de Transporte** | Colombia | Chía, Cundinamarca | ITS, Simulación de Tráfico, Movilidad | Distribuidor autorizado de **Aimsun** (simulación) y consultoría en ITS. Soluciones de CCTV integradas en proyectos de tráfico. | Consultoría y modelado de tráfico en corredores de Cundinamarca. | 2019 | https://www.sit-colombia.com/ |

---

#### 4.2.1.5. Análisis Comparativo de Soluciones CCTV

| Criterio | Kapsch EcoTrafiX™ | Hikvision ITS | Bosch VMS | Seguritech VIITS | Grupo Masa | CI2 | Deviteck | SIT Ltda. |
|----------|-------------------|---------------|-----------|-------------------|------------|-----|----------|-----------|
| **Madurez** | TRL 9 — desplegado en 50+ países | TRL 9 — líder mundial en CCTV, 900+ cámaras en UNAL | TRL 9 — presencia global en seguridad | TRL 8 — 6,000 km en Colombia con INVIAS | TRL 8 — corredores viales en México | TRL 7 — integración de sistemas | TRL 7 — implementación local | TRL 7 — consultoría y modelado |
| **Interoperabilidad** | NTCIP, ONVIF, API REST | ONVIF, API, integración con plataformas de gestión | ONVIF, estándares abiertos | Integrado con INVIAS | Estándares abiertos | Estándares abiertos | Estándares abiertos | Aimsun, estándares abiertos |
| **Soporte Local** | Oficina en Bogotá (Kapsch Colombia) | Distribuidor nacional, soporte local | Distribuidor en Colombia | Oficina en Bogotá, 4 años operando | México | Bogotá | Bogotá | Chía, Cundinamarca |
| **TCO 10 años** | Medio-Alto | Medio-Bajo (alta escala) | Medio-Alto | Medio (adaptado a presupuestos públicos) | Medio | Medio | Medio-Bajo | Bajo-Medio |
| **Cumplimiento** | ISO 9001, ISO 27001 | Certificaciones internacionales, ciberseguridad | ISO 9001, ISO 27001 | Reconocimiento Sociedad de Ingenieros, Intertraffic Award | Certificaciones nacionales | Certificaciones nacionales | Certificaciones nacionales | Experiencia local |
| **Casos en Colombia** | Palmillas-Apaseo (México), Accesos Norte | Universidad Nacional, múltiples proyectos | Infraestructura crítica en LATAM | 6,000 km VIITS | México | Proyectos de integración | Proyectos de videovigilancia | Corredores de Cundinamarca |

---

#### 4.2.1.6. Conclusiones para CC-01

El análisis comparativo documenta un mercado maduro con múltiples alternativas tecnológicas para la implementación de CCTV en corredores de concesión 5G. Las soluciones internacionales (Kapsch, Hikvision, Bosch) presentan madurez probada en despliegues de gran escala, mientras que los proveedores LATAM y nacionales (Seguritech, Grupo Masa, CI2, Deviteck, SIT) ofrecen ventajas en soporte local, conocimiento del contexto colombiano y adaptación a presupuestos públicos.

Las variables críticas de diseño definidas en el Capítulo 7 del Entregable 1 (resolución 4K, visión nocturna infrarroja, cobertura cada 500 m, latencia < 300 ms, almacenamiento 30 días, integración con AID/DMS/SOS, cumplimiento Resolución 1090 de 2020) son técnicamente alcanzables con las tecnologías documentadas. La selección final de proveedores dependerá de la estrategia de adquisición del concesionario, criterios de evaluación de ofertas y condiciones contractuales específicas del proyecto.

---

### 4.2.2. CC-02: AID — SISTEMA DE DETECCIÓN AUTOMÁTICA DE INCIDENTES

#### 4.2.2.1. Descripción y Función del Componente

El componente CC-02, AID (Automatic Incident Detection), implementa análisis de video mediante inteligencia artificial para la detección en tiempo real de eventos críticos: vehículos detenidos, peatones en vía, objetos extraños, humo/incendios, derrames, vehículos en contravía y colisiones. Según la definición del Capítulo 7 del Entregable 1, el sistema procesa video de cámaras CCTV instaladas en el corredor mediante algoritmos de deep learning ejecutados en servidores de edge o en el CCO, generando alertas automáticas a operadores en menos de 10 segundos desde la ocurrencia del evento. Integrado con CCTV, DMS y ECS/SOS, proporciona capacidad de respuesta temprana que reduce severidad de incidentes y mejora tiempos de atención en el corredor de 306 km.

El propósito es **"identificar proactivamente peligros: capacidad de alertar automáticamente sobre eventos disruptivos sin depender del ojo humano"**.

#### 4.2.2.2. Variables Críticas de Diseño (según Capítulo 7, Entregable 1)

| Variable | Especificación | Justificación (Capítulo 7) |
|----------|---------------|---------------------------|
| Tipos de Incidentes Detectados | Vehículos detenidos, peatones en vía, objetos extraños, humo/incendios, derrames, vehículos en contravía, colisiones | Cobertura completa de escenarios críticos en 306 km de corredor |
| Tiempo de Detección | < 10 segundos desde la ocurrencia | Reducción de severidad de incidentes y mejora de tiempos de respuesta |
| Procesamiento | Deep learning en edge computing o servidores GPU en CCO | Flexibilidad según criticidad del tramo y latencia requerida |
| Integración | Con CCTV, DMS, ECS/SOS | Flujo de información automatizado al CCO y activación de protocolos |
| Zonas de Detección | Personalizadas por tramo mediante calibración de cámaras | Adaptación a características específicas de cada zona del corredor |
| Tracking | Entre cámaras adyacentes | Seguimiento de objetos en movimiento a lo largo del corredor |
| Reducción de Falsos Positivos | Aprendizaje continuo basado en retroalimentación de operadores | Mejora de precisión con el tiempo y reducción de alertas innecesarias |
| Cumplimiento | ISO 39001 | Estándar internacional de seguridad vial |

#### 4.2.2.3. Ficha Técnica de Referencia (validada contra Capítulo 7)

| Parámetro | Valor |
|-----------|-------|
| Código | CC-02 |
| Nombre | Sistema de Detección Automática de Incidentes (AID) |
| Tipo | Software de analítica (deep learning, computer vision) + Hardware de procesamiento (GPU, edge) |
| Subsistema | Gestión de Tráfico y Seguridad Vial |
| Función Principal | Detección automática en tiempo real de incidentes de tráfico y alerta al CCO en menos de 10 segundos |
| Campos de Aplicación | Todos los tramos, especialmente zonas de neblina, alta siniestralidad, túneles y puentes |
| Variables Medidas | Tipo de incidente, ubicación, hora, severidad, clasificación de vehículos involucrados |
| Ciclo de Vida Esperado | 5-7 años (software); 10 años (hardware de edge) |
| Normativa Aplicable | ISO 39001 (Seguridad Vial), ISO 14813-1, NTCIP 1204 |

---

#### 4.2.2.4. Referencias del Mercado: Proveedores y Soluciones

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Kapsch TrafficCom AG** | Austria | Viena | ITS, Tunnel Management | **DYNAC® Tunnel Management** — Suite integrada de gestión de túneles con AID, SCADA, CCTV, VMS. Detección de incidentes en tiempo real. | Autopista al Mar 1 (Túneles del Occidente), Colombia. 181 km, túnel de 4.6 km. | 2021 | https://www.kapsch.net/en/press/releases/ktc-20210505-pr-en |
| 2 | **Hikvision** | China | Hangzhou | IoT, ITS, Seguridad | **Cámaras AID (Automatic Incident Detection)** — Detección de peatones en autopistas, flujo en contrario, vehículos detenidos, basura. Reducción del 60% en falsas alarmas. | Universidad Nacional de Colombia, corredores viales en LATAM. | 2024 | https://www.hikvision.com/en/products/ITS-Products/traffic-cameras/incident-detection-cameras/ |
| 3 | **Jenoptik Group** | Alemania | Jena | ITS, Semiconductores, Optoelectrónica | **Jenoptik TraffiData** — Sistema de detección de incidentes con cámaras y sensores, analítica de tráfico. | Autopistas en Europa, proyectos de tráfico en LATAM. | 2024 | https://www.jenoptik.com |

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, Seguridad Vial | **VIITS — Vías Inteligentes** — Sistema de monitoreo de 6,000 km con detección de incidentes, cámaras de atención, alertas automáticas. | Proyecto ITS-VIITS para INVIAS, 6,000 km. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |
| 2 | **SICE** | España / México | Madrid | ITS, Traffic Management | **SICE Intelligent Traffic Management** — Sistemas de gestión de tráfico con detección de incidentes, control de túneles. | Proyectos de ITS en México y España. | 2024 | https://www.sice.es |

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración de sistemas, ITS | Integración de AID con CCTV, VMS y CCO. Soluciones de detección de incidentes para corredores viales. | Proyectos de integración ITS en infraestructura de transporte en Colombia. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, Seguridad, ITS | Implementación de sistemas de detección de incidentes, integración con videovigilancia y centros de control. | Proyectos de videovigilancia inteligente en infraestructura de transporte en Colombia. | 2024 | https://www.deviteck.com.co |
| 3 | **ILINEA SAS** | Colombia | Bogotá | Ingeniería de Sistemas, Seguridad | Diseño e integración de sistemas de CCTV con analítica de video, control de acceso y automatización. | Conjuntos residenciales, industrias y proyectos de seguridad en Bogotá. | 2024 | https://ilinea.com.co |

---

#### 4.2.2.5. Análisis Comparativo de Soluciones AID

| Criterio | Kapsch DYNAC® | Hikvision AID | Jenoptik TraffiData | Seguritech VIITS | SICE | CI2 | Deviteck | ILINEA |
|----------|---------------|---------------|---------------------|------------------|------|-----|----------|--------|
| **Madurez** | TRL 9 — túneles mundiales, Colombia | TRL 9 — reducción 60% falsas alarmas | TRL 9 — Europa, LATAM | TRL 8 — 6,000 km con INVIAS | TRL 9 — España, México | TRL 7 — integración local | TRL 7 — implementación local | TRL 7 — proyectos de seguridad |
| **Interoperabilidad** | Integración con CCTV, SCADA, VMS, CCO | ONVIF, API, integración con VMS | Estándares abiertos | Integrado con INVIAS | Estándares abiertos | Estándares abiertos | Estándares abiertos | Estándares abiertos |
| **Soporte Local** | Oficina Bogotá, proyectos Colombia | Distribuidor nacional | Distribuidor en Colombia | Oficina Bogotá | México | Bogotá | Bogotá | Bogotá |
| **TCO 10 años** | Medio-Alto | Medio-Bajo | Medio-Alto | Medio | Medio-Alto | Medio | Medio-Bajo | Medio-Bajo |
| **Cumplimiento** | ISO 9001, ISO 27001 | Certificaciones internacionales | ISO 9001 | Reconocimiento INVIAS | Certificaciones europeas | Certificaciones nacionales | Certificaciones nacionales | Certificaciones nacionales |
| **Casos en Colombia** | Autopista al Mar, Accesos Norte, Vías del Nus | Universidad Nacional | LATAM | 6,000 km VIITS | México | Proyectos de integración | Proyectos de videovigilancia | Proyectos de seguridad |

---

#### 4.2.2.6. Conclusiones para CC-02

El análisis comparativo documenta soluciones de AID con distintos enfoques tecnológicos: Kapsch con suite integrada para túneles, Hikvision con cámaras AID de edge, Jenoptik con sistemas de detección multi-sensor. A nivel LATAM, Seguritech y SICE ofrecen experiencia en despliegues regionales. A nivel nacional, CI2, Deviteck e ILINEA pueden ejecutar integración e implementación local.

Las variables críticas del Capítulo 7 (detección < 10 segundos, procesamiento deep learning, edge o GPU, integración con CCTV/DMS/SOS, tracking entre cámaras, aprendizaje continuo, ISO 39001) son alcanzables con las tecnologías documentadas. La selección final dependerá de la estrategia de adquisición del concesionario y las condiciones específicas del proyecto.

---

### 4.2.3. CC-03: DMS/VMS — SISTEMA DE MENSAJERÍA VARIABLE

#### 4.2.3.1. Descripción y Función del Componente

El componente CC-03, DMS/VMS (Dynamic Message Sign / Variable Message Sign), proporciona capacidad de comunicación dinámica con usuarios viales mediante paneles de mensajes LED de alta visibilidad. Según la definición del Capítulo 7 del Entregable 1, el sistema permite publicar alertas de tráfico, condiciones climáticas adversas, restricciones de vía, tiempos de recorrido estimados y mensajes de seguridad vial en tiempo real. Integrado con los subsistemas AID, Meteo y CCO, garantiza que la información mostrada corresponda a las condiciones reales del corredor, mejorando la toma de decisiones de conductores y reduciendo la siniestralidad atribuible a falta de información oportuna.

El propósito es **"difusión masiva de información: capacidad de comunicar mensajes estratégicos y alertas directamente al conductor en vía"**.

#### 4.2.3.2. Variables Críticas de Diseño (según Capítulo 7, Entregable 1)

| Variable | Especificación | Justificación (Capítulo 7) |
|----------|---------------|---------------------------|
| Tecnología de Display | LED de matriz completa (full matrix) | Flexibilidad para texto, gráficos e iconos |
| Ubicación | Antes de zonas de decisión críticas: intercambiadores, zonas de neblina, reductores de velocidad, puntos de alta siniestralidad | Información oportuna para toma de decisiones del conductor |
| Brillo | Alta intensidad con ajuste automático según iluminación ambiental (fotoceldas) | Visibilidad en sol directo, nocturnas y neblina |
| Control | Centralizado desde CCO | Programación de mensajes predefinidos y personalizados en tiempo real |
| Protocolo | NTCIP | Interoperabilidad con diferentes fabricantes de paneles |
| Publicación Automática | Basada en triggers de AID, Meteo | Mensajes de alerta sin intervención manual del operador |
| Redundancia | Fibra óptica + radio | Disponibilidad ante fallas de red |
| Mensajes | Predefinidos y personalizables | Escenarios estándar y emergencias en tiempo real |

#### 4.2.3.3. Ficha Técnica de Referencia (validada contra Capítulo 7)

| Parámetro | Valor |
|-----------|-------|
| Código | CC-03 |
| Nombre | Sistema de Mensajería Variable (DMS/VMS) |
| Tipo | Hardware de campo (paneles LED full matrix) + Software de gestión de contenido |
| Subsistema | Gestión de Tráfico y Seguridad Vial / Información al Usuario |
| Función Principal | Comunicación de información en tiempo real a usuarios de la vía: alertas, tiempos de recorrido, restricciones, seguridad vial |
| Campos de Aplicación | Antes de intercambiadores, zonas de neblina, reductores de velocidad, puntos de alta siniestralidad |
| Variables Medidas | Mensajes de texto, iconos, tiempos de viaje, velocidad variable, alertas climáticas |
| Ciclo de Vida Esperado | 10-12 años (paneles LED); 15 años (estructura de montaje) |
| Normativa Aplicable | ISO 14813-1, NTCIP 1203, EN 12966, MUTCD |

---

#### 4.2.3.4. Referencias del Mercado: Proveedores y Soluciones

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **SWARCO AG** | Austria | Wattens (Innsbruck) | Señalización, ITS, VMS | **SWARCO Variable Message Signs** — Paneles LED full color RGB, matriz completa, certificados EN 12966, control Zephyr, IP-based. | Desplegados en Ártico, Arabia Saudita, Brasil, múltiples proyectos LATAM. | 2024 | https://www.swarco.com/es |
| 2 | **Daktronics, Inc.** | EE.UU. | Brookings, Dakota del Sur | VMS, DMS, ITS | **Vanguard® DMS** — Paneles de mensaje dinámico: acceso frontal, walk-in, señales de uso de carril, tiempos de viaje/tarifas, velocidad variable. Líder desde 1988. | Miles de instalaciones en autopistas de EE.UU., Canadá y proyectos internacionales. | 2024 | https://www.daktronics.com/en-us/products/its-dynamic-message-signs |
| 3 | **LeddarTech** | Canadá | Quebec | Sensores, ITS, LiDAR | **LeddarTraffic** — Soluciones de detección de tráfico y control de señales para gestión de flujo vehicular. | Proyectos de gestión de tráfico en Norteamérica y Europa. | 2024 | https://www.leddartech.com |

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, VMS | **VIITS — Vías Inteligentes** — Sistema de paneles variables, señalización dinámica y control de tráfico en 6,000 km de carreteras nacionales. | Proyecto ITS-VIITS para INVIAS, 6,000 km. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |
| 2 | **Grupo Masa** | México | Ciudad de México | ITS, Construcción | Sistemas de señalización variable y control de tráfico para corredores viales. | Corredores viales en México y proyectos de infraestructura en LATAM. | 2024 | https://www.grupomasa.com.mx |

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración, ITS | Integración de VMS/DMS con CCTV, CCO y sistemas de control de tráfico. | Proyectos de integración de señalización variable en infraestructura de transporte. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, ITS | Diseño e implementación de sistemas de señalización electrónica, paneles LED y control de contenido. | Proyectos de señalización inteligente en infraestructura de transporte. | 2024 | https://www.deviteck.com.co |
| 3 | **SISLEC** | Colombia | Bogotá | Seguridad Electrónica | Instalación y mantenimiento de sistemas de video, señalización electrónica, NVR, VMS. | Proyectos de videovigilancia y señalización empresarial en Bogotá. | 2024 | https://sislec.com |

---

#### 4.2.3.5. Análisis Comparativo de Soluciones DMS/VMS

| Criterio | SWARCO VMS | Daktronics Vanguard | LeddarTech | Seguritech VIITS | Grupo Masa | CI2 | Deviteck | SISLEC |
|----------|------------|---------------------|------------|------------------|------------|-----|----------|--------|
| **Madurez** | TRL 9 — desde 1969, Ártico, Arabia, Brasil | TRL 9 — desde 1988, líder Norteamérica | TRL 8 — Norteamérica, Europa | TRL 8 — 6,000 km con INVIAS | TRL 8 — corredores México | TRL 7 — integración local | TRL 7 — implementación local | TRL 7 — proyectos empresariales |
| **Interoperabilidad** | EN 12966, NTCIP 1203, UTMC | NTCIP, MUTCD, EN 12966 | Estándares abiertos | Integrado con INVIAS | Estándares abiertos | Estándares abiertos | Estándares abiertos | Estándares abiertos |
| **Soporte Local** | Presencia LATAM, Brasil | Soporte internacional | Canadá | Oficina Bogotá | México | Bogotá | Bogotá | Bogotá |
| **TCO 10 años** | Medio-Alto | Medio-Alto | Medio | Medio | Medio | Medio | Medio-Bajo | Medio-Bajo |
| **Cumplimiento** | CE, EN 12966, TOPAS | MUTCD, EN 12966 | Certificaciones internacionales | Reconocimiento INVIAS | Certificaciones nacionales | Certificaciones nacionales | Certificaciones nacionales | Certificaciones nacionales |
| **Casos en Colombia** | Brasil, LATAM | Proyectos internacionales | Norteamérica | 6,000 km VIITS | México | Proyectos de integración | Proyectos de señalización | Proyectos empresariales |

---

#### 4.2.3.6. Conclusiones para CC-03

El análisis comparativo documenta un mercado maduro de paneles DMS/VMS con alternativas tecnológicas probadas en climas y condiciones similares a las del corredor Chía–Girardot. SWARCO y Daktronics representan estándares internacionales con certificaciones EN 12966. LeddarTech ofrece un enfoque innovador con tecnología LiDAR. A nivel LATAM, Seguritech y Grupo Masa tienen experiencia en despliegues regionales. A nivel nacional, CI2, Deviteck y SISLEC pueden ejecutar integración, instalación y mantenimiento local.

Las variables críticas del Capítulo 7 (LED full matrix, ubicación estratégica, ajuste automático de brillo, NTCIP, publicación automática, redundancia fibra+radio) son técnicamente alcanzables con las tecnologías documentadas. La selección final dependerá de la estrategia de adquisición del concesionario y las condiciones contractuales del proyecto.

---

### 4.2.4. CC-04: ECS/SOS — SISTEMA DE LLAMADA DE EMERGENCIA

#### 4.2.4.1. Descripción y Función del Componente

El componente CC-04, ECS/SOS (Emergency Call System), proporciona a usuarios viales capacidad de comunicación directa y bidireccional con el Centro de Control de Operaciones (CCO) ante situaciones de emergencia. Según la definición del Capítulo 7 del Entregable 1, el sistema utiliza postes de emergencia instalados cada 2 km en zonas estratégicas del corredor (cada 1 km en tramos de alta siniestralidad o baja cobertura celular), permitiendo reportar accidentes, vehículos averiados, emergencias médicas o situaciones que requieran atención inmediata. La comunicación voz sobre IP (VoIP) garantiza calidad de audio superior a sistemas analógicos tradicionales, permitiendo al operador del CCO evaluar la gravedad de la situación y despachar recursos apropiados.

El propósito es **"auxilio inmediato al usuario: capacidad de establecer un canal de voz crítico para asistencia en situaciones de crisis"**.

#### 4.2.4.2. Variables Críticas de Diseño (según Capítulo 7, Entregable 1)

| Variable | Especificación | Justificación (Capítulo 7) |
|----------|---------------|---------------------------|
| Distancia entre Postes | 2 km en zonas estándar; 1 km en tramos de alta siniestralidad o baja cobertura celular | Cobertura garantizada en zonas rurales sin señal celular |
| Visibilidad | Doble cara (visibles desde ambos sentidos de la vía) | Acceso rápido desde cualquier dirección |
| Comunicación | VoIP (SIP sobre red IP) | Calidad de audio superior a analógico |
| Identificación | GPS exacto del poste activado | Ubicación precisa para despacho de recursos |
| Calidad de Servicio | QoS garantizada para tráfico de voz | Prioridad de comunicación de emergencia |
| Respaldo de Comunicaciones | 4G/5G ante falla de fibra óptica | Continuidad operativa |
| Alimentación | Solar con baterías de respaldo | Autonomía de 7 días ante falla de red eléctrica |
| Integración | Con CCTV (cámara más cercana) y DMS/VMS (mensaje automático) | Visualización de escena y alerta a otros conductores |
| Reducción de Tiempo de Reporte | De 15 min a menos de 2 min | Respuesta más rápida de servicios de emergencia |

#### 4.2.4.3. Ficha Técnica de Referencia (validada contra Capítulo 7)

| Parámetro | Valor |
|-----------|-------|
| Código | CC-04 |
| Nombre | Sistema de Llamada de Emergencia (ECS/SOS) |
| Tipo | Hardware de campo (postes de emergencia) + Software de comunicación VoIP |
| Subsistema | Gestión de Tráfico y Seguridad Vial / Emergencias |
| Función Principal | Comunicación bidireccional voz entre usuario en vía y operador del CCO ante emergencias |
| Campos de Aplicación | Todos los tramos, con mayor densidad en zonas rurales, túneles, puentes y zonas de alta siniestralidad |
| Variables Medidas | Ubicación GPS, tipo de emergencia, tiempo de respuesta, calidad de comunicación |
| Ciclo de Vida Esperado | 10-12 años (postes); 7-10 años (electrónica de comunicación) |
| Normativa Aplicable | ISO 14813-1, NTCIP, SIP/RTP, IEEE 802.3bt |

---

#### 4.2.4.4. Referencias del Mercado: Proveedores y Soluciones

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Kapsch TrafficCom AG** | Austria | Viena | ITS, Tunnel Management | **DYNAC® Tunnel Management** — Sistema de comunicación de emergencia para túneles, integrado con CCTV, SCADA, VMS. | Autopista al Mar 1, Colombia. Túneles de 4.6 km con sistemas de emergencia integrados. | 2021 | https://www.kapsch.net/en/press/releases/ktc-20210505-pr-en |
| 2 | **Siemens AG** | Alemania | Múnich | Movilidad, Infraestructura | **Siemens Xcelerator for Mobility** — Sistemas de comunicación de emergencia para infraestructura vial, integración con centros de control. | Proyectos de movilidad en Bogotá (Accesos Norte) y corredores LATAM. | 2024 | https://www.siemens.com/global/en.html |
| 3 | **Indra Group** | España | Madrid | ITS, Traffic Management | **Indra Mobility — Emergency Management** — Sistemas de gestión de emergencias en infraestructura vial, comunicación VoIP, centros de control. | Sistema de gestión de tráfico y túneles en Bogotá (Accesos Norte). | 2019 | https://www.indracompany.com |

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, Seguridad Vial | **VIITS — Vías Inteligentes** — Sistema de postes de emergencia y comunicación con CCO en 6,000 km de carreteras nacionales. | Proyecto ITS-VIITS para INVIAS, 6,000 km. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |
| 2 | **SICE** | España / México | Madrid | ITS, Tunnel Management | **SICE Tunnel Control** — Sistemas de control de túneles con comunicación de emergencia, VoIP, integración con CCTV. | Proyectos de ITS en México y España. | 2024 | https://www.sice.es |

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración, ITS | Integración de ECS/SOS con CCTV, CCO y sistemas de comunicación de emergencia. | Proyectos de integración de sistemas de emergencia en infraestructura de transporte. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, ITS | Diseño e implementación de sistemas de comunicación de emergencia, postes SOS, VoIP y redes. | Proyectos de comunicación de emergencia en infraestructura de transporte. | 2024 | https://www.deviteck.com.co |
| 3 | **SISLEC** | Colombia | Bogotá | Seguridad Electrónica | Instalación y mantenimiento de sistemas de comunicación, CCTV, control de acceso. | Proyectos de seguridad y comunicación empresarial en Bogotá. | 2024 | https://sislec.com |

---

#### 4.2.4.5. Análisis Comparativo de Soluciones ECS/SOS

| Criterio | Kapsch DYNAC® | Siemens Xcelerator | Indra Mobility | Seguritech VIITS | SICE | CI2 | Deviteck | SISLEC |
|----------|---------------|---------------------|----------------|------------------|------|-----|----------|--------|
| **Madurez** | TRL 9 — túneles, Colombia | TRL 9 — global | TRL 9 — España, Colombia | TRL 8 — 6,000 km INVIAS | TRL 9 — México, España | TRL 7 — integración local | TRL 7 — implementación local | TRL 7 — proyectos empresariales |
| **Interoperabilidad** | Integración CCTV, SCADA, VMS | Estándares abiertos | Estándares abiertos | Integrado con INVIAS | Estándares abiertos | Estándares abiertos | Estándares abiertos | Estándares abiertos |
| **Soporte Local** | Oficina Bogotá | Oficina Bogotá | Oficina Bogotá | Oficina Bogotá | México | Bogotá | Bogotá | Bogotá |
| **TCO 10 años** | Medio-Alto | Medio-Alto | Medio-Alto | Medio | Medio-Alto | Medio | Medio-Bajo | Medio-Bajo |
| **Cumplimiento** | ISO 9001, ISO 27001 | Certificaciones globales | Certificaciones globales | Reconocimiento INVIAS | Certificaciones europeas | Certificaciones nacionales | Certificaciones nacionales | Certificaciones nacionales |
| **Casos en Colombia** | Autopista al Mar, Accesos Norte | Accesos Norte | Accesos Norte | 6,000 km VIITS | México | Proyectos de integración | Proyectos de comunicación | Proyectos empresariales |

---

#### 4.2.4.6. Conclusiones para CC-04

El análisis comparativo documenta soluciones de comunicación de emergencia para infraestructura vial. Kapsch, Siemens e Indra tienen experiencia en proyectos colombianos (Accesos Norte, Autopista al Mar). Seguritech y SICE ofrecen alternativas LATAM con despliegues regionales. A nivel nacional, CI2, Deviteck y SISLEC pueden ejecutar integración e instalación local.

Las variables críticas del Capítulo 7 (postes cada 2 km / 1 km, doble cara, VoIP, GPS, QoS, respaldo 4G/5G, alimentación solar 7 días, integración CCTV/DMS, reducción de tiempo de reporte a < 2 min) son técnicamente alcanzables con las tecnologías documentadas. La selección final dependerá de la estrategia de adquisición del concesionario y las condiciones contractuales del proyecto.

---

### 4.2.5. CC-05: VDS/TDS — SISTEMA DE DETECCIÓN DE TRÁFICO

#### 4.2.5.1. Descripción y Función del Componente

El componente CC-05, VDS/TDS (Vehicle Detection System / Traffic Detection System), proporciona datos en tiempo real sobre el estado del flujo vehicular mediante sensores instalados a lo largo de los 306 km del corredor. Según la definición del Capítulo 7 del Entregable 1, el sistema mide volumen de tráfico, velocidad promedio por carril, ocupación de vía, clasificación de vehículos (livianos, buses, camiones), y detecta condiciones de congestión o flujo anómalo. Estos datos alimentan los sistemas DMS/VMS (publicación de tiempos de recorrido), CCO (monitoreo operativo), y generan información histórica para planificación de mantenimiento y ampliaciones de capacidad.

El propósito es **"caracterización dinámica del flujo: capacidad de cuantificar y clasificar el volumen vehicular para decisiones operativas"**.

#### 4.2.5.2. Variables Críticas de Diseño (según Capítulo 7, Entregable 1)

| Variable | Especificación | Justificación (Capítulo 7) |
|----------|---------------|---------------------------|
| Variables Medidas | Volumen, velocidad promedio por carril, ocupación, clasificación de vehículos (livianos, buses, camiones) | Datos completos para gestión de tráfico y planificación |
| Tecnologías de Detección | Radar Doppler, cámaras con analítica, sensores magnéticos inductivos | Adaptación según características de cada tramo |
| Distancia entre Estaciones | 2 km en promedio; 500 m en zonas de alta congestión | Cobertura según densidad de tráfico |
| Procesamiento | Procesador de tráfico local que agrega datos de múltiples sensores | Transmisión de información procesada al CCO |
| Intervalos de Agregación | 1 min (tiempo real), 15 min (reportes), 1 hora (planificación) | Diferentes usos: operación, reportes, planificación |
| Compensación Climática | Ajuste de algoritmos según condiciones meteorológicas (lluvia, neblina) | Precisión en condiciones adversas |
| Integración | Con sistema Meteo y DMS/VMS | Ajuste automático de algoritmos y publicación de tiempos de recorrido |

#### 4.2.5.3. Ficha Técnica de Referencia (validada contra Capítulo 7)

| Parámetro | Valor |
|-----------|-------|
| Código | CC-05 |
| Nombre | Sistema de Detección de Tráfico (VDS/TDS) |
| Tipo | Hardware de campo (sensores radar, cámaras, inductivos) + Software de procesamiento de tráfico |
| Subsistema | Gestión de Tráfico y Seguridad Vial / Información al Usuario |
| Función Principal | Medición en tiempo real de volumen, velocidad, ocupación, clasificación de vehículos y detección de congestión |
| Campos de Aplicación | Todos los tramos, con mayor densidad en zonas de alta congestión, intercambiadores y áreas de servicio |
| Variables Medidas | Volumen vehicular, velocidad promedio por carril, ocupación, clasificación (livianos, buses, camiones), congestión |
| Ciclo de Vida Esperado | 7-10 años (sensores); 10-15 años (infraestructura de montaje) |
| Normativa Aplicable | ISO 14813-1, NTCIP 1202, IEEE 1512 |

---

#### 4.2.5.4. Referencias del Mercado: Proveedores y Soluciones

**PROVEEDORES INTERNACIONALES**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Kapsch TrafficCom AG** | Austria | Viena | ITS, Tolling, Traffic Data | **EcoTrafiX™ Traffic Data** — Sistema de detección de tráfico, clasificación de vehículos, integración con ATMS. | Palmillas-Apaseo Highway, México; Accesos Norte, Bogotá. | 2025 | https://www.kapsch.net/en/press/releases/ktc-20250805-pr-en |
| 2 | **Siemens AG** | Alemania | Múnich | Movilidad, Infraestructura | **Siemens Mobility — Traffic Detection** — Sensores de tráfico, clasificación de vehículos, integración con sistemas de control. | Proyectos de movilidad en Bogotá y corredores LATAM. | 2024 | https://www.siemens.com/global/en.html |
| 3 | **WIM Technologies** | Australia | Melbourne | Weigh-in-Motion, Traffic Detection | **WIM Traffic Sensors** — Sensores de pesaje dinámico y detección de tráfico para clasificación vehicular. | Proyectos de peaje y control de tráfico en Australia y Asia. | 2024 | https://www.wim-technologies.com |

**PROVEEDORES LATAM**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **Seguritech Colombia / México** | México / Colombia | Bogotá | ITS, Traffic Management | **VIITS — Vías Inteligentes** — Sistema de detección de tráfico, conteo vehicular, clasificación y publicación de tiempos de recorrido en 6,000 km. | Proyecto ITS-VIITS para INVIAS, 6,000 km. | 2022 | https://www.ventasdeseguridad.com/novedades/ultimas-noticias/21-empresas/22346-seguritech-implementa-centro-de-control-y-monitoreo-vial-en-colombia.html |
| 2 | **Grupo Masa** | México | Ciudad de México | ITS, Construcción | Sistemas de detección de tráfico y control de flujo vehicular para corredores viales. | Corredores viales en México y proyectos de infraestructura en LATAM. | 2024 | https://www.grupomasa.com.mx |

**PROVEEDORES NACIONALES (COLOMBIA)**

| # | Empresa | País | Ciudad Sede | Especialidad | Solución Tecnológica | Caso de Uso / Proyecto Implementado | Año | Web |
|---|---------|------|-------------|--------------|---------------------|--------------------------------------|-----|-----|
| 1 | **CI2 — Compañía Internacional de Integración** | Colombia | Bogotá | Integración, ITS | Integración de VDS/TDS con CCTV, DMS/VMS y CCO. Sistemas de detección de tráfico para corredores viales. | Proyectos de integración de detección de tráfico en infraestructura de transporte. | 2024 | https://www.ci2.co |
| 2 | **Deviteck** | Colombia | Bogotá | Tecnología, ITS | Diseño e implementación de sistemas de detección de tráfico, sensores, procesadores de tráfico y redes. | Proyectos de detección de tráfico en infraestructura de transporte en Colombia. | 2024 | https://www.deviteck.com.co |
| 3 | **SIT Ltda.** | Colombia | Chía, Cundinamarca | ITS, Simulación | Consultoría e integración de sistemas de detección de tráfico, modelado de flujo vehicular. | Corredores de Cundinamarca, modelado de tráfico y detección de anomalías. | 2019 | https://www.sit-colombia.com/ |

---

#### 4.2.5.5. Análisis Comparativo de Soluciones VDS/TDS

| Criterio | Kapsch EcoTrafiX™ | Siemens Mobility | WIM Technologies | Seguritech VIITS | Grupo Masa | CI2 | Deviteck | SIT Ltda. |
|----------|-------------------|------------------|-------------------|------------------|------------|-----|----------|-----------|
| **Madurez** | TRL 9 — desplegado en 50+ países | TRL 9 — global | TRL 9 — Australia, Asia | TRL 8 — 6,000 km con INVIAS | TRL 8 — corredores México | TRL 7 — integración local | TRL 7 — implementación local | TRL 7 — consultoría y modelado |
| **Interoperabilidad** | NTCIP, API REST, integración ATMS | Estándares abiertos | Estándares abiertos | Integrado con INVIAS | Estándares abiertos | Estándares abiertos | Estándares abiertos | Aimsun, estándares abiertos |
| **Soporte Local** | Oficina Bogotá | Oficina Bogotá | Distribuidor internacional | Oficina Bogotá | México | Bogotá | Bogotá | Chía, Cundinamarca |
| **TCO 10 años** | Medio-Alto | Medio-Alto | Medio | Medio | Medio | Medio | Medio-Bajo | Bajo-Medio |
| **Cumplimiento** | ISO 9001, ISO 27001 | Certificaciones globales | Certificaciones internacionales | Reconocimiento INVIAS | Certificaciones nacionales | Certificaciones nacionales | Certificaciones nacionales | Experiencia local |
| **Casos en Colombia** | Palmillas-Apaseo, Accesos Norte | Accesos Norte | Australia, Asia | 6,000 km VIITS | México | Proyectos de integración | Proyectos de detección | Corredores de Cundinamarca |

---

#### 4.2.5.6. Conclusiones para CC-05

El análisis comparativo documenta soluciones de detección de tráfico con distintos enfoques tecnológicos: Kapsch y Siemens con sistemas integrados de gestión de tráfico, WIM Technologies con sensores especializados. A nivel LATAM, Seguritech y Grupo Masa tienen experiencia en despliegues regionales. A nivel nacional, CI2, Deviteck y SIT pueden ejecutar integración, instalación y consultoría local.

Las variables críticas del Capítulo 7 (volumen, velocidad, ocupación, clasificación de vehículos, radar Doppler + cámaras + inductivos, estaciones cada 2 km / 500 m, agregación 1 min/15 min/1 hora, compensación climática, integración con Meteo y DMS/VMS) son técnicamente alcanzables con las tecnologías documentadas. La selección final dependerá de la estrategia de adquisición del concesionario y las condiciones contractuales del proyecto.

---

*(Continúa con CC-06 a CC-42 en secciones siguientes...)*
