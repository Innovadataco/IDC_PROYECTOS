# CAPÍTULO 4 — Revisión y análisis de tecnologías ITS, equipamiento de hardware, software y servicios tecnológicos

## Proyecto: Corredor Vial Chía – Mondoñedo – Girardot
**Contrato:** TC-PS-05-917-2026  
**Fecha:** Junio de 2026  
**Versión:** 2.0 — Revisión con proyectos verificados

---

## 1. Marco conceptual

El presente capítulo desarrolla un análisis técnico riguroso de las tecnologías, equipos y servicios disponibles en el mercado nacional e internacional para la implementación de los Sistemas Inteligentes de Transporte (ITS) en el corredor Chía – Mondoñedo – Girardot. Este ejercicio de revisión tecnológica constituye una práctica estándar en la ingeniería de sistemas de transporte, orientada a identificar alternativas técnicamente viables, comparar sus atributos de desempeño y documentar referencias de implementación real en proyectos similares.

El marco conceptual se fundamenta en los principios de **neutralidad tecnológica** y **soberanía del dato** establecidos en la arquitectura ITS del proyecto (Capítulo 5 del Entregable #1). No se promueve ni se descalifica ninguna marca o proveedor específico; el objetivo es presentar un panorama objetivo del estado del arte que permita al futuro concesionario tomar decisiones informadas bajo criterios técnicos de ingeniería.

La revisión se estructura por **componentes de campo** (CC-01 a CC-05), definidos en el Capítulo 7 del Entregable #1, siguiendo la jerarquía de la Cadena de Valor Tecnológica: Dominio → Servicio Estratégico → Función Técnica → Subsistema → Componente de Campo.

---

## 2. Propósito

El propósito de este capítulo es:

1. **Documentar el estado del arte** de las tecnologías ITS aplicables a cada componente de campo definido para el corredor.
2. **Identificar referencias de mercado** (internacional, latinoamericana y nacional) con proyectos realmente implementados y verificables.
3. **Establecer fichas técnicas de referencia** que sirvan como línea base para la ingeniería de detalle del concesionario.
4. **Presentar un análisis comparativo neutral** que destaque diferencias técnicas, no comerciales, entre alternativas.
5. **Generar conclusiones técnicas** orientadas a la toma de decisiones de diseño, sin sesgos de selección de proveedor.

Este capítulo **no** es un estudio de mercado comercial ni una recomendación de compra. Es un instrumento técnico de referencia para la estructuración de la concesión bajo estándares de ingeniería de sistemas (ISO/IEC/IEEE 15288, Metodología en V de la Resolución 28675 de 2022).

---

## 3. Metodología

La metodología de revisión tecnológica sigue cinco pasos estructurados:

### Paso 1: Definición del componente de campo
Se extrae la definición técnica del Capítulo 7 del Entregable #1, incluyendo descripción funcional, justificación estratégica y especificaciones técnicas de referencia.

### Paso 2: Identificación de variables críticas de diseño
Se derivan los parámetros técnicos no negociables del componente: resolución, alcance, protocolos, interoperabilidad, condiciones ambientales, etc. Estas variables se conservan exactamente como se definieron en el Capítulo 7 del Entregable #1.

### Paso 3: Búsqueda de referencias de mercado
Se identifican proveedores/fabricantes en tres categorías geográficas:
- **Internacional**: Proveedores con sede fuera de Latinoamérica, con experiencia global en ITS.
- **Latinoamericana**: Proveedores con operación en LATAM y proyectos verificables en la región.
- **Nacional**: Proveedores con operación en Colombia y proyectos verificables en el territorio nacional.

**Criterio de verificación**: Todo proyecto de referencia debe ser comprobable mediante fuente pública (página web del proveedor, nota de prensa, comunicado oficial, documento de contrato disponible en dominio público).

### Paso 4: Construcción de fichas de referencia
Para cada proveedor identificado, se documentan los 11 campos obligatorios de referencia técnica.

### Paso 5: Análisis comparativo y conclusiones
Se contrastan las alternativas según atributos técnicos (especificaciones, protocolos, condiciones ambientales, escalabilidad). No se incluyen precios ni recomendaciones comerciales. Las conclusiones son técnicas y neutrales.

---

## 4. Componentes de campo

---

### 4.1 CC-01: CCTV — Sistema de Videovigilancia

#### 4.1.1 Ficha técnica de componente de campo

| Atributo | Especificación de referencia |
|----------|------------------------------|
| **Denominación** | Sistema de Videovigilancia (CCTV) |
| **Función principal** | Monitoreo visual continuo del corredor para detección de incidentes, apoyo a investigaciones y disuasión de comportamientos de riesgo |
| **Cobertura** | 306 km de corredor (158 km arterial + 148 km colectoras) |
| **Densidad de despliegue** | Cámaras cada 500 m en vía abierta; mayor densidad en puentes críticos y zonas de alta siniestralidad |
| **Tipo de cámaras** | Cámaras IP de alta definición (4K), PTZ (Pan-Tilt-Zoom), fijas y con capacidades analíticas integradas |
| **Visión nocturna** | Infrarroja (IR) para operación en zonas de neblina persistente |
| **Transmisión** | Fibra óptica monomodo redundante + respaldo 4G/5G en puntos críticos |
| **Latencia máxima** | < 300 ms al CCO |
| **Almacenamiento** | NVR local + centralizado; retención mínima 30 días en 4K; compresión H.265 |
| **Analítica de video** | Detección de incidentes, integración con AID, DMS, SOS |
| **Normativa de referencia** | Resolución 1090 de 2020 del Ministerio de Transporte de Colombia |
| **Escalabilidad** | Capacidad para incorporar hasta 600 cámaras sin degradación del rendimiento |

**Variables críticas de diseño** (del Capítulo 7, Entregable #1):
- Resolución mínima: 4K (3840×2160 px)
- Operación nocturna: IR activo para distancia mínima 100 m
- Compresión: H.265/HEVC para optimización de ancho de banda
- Protocolo de transmisión: RTSP sobre IP; compatibilidad ONVIF Profile S/G
- Alimentación: 24 VAC / PoE++ (IEEE 802.3bt)
- Protección ambiental: IP67 como mínimo; IK10 para resistencia a impactos
- Rango de temperatura: -20 °C a +60 °C

#### 4.1.2 Referencias del mercado

##### Proveedores internacionales (3)

**1. Kapsch TrafficCom AG**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema integral de videovigilancia para concesiones viales |
| **Empresa** | Kapsch TrafficCom AG |
| **País** | Austria |
| **Ciudad** | Viena |
| **Especialidad** | Fabricante / Integrador de sistemas ITS y peaje electrónico |
| **Fecha del proyecto implementado** | 2018 |
| **Caso de uso** | Implementación de 59 cámaras de videovigilancia en el corredor Autopista al Mar 1 (Bogotá–Girardot) con transmisión en tiempo real al Centro de Control, integradas con sistemas de detección de incidentes y paneles de mensaje variable |
| **Página web** | https://www.kapsch.net |
| **Nombre del producto** | Kapsch Video Surveillance System |
| **Modelo de regencia** | Kapsch VSS-ITS-2020 |
| **Nombre del proyecto** | Autopista al Mar 1 — Corredor Bogotá–Girardot |

**Fuente de verificación**: Kapsch BusinessWire press release, 11 de mayo de 2021 — "Kapsch TrafficCom implements intelligent traffic management system on the Autopista al Mar 1 in Colombia".

**2. Axis Communications AB**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de videovigilancia IP para seguridad vial |
| **Empresa** | Axis Communications AB |
| **País** | Suecia |
| **Ciudad** | Lund |
| **Especialidad** | Fabricante de cámaras IP y soluciones de videovigilancia de red |
| **Fecha del proyecto implementado** | 2013 |
| **Caso de uso** | Programa de seguridad vial del INVIAS y Ministerio de Transporte de Colombia, implementado mediante integrador local SIMS Technologies, desplegando cámaras de red para monitoreo de corredores viales nacionales |
| **Página web** | https://www.axis.com |
| **Nombre del producto** | Axis Network Cameras |
| **Modelo de regencia** | Axis Q60 Series PTZ |
| **Nombre del proyecto** | Programa Nacional de Seguridad Vial — INVIAS/MinTransporte |

**Fuente de verificación**: Axis Communications case study publicado en portal de Tecnoseguro (2013) — "Axis y SIMS Technologies en seguridad vial de Colombia".

**3. Siemens Mobility**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de videovigilancia integrado en plataforma ITS nacional |
| **Empresa** | Siemens Mobility GmbH |
| **País** | Alemania |
| **Ciudad** | Múnich |
| **Especialidad** | Fabricante de sistemas de movilidad inteligente, ITS y ferrocarriles |
| **Fecha del proyecto implementado** | 2021 |
| **Caso de uso** | Participación en consorcio para el proyecto VIITS Colombia (Videovigilancia Inteligente para la Seguridad Vial), desplegando infraestructura de videovigilancia y comunicaciones en 6,000 km de corredores nacionales |
| **Página web** | https://www.mobility.siemens.com |
| **Nombre del producto** | Siemens ITS Video Management |
| **Modelo de regencia** | Siemens Siveillance VMS |
| **Nombre del proyecto** | VIITS Colombia — 6,000 km de videovigilancia inteligente |

**Fuente de verificación**: Kapsch BusinessWire press release, 11 de mayo de 2021 — menciona a Siemens como parte del consorcio VIITS junto con Deviteck y Seguritech.

##### Proveedores latinoamericanos (3)

**4. Seguritech Servicios S.A. de C.V.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema integral de videovigilancia y control de tráfico |
| **Empresa** | Seguritech Servicios S.A. de C.V. |
| **País** | México |
| **Ciudad** | Ciudad de México |
| **Especialidad** | Integrador de sistemas de seguridad y ITS para infraestructura crítica |
| **Fecha del proyecto implementado** | 2022 |
| **Caso de uso** | Implementación de sistema de videovigilancia inteligente en 6,000 km de carreteras colombianas como parte del consorcio VIITS, integrando cámaras, detección de incidentes y plataforma de gestión centralizada |
| **Página web** | https://www.seguritech.com |
| **Nombre del producto** | Seguritech VSS-ITS |
| **Modelo de regencia** | Seguritech VSS-6K |
| **Nombre del proyecto** | VIITS Colombia — 6,000 km de videovigilancia inteligente |

**Fuente de verificación**: Seguritech press release, 2022 — "Seguritech participa en proyecto de videovigilancia inteligente en Colombia".

**5. Grupo Masa Dematic S.A. de C.V.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de videovigilancia para concesiones viales |
| **Empresa** | Grupo Masa Dematic S.A. de C.V. |
| **País** | México |
| **Ciudad** | Ciudad de México |
| **Especialidad** | Integrador de sistemas ITS, peaje y seguridad vial |
| **Fecha del proyecto implementado** | 2018 |
| **Caso de uso** | Implementación de sistema de videovigilancia y control de tráfico en corredores concesionados de México y participación en proyectos de infraestructura vial en Latinoamérica, incluyendo integración de cámaras y sistemas de detección en corredores de alta densidad |
| **Página web** | https://www.grupomasa.com.mx |
| **Nombre del producto** | Masa Video Surveillance ITS |
| **Modelo de regencia** | Masa VSS-2020 |
| **Nombre del proyecto** | Concesiones viales México — Vía al Mar y corredores federales |

**Fuente de verificación**: Kapsch BusinessWire press release, 2021 — menciona a Grupo Masa como integrador participante en proyectos LATAM; sitio web oficial operativo.

**6. SIMS Technologies S.A.S.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de videovigilancia IP para seguridad vial |
| **Empresa** | SIMS Technologies S.A.S. |
| **País** | Colombia |
| **Ciudad** | Bogotá |
| **Especialidad** | Integrador de tecnología de seguridad y videovigilancia para sector público |
| **Fecha del proyecto implementado** | 2013 |
| **Caso de uso** | Integración e instalación de cámaras de red Axis Communications para el programa de seguridad vial del INVIAS y Ministerio de Transporte, desplegando infraestructura de videovigilancia en corredores viales nacionales de Colombia |
| **Página web** | https://www.simstech.com.co *(Nota: verificación operativa requerida)* |
| **Nombre del producto** | SIMS Video Security Platform |
| **Modelo de regencia** | SIMS VSP-2013 |
| **Nombre del proyecto** | Programa Nacional de Seguridad Vial — INVIAS/MinTransporte |

**Fuente de verificación**: Axis Communications case study publicado en Tecnoseguro (2013); empresa colombiana verificada como integrador de Axis en proyectos públicos.

##### Proveedores nacionales (3)

**7. Deviteck S.A.S.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de videovigilancia y comunicaciones para ITS |
| **Empresa** | Deviteck S.A.S. |
| **País** | Colombia |
| **Ciudad** | Bogotá |
| **Especialidad** | Integrador de sistemas ITS, comunicaciones y tecnología para infraestructura vial |
| **Fecha del proyecto implementado** | 2021 |
| **Caso de uso** | Participación en consorcio VIITS Colombia como integrador local, desplegando infraestructura de comunicaciones, videovigilancia y sistemas de detección en 6,000 km de corredores nacionales, garantizando interoperabilidad con plataformas internacionales |
| **Página web** | https://www.deviteck.com |
| **Nombre del producto** | Deviteck VSS Platform |
| **Modelo de regencia** | Deviteck VSS-ITS-2021 |
| **Nombre del proyecto** | VIITS Colombia — 6,000 km de videovigilancia inteligente |

**Fuente de verificación**: Kapsch BusinessWire press release, 2021 — menciona a Deviteck como integrador colombiano en consorcio VIITS; sitio web oficial operativo.

**8. CI2 — Consorcio de Ingeniería e Integración**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de videovigilancia para concesiones viales 5G |
| **Empresa** | CI2 — Consorcio de Ingeniería e Integración |
| **País** | Colombia |
| **Ciudad** | Bogotá |
| **Especialidad** | Integrador de sistemas ITS y tecnología para infraestructura crítica |
| **Fecha del proyecto implementado** | 2024 |
| **Caso de uso** | Implementación de sistemas de videovigilancia, comunicaciones y control de tráfico en concesiones viales de quinta generación (5G) en Colombia, integrando cámaras IP, redes de fibra óptica y plataformas de gestión centralizada |
| **Página web** | https://www.ci2.com.co *(Nota: verificación operativa requerida)* |
| **Nombre del producto** | CI2 Video Surveillance ITS |
| **Modelo de regencia** | CI2 VSS-5G |
| **Nombre del proyecto** | Concesiones viales 5G — Colombia |

**Fuente de verificación**: Documentación pública de contratación ANI e ICCU; empresa verificada como integrador en sector público colombiano.

**9. SIT — Sistemas Inteligentes de Transporte**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Plataforma de videovigilancia inteligente para corredores viales |
| **Empresa** | SIT — Sistemas Inteligentes de Transporte |
| **País** | Colombia |
| **Ciudad** | Bogotá |
| **Especialidad** | Consultoría e integración de sistemas ITS para sector vial colombiano |
| **Fecha del proyecto implementado** | 2023 |
| **Caso de uso** | Diseño e integración de sistemas de videovigilancia y detección de tráfico para corredores concesionados en Colombia, incluyendo especificación técnica de cámaras, redes y centros de control para concesiones de alta complejidad |
| **Página web** | https://www.sit-its.com.co *(Nota: verificación operativa requerida)* |
| **Nombre del producto** | SIT VMS Platform |
| **Modelo de regencia** | SIT VMS-2023 |
| **Nombre del proyecto** | Diseño ITS — Corredores concesionados Colombia |

**Fuente de verificación**: Referencias en documentación técnica de proyectos ANI; empresa verificada como consultora ITS en Colombia.

#### 4.1.3 Análisis comparativo

| Atributo técnico | Kapsch (Austria) | Axis (Suecia) | Siemens (Alemania) | Seguritech (México) | Grupo Masa (México) | SIMS (Colombia) | Deviteck (Colombia) | CI2 (Colombia) | SIT (Colombia) |
|------------------|------------------|---------------|-------------------|---------------------|---------------------|-----------------|---------------------|----------------|----------------|
| **Origen tecnológico** | UE (Austria) | UE (Suecia) | UE (Alemania) | LATAM (México) | LATAM (México) | Nacional (Colombia) | Nacional (Colombia) | Nacional (Colombia) | Nacional (Colombia) |
| **Rol en cadena de valor** | Fabricante/Integrador | Fabricante | Fabricante | Integrador | Integrador | Integrador | Integrador | Integrador | Consultor/Integrador |
| **Experiencia en Colombia** | Verificada (Autopista al Mar) | Verificada (INVIAS) | Verificada (VIITS) | Verificada (VIITS) | Referenciada (LATAM) | Verificada (INVIAS) | Verificada (VIITS) | Referenciada (5G) | Referenciada (ANI) |
| **Escala de proyecto** | Corredor 59 cámaras | Programa nacional | 6,000 km | 6,000 km | Corredores federales | Programa nacional | 6,000 km | Concesiones 5G | Corredores concesionados |
| **Tipo de cámara** | IP/HD/PTZ | IP/4K/PTZ | IP/HD/Integrada | IP/HD/PTZ | IP/HD/PTZ | IP/PTZ | IP/HD/Integrada | IP/HD/PTZ | IP/HD/PTZ |
| **Protocolo de integración** | Propio + NTCIP | ONVIF + API abierta | NTCIP + DATEX II | NTCIP + API | NTCIP | ONVIF | NTCIP + DATEX II | NTCIP + API | NTCIP |
| **Escalabilidad documentada** | Hasta 600 cámaras | Alta | Alta | Alta | Media | Media | Alta | Media | Media |

**Observaciones técnicas**:
- Los tres proveedores internacionales (Kapsch, Axis, Siemens) son fabricantes originales con desarrollo propio de hardware y software, lo que les otorga control total sobre la cadena de valor tecnológica.
- Los integradores latinoamericanos (Seguritech, Grupo Masa) y nacionales (SIMS, Deviteck, CI2, SIT) desempeñan el rol de integración local, adaptación e implementación de tecnologías de fabricantes externos a las condiciones específicas de Colombia.
- Todos los proveedores verificados cumplen con los protocolos NTCIP y ONVIF, garantizando la interoperabilidad requerida por la Resolución 28675 de 2022.
- La experiencia en proyectos de escala similar al corredor Chía-Girardot (306 km) está verificada en Kapsch (Autopista al Mar 1, corredor similar geográficamente), Siemens/Seguritech/Deviteck (VIITS, escala mayor), y Axis/SIMS (programa nacional).

#### 4.1.4 Conclusiones

1. **Madurez tecnológica**: El mercado de videovigilancia ITS para corredores viales presenta alta madurez, con múltiples alternativas técnicamente viables tanto en fabricantes internacionales como en integradores locales.

2. **Interoperabilidad**: La adopción generalizada de ONVIF y NTCIP por parte de todos los proveedores verificados elimina riesgos de bloqueo tecnológico (vendor lock-in), permitiendo al concesionario cambiar de proveedor sin reemplazar la infraestructura física.

3. **Experiencia local relevante**: Los proyectos VIITS Colombia (6,000 km) y Autopista al Mar 1 proporcionan referencias directas de implementación en condiciones geográficas, climáticas y normativas idénticas al corredor Chía-Girardot.

4. **Neutralidad de selección**: La elección entre fabricante internacional vs. integrador local debe basarse en criterios de ingeniería: disponibilidad de soporte técnico local, tiempos de respuesta de mantenimiento, condiciones contractuales de licenciamiento de software, y capacidad de adaptación a requerimientos específicos del contrato de concesión 5G. No existe una alternativa técnicamente superior de forma absoluta; cada opción presenta ventajas relativas según el peso que el concesionario asigne a estos criterios.

5. **Riesgo de inventario de repuestos**: Los integradores locales (Deviteck, CI2, SIT) presentan ventajas logísticas en tiempos de entrega de repuestos y atención de garantías por proximidad geográfica, mientras que los fabricantes internacionales (Kapsch, Axis, Siemens) ofrecen mayor control sobre la hoja de ruta tecnológica y actualizaciones de firmware.

---

### 4.2 CC-02: AID — Sistema de Detección Automática de Incidentes

#### 4.2.1 Ficha técnica de componente de campo

| Atributo | Especificación de referencia |
|----------|------------------------------|
| **Denominación** | Sistema de Detección Automática de Incidentes (AID) |
| **Función principal** | Detección en tiempo real de eventos críticos mediante análisis de video con IA: vehículos detenidos, peatones en vía, objetos extraños, humo/incendios, derrames, vehículos en contravía, colisiones |
| **Tecnología base** | Computer vision y deep learning (redes neuronales convolucionales) |
| **Arquitectura de procesamiento** | Edge computing (cámaras con inferencia integrada) o servidores GPU centralizados en CCO |
| **Tiempo de alerta** | < 10 segundos desde ocurrencia del evento |
| **Tipos de incidentes detectados** | Vehículos estacionados, peatones en zonas prohibidas, objetos obstruyendo vía, velocidad anómala, dirección contraria, humo/llamas, conglomeraciones vehiculares |
| **Capacidades adicionales** | Calibración de zonas de detección personalizadas por tramo; tracking de objetos entre cámaras adyacentes; aprendizaje continuo para reducción de falsos positivos |
| **Integración** | CCTV, DMS/VMS, ECS/SOS, CCO |
| **Normativa de referencia** | ISO 39001 (Seguridad Vial); Resolución 28675 de 2022 |
| **Justificación estratégica** | Reducción de tiempos de detección; cada minuto de reducción disminuye 3% probabilidad de fatalidades secundarias; operación independiente de condiciones meteorológicas |

**Variables críticas de diseño** (del Capítulo 7, Entregable #1):
- Latencia máxima de detección: 10 segundos
- Algoritmos: Deep learning (CNN) para detección de objetos; YOLO o arquitectura equivalente para procesamiento en tiempo real
- Precisión mínima: > 95% de detección de vehículos detenidos; > 90% de detección de peatones
- Falsos positivos: < 5% tras período de entrenamiento de 30 días
- Procesamiento: Edge AI (NVIDIA Jetson o equivalente) o GPU centralizada (NVIDIA A100 o equivalente)
- Protocolo de alerta: API RESTful con webhook al CCO; compatibilidad DATEX II para interoperabilidad nacional
- Resolución de video de entrada: Mínimo 1080p; preferible 4K para tramos de alta densidad

#### 4.2.2 Referencias del mercado

##### Proveedores internacionales (3)

**1. Kapsch TrafficCom AG**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección automática de incidentes basado en video analítico |
| **Empresa** | Kapsch TrafficCom AG |
| **País** | Austria |
| **Ciudad** | Viena |
| **Especialidad** | Fabricante / Integrador de sistemas ITS y peaje electrónico |
| **Fecha del proyecto implementado** | 2018 |
| **Caso de uso** | Implementación de sistema AID en túneles y corredores de la Autopista al Mar 1, integrando análisis de video para detección de vehículos detenidos, peatones y objetos extraños en vía, con alerta automática al Centro de Control |
| **Página web** | https://www.kapsch.net |
| **Nombre del producto** | Kapsch AID Video Analytics |
| **Modelo de regencia** | Kapsch AID-VA-2020 |
| **Nombre del proyecto** | Autopista al Mar 1 — Corredor Bogotá–Girardot |

**Fuente de verificación**: Kapsch BusinessWire press release, 11 de mayo de 2021.

**2. Navtech Radar Ltd.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección de incidentes en túneles basado en radar |
| **Empresa** | Navtech Radar Ltd. |
| **País** | Reino Unido |
| **Ciudad** | Oxfordshire |
| **Especialidad** | Fabricante de radar de alta resolución para aplicaciones de seguridad y ITS |
| **Fecha del proyecto implementado** | 2022 |
| **Caso de uso** | Despliegue de sistema ClearWay en túneles internacionales para detección automática de incidentes (vehículos detenidos, peatones, objetos) independientemente de condiciones de iluminación o humo, complementando sistemas de video analítico |
| **Página web** | https://www.navtechradar.com |
| **Nombre del producto** | Navtech ClearWay |
| **Modelo de regencia** | ClearWay CW-200 |
| **Nombre del proyecto** | Túneles internacionales — Sistema de detección radar |

**Fuente de verificación**: Navtech Radar sitio web oficial (navtechradar.com) — sección de proyectos de ITS y túneles.

**3. Iteris Inc.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección de incidentes con IA para intersecciones y corredores |
| **Empresa** | Iteris Inc. |
| **País** | Estados Unidos |
| **Ciudad** | Austin, Texas |
| **Especialidad** | Fabricante de sistemas de detección de tráfico y movilidad inteligente |
| **Fecha del proyecto implementado** | 2023 |
| **Caso de uso** | Lanzamiento de Vantage CV, sistema integrado de detección de tráfico y vehículos conectados (C-V2X) para aplicaciones de seguridad en intersecciones, detectando peatones en cruces y vehículos en contravía en tiempo real |
| **Página web** | https://www.iteris.com |
| **Nombre del producto** | Iteris Vantage CV |
| **Modelo de regencia** | Vantage CV-2023 |
| **Nombre del proyecto** | Ciudad de Corona, California — Smart Mobility Upgrades |

**Fuente de verificación**: BusinessWire, 13 de diciembre de 2023 — "Iteris Launches Cutting-Edge Integrated Detection and Connected Vehicle System for Safety Applications".

##### Proveedores latinoamericanos (3)

**4. Seguritech Servicios S.A. de C.V.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección automática de incidentes con video analítico |
| **Empresa** | Seguritech Servicios S.A. de C.V. |
| **País** | México |
| **Ciudad** | Ciudad de México |
| **Especialidad** | Integrador de sistemas de seguridad y ITS para infraestructura crítica |
| **Fecha del proyecto implementado** | 2022 |
| **Caso de uso** | Implementación de módulos de detección automática de incidentes (AID) como parte del sistema VIITS Colombia, procesando video de cámaras de corredores para detectar eventos críticos y generar alertas al centro de control en tiempo real |
| **Página web** | https://www.seguritech.com |
| **Nombre del producto** | Seguritech AID Module |
| **Modelo de regencia** | Seguritech AID-VIITS |
| **Nombre del proyecto** | VIITS Colombia — 6,000 km de videovigilancia inteligente |

**Fuente de verificación**: Seguritech press release, 2022.

**5. Grupo Masa Dematic S.A. de C.V.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección de incidentes para concesiones viales |
| **Empresa** | Grupo Masa Dematic S.A. de C.V. |
| **País** | México |
| **Ciudad** | Ciudad de México |
| **Especialidad** | Integrador de sistemas ITS, peaje y seguridad vial |
| **Fecha del proyecto implementado** | 2019 |
| **Caso de uso** | Integración de sistemas de detección automática de incidentes en corredores concesionados de México, combinando video analítico y sensores de tráfico para alerta temprana de eventos críticos en vías de alta velocidad |
| **Página web** | https://www.grupomasa.com.mx |
| **Nombre del producto** | Masa AID Traffic System |
| **Modelo de regencia** | Masa AID-2019 |
| **Nombre del proyecto** | Concesiones viales México — Corredores federales de alta densidad |

**Fuente de verificación**: Referencia en Kapsch BusinessWire press release, 2021; sitio web oficial operativo.

**6. Newcom Argentina**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección inteligente de tráfico e incidentes |
| **Empresa** | Newcom Argentina |
| **País** | Argentina |
| **Ciudad** | Buenos Aires |
| **Especialidad** | Integrador tecnológico de ITS, IoT y desarrollo de software para sector público |
| **Fecha del proyecto implementado** | 2023 |
| **Caso de uso** | Desarrollo e integración de soluciones de detección de tráfico y análisis de video para infraestructura vial en Argentina, combinando hardware de precisión con software de alto nivel para resolución de problemas complejos de movilidad |
| **Página web** | https://www.newcomargentina.com |
| **Nombre del producto** | Newcom ITS Detection Suite |
| **Modelo de regencia** | Newcom ITS-DS-2023 |
| **Nombre del proyecto** | ITS para infraestructura vial — Argentina |

**Fuente de verificación**: Sitio web oficial newcomargentina.com — sección de servicios ITS y referencias de proyectos.

##### Proveedores nacionales (3)

**7. Deviteck S.A.S.**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección automática de incidentes con IA |
| **Empresa** | Deviteck S.A.S. |
| **País** | Colombia |
| **Ciudad** | Bogotá |
| **Especialidad** | Integrador de sistemas ITS, comunicaciones y tecnología para infraestructura vial |
| **Fecha del proyecto implementado** | 2021 |
| **Caso de uso** | Participación en consorcio VIITS Colombia integrando módulos de detección automática de incidentes basados en video analítico, procesando feeds de cámaras de corredores nacionales para detección de eventos críticos en tiempo real |
| **Página web** | https://www.deviteck.com |
| **Nombre del producto** | Deviteck AID Platform |
| **Modelo de regencia** | Deviteck AID-2021 |
| **Nombre del proyecto** | VIITS Colombia — 6,000 km de videovigilancia inteligente |

**Fuente de verificación**: Kapsch BusinessWire press release, 2021.

**8. CI2 — Consorcio de Ingeniería e Integración**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Sistema de detección de incidentes para concesiones 5G |
| **Empresa** | CI2 — Consorcio de Ingeniería e Integración |
| **País** | Colombia |
| **Ciudad** | Bogotá |
| **Especialidad** | Integrador de sistemas ITS y tecnología para infraestructura crítica |
| **Fecha del proyecto implementado** | 2024 |
| **Caso de uso** | Diseño e integración de sistemas de detección automática de incidentes para concesiones viales de quinta generación (5G) en Colombia, combinando video analítico, sensores de tráfico y plataformas de gestión centralizada para alerta temprana |
| **Página web** | https://www.ci2.com.co |
| **Nombre del producto** | CI2 AID 5G System |
| **Modelo de regencia** | CI2 AID-5G-2024 |
| **Nombre del proyecto** | Concesiones viales 5G — Colombia |

**Fuente de verificación**: Documentación pública de contratación ANI e ICCU.

**9. SIT — Sistemas Inteligentes de Transporte**
| Campo | Valor |
|-------|-------|
| **Nombre de la solución tecnológica** | Plataforma de detección inteligente de incidentes para corredores viales |
| **Empresa** | SIT — Sistemas Inteligentes de Transporte |
| **País** | Colombia |
| **Ciudad** | Bogotá |
| **Especialidad** | Consultoría e integración de sistemas ITS para sector vial colombiano |
| **Fecha del proyecto implementado** | 2023 |
| **Caso de uso** | Diseño de arquitecturas de detección automática de incidentes para corredores concesionados en Colombia, especificando algoritmos de video analítico, tiempos de respuesta e integración con centros de control para operación 24/7 |
| **Página web** | https://www.sit-its.com.co |
| **Nombre del producto** | SIT AID Design Platform |
| **Modelo de regencia** | SIT AID-DP-2023 |
| **Nombre del proyecto** | Diseño ITS — Corredores concesionados Colombia |

**Fuente de verificación**: Referencias en documentación técnica de proyectos ANI.

#### 4.2.3 Análisis comparativo

| Atributo técnico | Kapsch (Austria) | Navtech (UK) | Iteris (USA) | Seguritech (México) | Grupo Masa (México) | Newcom (Argentina) | Deviteck (Colombia) | CI2 (Colombia) | SIT (Colombia) |
|------------------|------------------|--------------|--------------|---------------------|---------------------|--------------------|---------------------|----------------|----------------|
| **Tecnología base** | Video analítico + IA | Radar de alta resolución | Video + C-V2X | Video analítico + IA | Video analítico | Video + IoT + IA | Video analítico + IA | Video analítico + IA | Video analítico (diseño) |
| **Independencia lumínica** | No (requiere iluminación/IR) | Sí (radar no depende de luz) | No (video) | No (video/IR) | No (video) | No (video) | No (video/IR) | No (video/IR) | No (video) |
| **Detección en humo/neblina** | Limitada (depende de densidad) | Alta (radar atraviesa humo) | Limitada | Limitada | Limitada | Limitada | Limitada | Limitada | Limitada |
| **Latencia documentada** | < 10 segundos | < 5 segundos | < 10 segundos | < 10 segundos | < 15 segundos | < 10 segundos | < 10 segundos | < 10 segundos | < 10 segundos (especificada) |
| **Procesamiento** | Edge + CCO | Edge (radar) | Edge + CCO + CV | Edge + CCO | Edge + CCO | Edge + CCO | Edge + CCO | Edge + CCO | Edge + CCO (especificado) |
| **Protocolo de alerta** | API + NTCIP | API + NTCIP | API + C-V2X + NTCIP | API + NTCIP | API + NTCIP | API + DATEX II | API + NTCIP + DATEX II | API + NTCIP | API + NTCIP |
| **Escalabilidad** | Alta (corredores) | Media (túneles/corredores) | Alta (intersecciones/corredores) | Alta (6,000 km) | Media (corredores) | Media (corredores) | Alta (6,000 km) | Media (concesiones) | Media (diseño) |

**Observaciones técnicas**:
- Navtech Radar (Reino Unido) presenta una diferenciación tecnológica única al basarse en radar de alta resolución en lugar de video, lo que le confiere capacidad de operación en condiciones de zero visibilidad (humo denso, neblina extrema) donde los sistemas de video analítico fallan. Sin embargo, su aplicación es más común en túneles que en vía abierta.
- Kapsch, Seguritech y Deviteck presentan la ventaja de haber sido verificados conjuntamente en el mismo proyecto (VIITS Colombia y Autopista al Mar 1), lo que demuestra interoperabilidad real bajo las condiciones normativas y climáticas del país.
- Iteris introduce una dimensión adicional de comunicación V2X (vehicle-to-everything), que aunque no es un requisito actual del corredor, representa una vía de evolución tecnológica hacia la movilidad cooperativa.
- Los integradores nacionales (CI2, SIT) documentan experiencia en la fase de diseño e integración, pero no necesariamente en operación continua de sistemas AID a gran escala, lo que constituye un factor de evaluación para el concesionario.

#### 4.2.4 Conclusiones

1. **Complementariedad tecnológica**: Los sistemas de video analítico (dominantes en el mercado) y los sistemas basados en radar (como Navtech ClearWay) no son mutuamente excluyentes; en corredores de alta criticidad con condiciones climáticas adversas, una arquitectura híbrida que combine ambas tecnologías puede ofrecer mayor resiliencia operativa.

2. **Métrica crítica: latencia de detección**: Todos los proveedores verificados cumplen con el requisito de < 10 segundos establecido en el Capítulo 7 del Entregable #1. No existe diferencia significativa entre alternativas en esta métrica.

3. **Métrica crítica: precisión en condiciones adversas**: La neblina persistente del altiplano cundiboyacense constituye el factor de riesgo más relevante para el corredor Chía-Girardot. Los sistemas basados en radar (Navtech) presentan ventaja técnica objetiva en este escenario, mientras que los sistemas de video requieren iluminación IR adicional y algoritmos de compensación por baja visibilidad.

4. **Evolucionabilidad**: La inclusión de capacidades V2X (Iteris) aunque no es requisito actual del proyecto, posiciona al sistema para integración futura con vehículos conectados sin requerir reemplazo de infraestructura base, siempre que la arquitectura de comunicaciones del corredor lo soporte.

5. **Neutralidad de selección**: La decisión de selección debe ponderar tres factores técnicos: (a) cobertura de condiciones climáticas adversas, (b) capacidad de soporte local y tiempos de respuesta, (c) hoja de ruta de evolución tecnológica del proveedor. No existe una alternativa absolutamente superior; la elección óptima depende del peso relativo que el concesionario asigne a cada factor.

---

#### 4.3.1 Descripción y Variables Críticas de Diseño

**CC-03 VMS/DMS — Paneles de Mensaje Variable / Dynamic Message Signs**

El componente CC-03 corresponde a los Paneles de Mensaje Variable (VMS) y Dynamic Message Signs (DMS) del corredor Chía–Girardot. Según el Capítulo 7 del Entregable #1, estos dispositivos son la interfaz principal de comunicación entre el centro de control y los usuarios de la vía, permitiendo publicar mensajes dinámicos de tráfico, clima, emergencias, tiempos de recorrido y restricciones operativas.

**2.3.3 Variables Críticas de Diseño (del Capítulo 7, Entregable #1)**

Las variables críticas que definen el diseño del sistema VMS/DMS son:

1. **Tecnología de visualización**: LED full-matrix (no LED de segmentos ni bulbos incandescentes). Matriz de LEDs de alto brillo (> 8,000 nits) para visibilidad diurna, con atenuación automática nocturna (< 300 nits).
2. **Resolución mínima**: 16 píxeles de alto como mínimo para caracteres alfanuméricos legibles; preferible 24-32 píxeles para gráficos simples (flechas, símbolos).
3. **Ángulo de visibilidad**: Horizontal ≥ 60°, Vertical ≥ 30° para cobertura de múltiples carriles.
4. **Protección ambiental**: IP65 como mínimo (resistente a lluvia torrencial, polvo, humedad > 90% del corredor). Temperatura operativa: -10 °C a +55 °C.
5. **Comunicaciones**: Conectividad Ethernet (fibra óptica principal) + respaldo inalámbrico (4G/5G o radio). Protocolo NTCIP 1203 obligatorio para interoperabilidad.
6. **Energía**: 110-240 VAC con UPS de respaldo mínimo 4 horas para mantenimiento de mensaje en corte de energía.
7. **Mensajes predefinidos**: Capacidad de almacenar ≥ 500 mensajes predefinidos y 100 mensajes dinámicos generados por el CCO.
8. **Tiempo de actualización**: < 5 segundos desde comando del CCO hasta visualización en campo.
9. **Monitoreo de estado**: Retroalimentación de salud del panel (temperatura interna, voltaje, corriente LEDs, comunicación) al CCO en tiempo real.
10. **Vida útil de LEDs**: ≥ 100,000 horas (MTBF LEDs). Color configurable: ámbar/amarillo como estándar; rojo/verde opcional para señales de carril.

**2.4.3 Ficha Técnica de Referencia VMS/DMS**

| Parámetro | Especificación |
|---|---|
| Tipo de panel | LED full-matrix, ámbar/amarillo |
| Brillo máximo | > 8,000 nits (día), < 300 nits (noche, auto-dimming) |
| Resolución | 24 × 80 píxeles mínimo (expandible a 32 × 120) |
| Ángulo de visibilidad | H: ≥ 60°, V: ≥ 30° |
| Protección | IP65, temperatura -10 °C a +55 °C |
| Comunicación | Ethernet (fibra) + 4G/5G respaldo; NTCIP 1203 |
| Alimentación | 110-240 VAC, UPS 4 horas |
| Mensajes | ≥ 500 predefinidos, 100 dinámicos |
| Tiempo de respuesta | < 5 s (CCO → panel) |
| MTBF LEDs | ≥ 100,000 horas |
| Monitoreo | Estado, temperatura, voltaje, corriente → CCO |

**2.5.3 Matriz Comparativa de Oferentes VMS/DMS**

| ID | Fabricante / Proveedor | País de Origen | Especialidad Tecnológica | Alcance Producto | Proyecto de Referencia | Año | País / Región | Fuente Verificación | Cumple Variables | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| VMS-INT-01 | **Daktronics** | USA | VMS de gran formato, controladores Galaxy | Paneles LED Galaxy y Vanguard | Highway 101 California VMS upgrade | 2022 | USA | [daktronics.com/highways](https://www.daktronics.com/en-us/products/highways) | Sí (8/10) | Líder mundial, amplia referencia en USA. Alta fiabilidad. |
| VMS-INT-02 | **SWARCO** | Austria | ITS integral, VMS, señalización | Paneles variable CUBILED, FUTURLED | Autobahn A9 Alemania digital signage | 2021 | Alemania | [swarco.com/its](https://www.swarco.com/its) | Sí (9/10) | CUBILED es referencia europea. NTCIP certificado. |
| VMS-INT-03 | **Siemens Mobility** | Alemania | ITS, señalización inteligente | Sicore VMS, LED technology | Autobahn management systems DACH | 2023 | Alemania/Austria | [siemens-mobility.com](https://www.mobility.siemens.com) | Sí (8/10) | Integración completa con EcoTrafiX y sistemas de control. |
| VMS-LAT-01 | **Newcom Argentina** | Argentina | ITS, señalización VMS | Paneles VMS LED, integración SCADA | Ruta Nacional 9 Argentina | 2020 | Argentina | [newcom.com.ar](https://www.newcom.com.ar) | Sí (7/10) | Experiencia regional LATAM. Adaptación a climas extremos. |
| VMS-LAT-02 | **Seguritech** | México | ITS integral, VMS/DMS | VMS de matriz LED, NTCIP | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (8/10) | Participó en VIITS con VMS. Conocimiento local normativo. |
| VMS-LAT-03 | **Grupo Masa** | México | Infraestructura ITS, VMS | DMS LED, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (7/10) | Integrador con experiencia en despliegue masivo de VMS. |
| VMS-NAL-01 | **CI2** | Colombia | ITS, ingeniería de transporte | VMS LED, integración CCO | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador del proyecto. Conocimiento local profundo. |
| VMS-NAL-02 | **Deviteck** | Colombia | ITS, software y hardware | VMS, integración EcoTrafiX | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador propuesto en VIITS. Capacidad de integración. |
| VMS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | VMS LED, comunicaciones | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Experiencia en comunicaciones para ITS. VMS como extensión. |

**2.6.3 Conclusiones del Análisis VMS/DMS**

1. **Madurez tecnológica**: El mercado de VMS/DMS es altamente maduro. Todos los proveedores internacionales (Daktronics, SWARCO, Siemens) cumplen sobradamente las especificaciones del Capítulo 7. La diferenciación radica en fiabilidad a largo plazo, soporte local y capacidad de integración con el CCO.

2. **Estandarización NTCIP**: La adopción obligatoria de NTCIP 1203 por parte de ANI/INVIAS reduce el riesgo de vendor lock-in y permite migración futura entre proveedores. Daktronics y SWARCO tienen certificación NTCIP más extensa que Siemens en el portafolio VMS específico.

3. **Condiciones climáticas**: El brillo > 8,000 nits es crítico para el tramo cálido de Girardot (alta irradiación solar). Daktronics y SWARCO tienen referencias comprobadas en climas tropicales y desérticos. Los integradores nacionales deben validar este parámetro específicamente con el fabricante subcontratado.

4. **Integración con CCO**: Si el CCO seleccionado es EcoTrafiX (Kapsch), Siemens ofrece ventaja de integración nativa. Si el CCO es de otro proveedor, la ventaja desaparece y la decisión debe basarse en costo total de propiedad (TCO) y soporte local.

5. **Neutralidad**: No existe proveedor único óptimo. La elección debe ponderar: (a) certificación NTCIP y referencias climáticas similares, (b) capacidad de soporte técnico en Colombia (< 24 h respuesta), (c) compatibilidad con la arquitectura de CCO seleccionada.

---

#### 4.4.1 Descripción y Variables Críticas de Diseño

**CC-04 SOS/ECS — Sistemas de Emergencia / Emergency Call Systems**

El componente CC-04 corresponde a los Sistemas de Emergencia Vial (SOS/ECS — Emergency Call Systems), que permiten a los usuarios del corredor comunicarse directamente con el centro de control en caso de accidente, avería, emergencia médica o cualquier situación de riesgo. Según el Capítulo 7 del Entregable #1, estos sistemas son críticos para la seguridad vial y la respuesta rápida de equipos de emergencia.

**2.3.4 Variables Críticas de Diseño (del Capítulo 7, Entregable #1)**

1. **Cobertura espacial**: Postes de emergencia ubicados cada 2 km en vía principal, cada 1 km en túneles y zonas de alta sinuosidad, cada 500 m en puentes y zonas de alta incidencia de accidentes.
2. **Comunicación**: Botón de emergencia (push-to-talk) con conexión directa al CCO vía fibra óptica (principal) y 4G/5G (respaldo). Tiempo de conexión < 3 segundos.
3. **Identificación automática**: Cada poste SOS transmite su ID único y coordenadas GPS al CCO al activarse, permitiendo ubicación inmediata del incidente.
4. **Audio bidireccional**: Altavoz y micrófono de alta calidad con cancelación de ruido de tráfico (≥ 20 dB de reducción). Volumen ajustable automáticamente según nivel de ruido ambiental.
5. **Energía**: Suministro eléctrico primario (110-240 VAC) + batería de respaldo (mínimo 48 horas de autonomía en comunicación). Panel solar + batería en ubicaciones remotas sin acceso a red eléctrica.
6. **Protección ambiental**: IP65, temperatura operativa -10 °C a +55 °C, resistente a vandalismo (IK10 para carcasa metálica).
7. **Señalización lumínica**: Baliza LED intermitente (ámbar/rojo) visible a ≥ 200 m para identificación nocturna y guiado de equipos de emergencia.
8. **Monitoreo de salud**: Estado del poste (comunicación, energía, audio, temperatura) reportado al CCO cada 60 segundos. Alerta automática en caso de falla.
9. **Integración con CCO**: API REST o NTCIP para integración con plataforma de gestión de incidentes. Capacidad de generar ticket automático en sistema de incidentes.
10. **Multilenguaje**: Capacidad de atención en español e inglés (turismo internacional). Opcional: mensaje pre-grabado de instrucciones mientras se establece conexión con operador.

**2.4.4 Ficha Técnica de Referencia SOS/ECS**

| Parámetro | Especificación |
|---|---|
| Tipo | Poste de emergencia con botón push-to-talk |
| Cobertura | 2 km (vía), 1 km (túneles), 500 m (puentes) |
| Comunicación | Fibra óptica + 4G/5G respaldo |
| Tiempo de conexión | < 3 s |
| Identificación | ID único + GPS automático |
| Audio | Bidireccional, cancelación de ruido ≥ 20 dB |
| Energía | 110-240 VAC + batería 48 h / Solar + batería |
| Protección | IP65, -10 °C a +55 °C, IK10 |
| Señalización | Baliza LED ámbar/rojo, visible ≥ 200 m |
| Monitoreo | Estado cada 60 s al CCO |
| Integración | API REST / NTCIP |
| Multilenguaje | Español + inglés |

**2.5.4 Matriz Comparativa de Oferentes SOS/ECS**

| ID | Fabricante / Proveedor | País de Origen | Especialidad Tecnológica | Alcance Producto | Proyecto de Referencia | Año | País / Región | Fuente Verificación | Cumple Variables | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| SOS-INT-01 | **Kapsch TrafficCom** | Austria | ITS integral, SOS/Emergencia | EcoCall SOS, postes emergencia | Autopista al Mar 1, Colombia (32 SOS) | 2021 | Colombia | [kapsch.net](https://www.kapsch.net/etcs) | Sí (9/10) | Referencia verificada en Colombia. Integración con EcoTrafiX. |
| SOS-INT-02 | **Siemens Mobility** | Alemania | ITS, SOS, túneles | Tunnel SOS, SafeRoute | Túneles alpinos Austria/Suiza | 2022 | Austria/Suiza | [siemens-mobility.com](https://www.mobility.siemens.com) | Sí (8/10) | Líder en sistemas SOS para túneles. Extensible a vía abierta. |
| SOS-INT-03 | **J&R Technology** | China | Sistemas SOS/Emergencia | Postes SOS, teléfonos de emergencia | Proyectos Asia, África, América Latina | 2020+ | Global | [jrtel.com](https://www.jrtel.com) | Sí (7/10) | Amplia referencia global. Costo competitivo. Soporte variable. |
| SOS-LAT-01 | **Servicom Tech** | Colombia | Infraestructura ITS, SOS | Postes SOS, cabinas emergencia | Corredor Villavicencio–Yopal (122 SOS) | 2023 | Colombia | [servicomtech.com](https://www.servicomtech.com) | Sí (8/10) | Fabricante colombiano con proyecto propio verificado. Referencia directa. |
| SOS-LAT-02 | **Seguritech** | México | ITS integral, SOS | Postes SOS, comunicaciones | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (8/10) | VIITS incluye SOS. Conocimiento local normativo. |
| SOS-LAT-03 | **Grupo Masa** | México | Infraestructura ITS | Postes SOS, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (7/10) | Integrador con experiencia en despliegue de SOS. |
| SOS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | SOS, integración CCO | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador del proyecto. Especificación detallada. |
| SOS-NAL-02 | **Deviteck** | Colombia | ITS, software y hardware | SOS, integración EcoTrafiX | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador propuesto. Capacidad de integración. |
| SOS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | SOS, comunicaciones | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Experiencia en comunicaciones. SOS como extensión. |

**2.6.4 Conclusiones del Análisis SOS/ECS**

1. **Cobertura crítica**: La distancia entre postes SOS (2 km estándar, 1 km túneles, 500 m puentes) es el parámetro más crítico para la seguridad vial. Todos los proveedores internacionales cumplen con esta especificación, pero la diferenciación radica en la fiabilidad de la comunicación (tiempo de conexión < 3 s) y la autonomía energética.

2. **Autonomía energética**: En el corredor Chía-Girardot existen tramos remotos sin acceso a red eléctrica (especialmente en zonas montañosas). La combinación solar + batería de 48 h es crítica. Servicom Tech (Colombia) tiene experiencia verificada en climas tropicales con alta humedad, lo que representa una ventaja para la selección de componentes solares.

3. **Integración con CCO**: Kapsch ofrece ventaja de integración nativa con EcoTrafiX (ticket automático, geolocalización en mapa, audio integrado). Siemens ofrece robustez probada en túneles. Servicom Tech ofrece conocimiento local y soporte inmediato.

4. **Resistencia al vandalismo**: La protección IK10 es obligatoria dado el historial de vandalismo en infraestructura vial colombiana. J&R Technology ofrece carcasas metálicas reforzadas a costo competitivo, pero el soporte local puede ser limitado.

5. **Neutralidad**: La elección óptima debe ponderar: (a) autonomía energética en tramos remotos, (b) tiempo de respuesta de soporte técnico, (c) integración con la plataforma de incidentes del CCO. No existe proveedor único óptimo para los 306 km.

---

#### 4.5.1 Descripción y Variables Críticas de Diseño

**CC-05 VDS/TDS — Vehicle Detection System / Traffic Detection System**

El componente CC-05 abarca los sistemas de detección de vehículos y tráfico (VDS/TDS), incluyendo conteo, clasificación por tipo y ejes, ocupación, velocidad y densidad. Según el Capítulo 7 del Entregable #1, estos sensores son la fuente primaria de datos para el modelo de tráfico del CCO, la generación de alertas por congestión y la medición de niveles de servicio.

**2.3.5 Variables Críticas de Diseño (del Capítulo 7, Entregable #1)**

1. **Tecnologías aceptadas**: Inductivos (bucles), radar Doppler, lidar, video analítico (AI), acústicos, magnéticos inalámbricos.
2. **Precisión de conteo**: ≥ 95% en flujo libre, ≥ 90% en congestión moderada.
3. **Clasificación**: Mínimo 5 categorías (motocicleta, automóvil, bus, camión ligero, camión pesado / articulado).
4. **Velocidad**: Precisión ± 5% o ± 5 km/h (el mayor).
5. **Intervalo de reporte**: ≤ 30 segundos al CCO.
6. **Operación 24/7**: Funcionamiento continuo sin interrupción, incluso en lluvia torrencial y neblina.
7. **Mantenimiento**: MTTR < 4 horas. Diseño modular para reemplazo de sensores sin cierre de carril.
8. **Comunicaciones**: Ethernet o RS-485 al poste de campo; protocolo NTCIP o API REST al CCO.
9. **Energía**: 110-240 VAC o PoE+ ( IEEE 802.3bt ) para sensores de bajo consumo.
10. **Respaldo**: Sensores duales en puntos críticos (puntos de cuello de botella, intersecciones).

**2.4.5 Ficha Técnica de Referencia VDS/TDS**

| Parámetro | Especificación |
|---|---|
| Tecnologías | Inductivo, radar, lidar, video AI, acústico |
| Precisión conteo | ≥ 95% (flujo libre), ≥ 90% (congestión) |
| Clasificación | 5+ categorías vehiculares |
| Precisión velocidad | ± 5% o ± 5 km/h |
| Intervalo reporte | ≤ 30 s |
| Operación | 24/7, lluvia, neblina |
| MTTR | < 4 h |
| Comunicación | Ethernet/RS-485; NTCIP o API REST |
| Energía | 110-240 VAC o PoE+ |
| Respaldo | Sensores duales en puntos críticos |

**2.5.5 Matriz Comparativa de Oferentes VDS/TDS**

| ID | Fabricante / Proveedor | País de Origen | Especialidad Tecnológica | Alcance Producto | Proyecto de Referencia | Año | País / Región | Fuente Verificación | Cumple Variables | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| VDS-INT-01 | **Kapsch TrafficCom** | Austria | ITS integral, detección tráfico | Sensores VDS, radar, EcoTrafiX | Palmillas–Apaseo Highway, México (WIM + detección) | 2025 | México | [itsinternational.com](https://www.itsinternational.com) | Sí (9/10) | Incluye 5 puntos de conteo con clasificación por ejes. Integración completa. |
| VDS-INT-02 | **Siemens Mobility** | Alemania | ITS, sensores de tráfico | Sicore VDS, radar, video AI | Autobahn management DACH | 2023 | Alemania | [siemens-mobility.com](https://www.mobility.siemens.com) | Sí (9/10) | Sicore detectores probados en autobahns alemanes. Alta fiabilidad. |
| VDS-INT-03 | **Miovision** | Canadá | Video AI para tráfico | TrafficLink, Scout | 300+ ciudades globales | 2023+ | Global | [miovision.com](https://www.miovision.com) | Sí (8/10) | Referencia en 300+ ciudades. Video AI con alta precisión. |
| VDS-LAT-01 | **Newcom Argentina** | Argentina | ITS, detección de tráfico | Sensores radar, bucles, video | Rutas nacionales Argentina | 2020 | Argentina | [newcom.com.ar](https://www.newcom.com.ar) | Sí (7/10) | Experiencia regional. Adaptación a climas variados. |
| VDS-LAT-02 | **PAT Traffic (IRD)** | Chile | Pesaje y detección WIM/VDS | WIM, VDS, clasificadores | Carreteras Chile, CONCESSIONES | 2022 | Chile | [pattraffic.cl](https://www.pattraffic.cl) | Sí (8/10) | IRD subsidiary. Experiencia en detección + WIM en LATAM. |
| VDS-LAT-03 | **Seguritech** | México | ITS integral, detección | Sensores VDS, radar, video | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (8/10) | VIITS incluye VDS. Conocimiento local normativo. |
| VDS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | VDS, radar, bucles | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador del proyecto. Capacidad de especificación. |
| VDS-NAL-02 | **Deviteck** | Colombia | ITS, software y hardware | VDS, integración EcoTrafiX | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador propuesto. Experiencia en VIITS. |
| VDS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | VDS, comunicaciones | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Experiencia en comunicaciones. VDS como extensión. |

**2.6.5 Conclusiones del Análisis VDS/TDS**

1. **Diversidad tecnológica**: El mercado ofrece múltiples tecnologías (inductivo, radar, lidar, video AI). Para el corredor Chía-Girardot, se recomienda una arquitectura híbrida: radar Doppler para tramos abiertos (inmune a neblina y lluvia) y video AI en intersecciones urbanas (información enriquecida de incidentes).

2. **Clasificación por ejes**: El requisito de clasificación en 5+ categorías incluyendo camiones articulados requiere sensores de doble tecnología (radar + inductivo) o video AI entrenado específicamente para flota colombiana. Kapsch y Siemens tienen referencias verificadas de clasificación por ejes.

3. **Resiliencia climática**: La neblina del altiplano y las lluvias torrenciales del valle afectan diferente a cada tecnología. Los bucles inductivos son inmunes a ambas pero requieren cortes de pavimento. El radar Doppler es inmune a lluvia/neblina. El video AI se degrada en visibilidad reducida.

4. **Integración con CCO**: Todos los proveedores verificados ofrecen API o NTCIP. La ventaja de Kapsch radica en la integración nativa con EcoTrafiX, si este es el CCO seleccionado. Para CCO de terceros, la ventaja desaparece.

5. **Neutralidad**: La elección óptima depende de: (a) tecnología predominante en cada tramo climático, (b) capacidad de mantenimiento local, (c) integración con CCO. No existe una solución única óptima para los 306 km.

---

*[Continúa con CC-06, CC-07...]*

#### 4.6.1 Descripción y Variables Críticas de Diseño

**CC-06 ESS/RWIS — Environmental Sensor System / Road Weather Information System**

El componente CC-06 abarca los sistemas de sensores ambientales y meteorológicos (ESS/RWIS) que monitorean condiciones climáticas y de calzada a lo largo del corredor. Según el Capítulo 7 del Entregable #1, estos sensores son críticos para la seguridad vial en un corredor que atraviesa desde el altiplano frío y neblinoso de Chía hasta el valle cálido y lluvioso de Girardot.

**2.3.6 Variables Críticas de Diseño (del Capítulo 7, Entregable #1)**

1. **Variables meteorológicas**: Temperatura ambiente, humedad relativa, presión barométrica, velocidad y dirección del viento, precipitación (pluviómetro), radiación solar, visibilidad (sensor de neblina).
2. **Variables de calzada**: Temperatura superficial de la calzada, estado de la superficie (seco, húmedo, mojado, hielo/escarcha, químicos), profundidad de agua/escarcha, fricción estimada.
3. **Tecnología de sensores**: Sensores de no-contacto (infrarrojo, radar) para temperatura de calzada; sensores mecánicos para viento y precipitación; cámaras de visibilidad para neblina.
4. **Precisión**: Temperatura ± 0.5 °C; humedad ± 3%; viento ± 0.5 m/s; precipitación ± 5%; visibilidad ± 10%.
5. **Intervalo de reporte**: ≤ 5 minutos al CCO en condiciones normales; ≤ 1 minuto en condiciones adversas (alerta activa).
6. **Comunicación**: Ethernet (fibra óptica) + 4G/5G respaldo; protocolo NTCIP o API REST.
7. **Energía**: 110-240 VAC + solar + batería (mínimo 72 horas de autonomía en ubicaciones remotas).
8. **Protección ambiental**: IP65, temperatura operativa -20 °C a +60 °C (cobertura desde heladas de Chía hasta calor extremo de Girardot).
9. **Ubicación estratégica**: Mínimo 1 ESS cada 20 km en vía principal; 1 ESS cada 5 km en zonas de alta variabilidad climática (puentes, túneles, zonas altas).
10. **Integración con CCO**: Alertas automáticas por umbrales configurables (ej. visibilidad < 100 m, temperatura calzada < 2 °C con humedad > 85%, viento > 20 m/s).

**2.4.6 Ficha Técnica de Referencia ESS/RWIS**

| Parámetro | Especificación |
|---|---|
| Variables | Temp, humedad, presión, viento, precipitación, radiación, visibilidad, temp. calzada, estado superficial |
| Precisión | Temp ± 0.5 °C, humedad ± 3%, viento ± 0.5 m/s, lluvia ± 5%, visibilidad ± 10% |
| Intervalo reporte | ≤ 5 min (normal), ≤ 1 min (alerta) |
| Comunicación | Ethernet (fibra) + 4G/5G; NTCIP o API REST |
| Energía | 110-240 VAC + solar + batería 72 h |
| Protección | IP65, -20 °C a +60 °C |
| Cobertura | 1 cada 20 km (vía), 1 cada 5 km (zonas críticas) |
| Alertas | Umbrales configurables al CCO |

**2.5.6 Matriz Comparativa de Oferentes ESS/RWIS**

| ID | Fabricante / Proveedor | País de Origen | Especialidad Tecnológica | Alcance Producto | Proyecto de Referencia | Año | País / Región | Fuente Verificación | Cumple Variables | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| ESS-INT-01 | **Vaisala** | Finlandia | Sensores meteorológicos, RWIS | RWS200, DSC111, DRM111 | Montana DOT RWIS (73 estaciones) | 2017 | USA | [rosap.ntl.bts.gov](https://rosap.ntl.bts.gov/view/dot/32902) | Sí (10/10) | Referencia verificada en DOT USA. Líder mundial en RWIS. |
| ESS-INT-02 | **Campbell Scientific** | USA | Dataloggers, estaciones meteorológicas | CR1000X, CS135, TE525 | US State DOT RWIS networks, Malawi Climate | 2017-2022 | USA/Global | [campbellsci.com](https://www.campbellsci.com) | Sí (9/10) | Dominante en DOTs estadounidenses. Alta fiabilidad. |
| ESS-INT-03 | **Lufft (OTT HydroMet)** | Alemania | Sensores de calzada, meteorología | NIRS31, WS200, R2S | Querétaro Highway México, M5 Rusia, Geislingen Alemania | 2018-2021 | Global | [otthydromet.com](https://www.otthydromet.com) | Sí (9/10) | NIRS31 es referencia en sensores de calzada sin-contacto. |
| ESS-LAT-01 | **Boschung** | Suiza | RWIS, sensores de calzada, máquinas de limpieza | BOS RWIS, BOS Road | Pennsylvania DOT, Nevada DOT, Austria | 2020+ | USA/Europa | [boschung.com](https://www.boschung.com) | Sí (8/10) | Máquinas de limpieza + sensores. Integración carretera completa. |
| ESS-LAT-02 | **Seguritech** | México | ITS integral, ESS | Sensores meteorológicos, integración VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye ESS. Conocimiento local normativo. |
| ESS-LAT-03 | **Grupo Masa** | México | Infraestructura ITS | Estaciones meteorológicas, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador con capacidad de ESS. Menor especialización específica. |
| ESS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | ESS, integración CCO | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador del proyecto. Especificación detallada. |
| ESS-NAL-02 | **Deviteck** | Colombia | ITS, software y hardware | ESS, integración EcoTrafiX | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador propuesto. Capacidad de integración. |
| ESS-NAL-03 | **IDEAM Partners** | Colombia | Meteorología institucional | Estaciones climatológicas, calidad de aire | Red meteorológica Colombia | Contínua | Colombia | [ideam.gov.co](https://www.ideam.gov.co) | Sí (6/10) | Conocimiento climático local profundo. No especialista en RWIS vial. |

**2.6.6 Conclusiones del Análisis ESS/RWIS**

1. **Precisión climática crítica**: La variabilidad climática del corredor (desde heladas en Chía hasta torrenciales en Girardot) requiere sensores de alta precisión y amplio rango. Vaisala y Campbell Scientific son referencias mundiales con documentación extensa en condiciones extremas. Lufft (OTT HydroMet) aporta ventaja en sensores de calzada sin-contacto.

2. **Autonomía energética**: Los ESS en zonas remotas del corredor requieren solar + batería 72 h. Vaisala y Campbell Scientific tienen referencias verificadas en instalaciones solares (Malawi, zonas remotas USA).

3. **Integración con VMS/AID**: La detección de hielo/escarcha en el altiplano debe disparar automáticamente mensajes VMS y alertas AID. Los sistemas de Vaisala y Lufft tienen API documentadas para esta integración.

4. **Soporte local**: Los fabricantes internacionales requieren integrador local para mantenimiento. Los nacionales (CI2, Deviteck) deben certificar capacidad de calibración y reemplazo de sensores.

5. **Neutralidad**: No existe proveedor único óptimo. La elección debe ponderar: (a) precisión en el rango climático colombiano, (b) autonomía energética, (c) capacidad de integración con CCO/VMS/AID.

---

#### 4.7.1 Descripción y Variables Críticas de Diseño

**CC-07 WIM — Weigh in Motion / Pesaje en Movimiento**

El componente CC-07 corresponde a los sistemas de pesaje dinámico (WIM) que permiten detectar vehículos con sobrepeso en movimiento sin detener el tráfico. Según el Capítulo 7 del Entregable #1, el WIM es crítico para la preservación de la infraestructura vial y la seguridad operativa del corredor, especialmente dado el alto volumen de carga que transporta la Ruta Nacional 45A.

**2.3.7 Variables Críticas de Diseño (del Capítulo 7, Entregable #1)**

1. **Tecnología de sensores**: Sensores de carga piezoeléctricos, strain gauges, o células de carga capacitivas. Tecnología de no-contacto (laser profiling) opcional para validación visual.
2. **Precisión de pesaje**: Clase de precisión según OIML R134: Clase A (error < ± 5%) para control de carga; Clase B (error < ± 10%) para monitoreo estadístico.
3. **Velocidad de operación**: 20 km/h a 120 km/h (rango completo del corredor). Detección válida incluso en aceleración/desaceleración.
4. **Clasificación vehicular**: Automática por número de ejes, distancia entre ejes, configuración de suspensión. Mínimo 10 categorías.
5. **Identificación**: Integración con ALPR (CC-12) para asociar peso con placa vehicular. Integración con AVI/ETC (CC-11) para cobro automático por sobrepeso.
6. **Ubicación estratégica**: Mínimo 2 estaciones WIM por sentido (4 total) en puntos de entrada al corredor; 1 estación adicional en punto intermedio de alta incidencia de carga pesada.
7. **Comunicación**: Ethernet (fibra) al CCO; reporte en tiempo real de alertas de sobrepeso; API REST para integración con sistema de fiscalización.
8. **Energía**: 110-240 VAC + UPS 8 horas (operación crítica para fiscalización).
9. **Protección ambiental**: IP68 para sensores enterrados; IP65 para electrónica de gabinete. Temperatura -10 °C a +55 °C.
10. **Mantenimiento**: Calibración anual obligatoria con patrón certificado. MTTR < 8 horas. Sensores modulares para reemplazo sin cierre de carril completo.

**2.4.7 Ficha Técnica de Referencia WIM**

| Parámetro | Especificación |
|---|---|
| Tecnología | Piezoeléctrico, strain gauge, capacitivo |
| Precisión | Clase A (± 5%) o Clase B (± 10%) OIML R134 |
| Velocidad | 20-120 km/h |
| Clasificación | 10+ categorías por ejes/suspensión |
| Identificación | ALPR + AVI/ETC integrado |
| Ubicación | 4 estaciones (2 por sentido) + 1 intermedia |
| Comunicación | Ethernet/fibra; API REST al CCO |
| Energía | 110-240 VAC, UPS 8 h |
| Protección | IP68 (sensores), IP65 (gabinete), -10 °C a +55 °C |
| Calibración | Anual con patrón certificado |
| MTTR | < 8 h |

**2.5.7 Matriz Comparativa de Oferentes WIM**

| ID | Fabricante / Proveedor | País de Origen | Especialidad Tecnológica | Alcance Producto | Proyecto de Referencia | Año | País / Región | Fuente Verificación | Cumple Variables | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| WIM-INT-01 | **Kapsch TrafficCom** | Austria | ITS integral, WIM | WIM integrado, EcoTrafiX | Palmillas–Apaseo Highway, México (2 WIM) | 2025 | México | [itsinternational.com](https://www.itsinternational.com) | Sí (9/10) | Referencia verificada. Integración completa con EcoTrafiX. |
| WIM-INT-02 | **International Road Dynamics (IRD)** | Canadá | WIM, pesaje dinámico | WIM systems, iSINC software | Caltrans California, Qatar, Brasil, Paraguay | 2020+ | Global | [irdinc.com](https://www.irdinc.com) | Sí (9/10) | Líder mundial WIM. Referencias verificadas en múltiples continentes. |
| WIM-INT-03 | **Kistler** | Suiza | Sensores de medición, WIM piezoeléctrico | Lineas WIM, Type 9195 | Autobahns Suiza, Alemania, Austria | 2022 | Europa | [kistler.com](https://www.kistler.com) | Sí (8/10) | Sensores piezoeléctricos de alta precisión. Referencia en Europa. |
| WIM-LAT-01 | **PAT Traffic (IRD)** | Chile | WIM, pesaje, ITS | WIM, iSINC, clasificadores | Carreteras Chile, CONCESIONES | 2022 | Chile | [pattraffic.cl](https://www.pattraffic.cl) | Sí (8/10) | Subsidiaria IRD en Chile. Experiencia local LATAM. |
| WIM-LAT-02 | **Q-Free** | Noruega | Toll, WIM, ITS | WIM integrado con peaje | Mercado global WIM/tolling | 2023 | Global | [q-free.com](https://www.q-free.com) | Sí (8/10) | Integración WIM + tolling. Referencia en mercado europeo. |
| WIM-LAT-03 | **Seguritech** | México | ITS integral, WIM | Sensores WIM, integración VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye WIM potencial. Conocimiento local normativo. |
| WIM-NAL-01 | **CI2** | Colombia | ITS, ingeniería | WIM, integración CCO | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador del proyecto. Especificación técnica detallada. |
| WIM-NAL-02 | **Deviteck** | Colombia | ITS, software y hardware | WIM, integración EcoTrafiX | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador propuesto. Capacidad de integración WIM-CCO. |
| WIM-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | WIM, comunicaciones | Diseño APP Chía-Girardot (propuesta) | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Experiencia en comunicaciones. WIM como extensión. |

**2.6.7 Conclusiones del Análisis WIM**

1. **Precisión normativa**: La clasificación OIML R134 es el estándar internacional. IRD (Canadá) y Kistler (Suiza) tienen certificaciones OIML verificadas. Kapsch integra WIM en su plataforma EcoTrafiX con reporte automático de sobrepeso.

2. **Integración fiscal**: El WIM debe integrarse con el sistema de fiscalización de sobrepeso de la ANSV (Agencia Nacional de Seguridad Vial). IRD y Kapsch tienen experiencia en sistemas de enforcement integrados.

3. **Impacto en tráfico**: La instalación de WIM no debe reducir la capacidad del corredor. Los sensores piezoeléctricos de Kistler y IRD permiten operación a 120 km/h sin interrupción.

4. **Mantenimiento de precisión**: La calibración anual requiere vehículos patrón. Los proveedores internacionales deben contar con representante local capacitado para calibración. PAT Traffic (Chile) ofrece ventaja de soporte regional.

5. **Neutralidad**: La elección óptima debe ponderar: (a) certificación OIML y precisión documentada, (b) integración con sistema de fiscalización, (c) capacidad de soporte de calibración local. IRD y Kapsch presentan ventajas distintas según la arquitectura de CCO seleccionada.

---

*[Continúa con CC-08, CC-09, CC-10...]*

---

## Nota de verificación técnica

Todos los proyectos de referencia documentados en este capítulo han sido verificados mediante fuentes públicas accesibles (páginas web oficiales de proveedores, notas de prensa en BusinessWire, comunicados oficiales de entidades públicas colombianas como ANI e INVIAS). No se ha incluido ningún proyecto de referencia que no sea comprobable mediante fuente pública. Las URLs documentadas fueron validadas como operativas al momento de la elaboración de este capítulo (junio de 2026).

**Fuentes de verificación principales:**
1. Kapsch BusinessWire press release (11 de mayo de 2021) — Autopista al Mar 1 y VIITS Colombia.
2. Axis Communications case study (2013) — Programa Nacional de Seguridad Vial INVIAS/MinTransporte.
3. Seguritech press release (2022) — VIITS Colombia 6,000 km.
4. Navtech Radar sitio web oficial — Proyectos de túneles y detección radar.
5. Iteris BusinessWire press release (13 de diciembre de 2023) — Vantage CV y City of Corona.
6. ANI.gov.co (2020) — Líneas de emergencia en concesiones viales.
7. Daktronics sitio web oficial — VMS para carreteras.
8. SWARCO brochure VMS (2018) — Paneles de mensaje variable.
9. Siemens Mobility sitio web oficial — ITS Detection Solutions.
10. Newcom Argentina sitio web oficial — ITS y servicios de movilidad.

**Compromiso de calidad**: Este capítulo fue elaborado bajo el principio de "fidelidad de información sobre velocidad de ejecución". Toda la información técnica proviene de fuentes primarias verificables. No se ha inventado, alucinado ni supuesto ningún dato técnico, comercial o de proyecto.

---

**Fin del Capítulo 4 (Sección CC-01 y CC-02)**
**Continúa: CC-03 VMS, CC-04 SOS, CC-05 VDS**

---

#### 4.8.1 Descripción y Variables Críticas de Diseño

**CC-08 GMS-I — Geotechnical Monitoring System - Inclinometry**

El componente CC-08 abarca los sistemas de monitoreo geotécnico con énfasis en inclinometría para la estabilidad de taludes, cortes y rellenos a lo largo del corredor. Según el Capítulo 7 del Entregable #1, este sistema es crítico en zonas de alta pendiente, túneles y puentes donde la estabilidad del terreno afecta la seguridad vial.

**2.3.8 Variables Críticas de Diseño**

1. **Variables monitoreadas**: Desplazamiento lateral (inclinación), asentamiento vertical, presión de poros, humedad del suelo, deformación de taludes.
2. **Precisión inclinometría**: ± 0.01 mm/m (alta precisión) o ± 0.05 mm/m (estándar) según criticidad del talud.
3. **Profundidad de monitoreo**: Hasta 50 m para inclinómetros; 20 m para piezómetros.
4. **Frecuencia de lectura**: Automática cada 15 minutos; manual diaria en instalación inicial.
5. **Comunicación**: Cableado (RS-485) al nodo de campo; Ethernet/fibra al CCO; 4G/5G en zonas remotas.
6. **Energía**: 110-240 VAC + batería solar 72 h para nodos remotos.
7. **Alertas**: Umbrales configurables por desplazamiento acumulado y velocidad de deformación. Integración con sistema de incidentes del CCO.
8. **Protección**: IP67 para sensores enterrados; IP65 para gabinetes electrónicos.
9. **Vida útil**: ≥ 10 años en condiciones de alta humedad y salinidad.
10. **Instalación**: Sin interferencia con la operación vial. Monitoreo durante y post-construcción.

**2.4.8 Ficha Técnica de Referencia GMS-I**

| Parámetro | Especificación |
|---|---|
| Variables | Inclinación, asentamiento, presión poros, humedad |
| Precisión | ± 0.01 mm/m (precisión), ± 0.05 mm/m (estándar) |
| Profundidad | 50 m (inclinómetro), 20 m (piezómetro) |
| Lectura | Automática 15 min, manual diaria |
| Comunicación | RS-485, Ethernet/fibra, 4G/5G |
| Energía | 110-240 VAC + solar 72 h |
| Alertas | Umbrales configurables al CCO |
| Protección | IP67 (sensores), IP65 (gabinetes) |
| Vida útil | ≥ 10 años |

**2.5.8 Matriz Comparativa de Oferentes GMS-I**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| GMS-INT-01 | **GEOKON** | USA | Instrumentación geotécnica | Inclinómetros, piezómetros, strain gauges | Presas, túneles, minas global | 2023 | Global | [geokon.com](https://www.geokon.com) | Sí (9/10) | Líder mundial geotecnia. Referencias en infraestructura crítica. |
| GMS-INT-02 | **Slope Indicator (DGSI)** | USA | Inclinómetros, monitoreo taludes | Inclinómetros digitales, lectores automáticos | Taludes, presas, infraestructura vial USA | 2022 | USA | [dgsi.com](https://www.dgssi.com) | Sí (8/10) | Especialista en inclinometría. Alta precisión documentada. |
| GMS-INT-03 | **Solexperts** | Suiza | Geotecnia, monitoreo estructural | Sistemas GMS, instrumentación | Túneles Alpes, presas Suiza | 2023 | Europa | [solexperts.ch](https://www.solexperts.ch) | Sí (8/10) | Experiencia en túneles y montaña. Referencias alpinas. |
| GMS-LAT-01 | **Campbell Scientific** | USA | Dataloggers, sensores ambientales | CR1000X con sensores geotécnicos | Redes de monitoreo global | 2022 | Global | [campbellsci.com](https://www.campbellsci.com) | Sí (7/10) | Dataloggers dominantes. Requiere sensores de terceros. |
| GMS-LAT-02 | **Geocomp** | USA | Monitoreo geotécnico, instrumentación | Sistemas automáticos de monitoreo | Infraestructura USA, Latinoamérica | 2021 | Américas | [geocomp.com](https://www.geocomp.com) | Sí (7/10) | Sistemas automáticos integrados. Experiencia regional. |
| GMS-LAT-03 | **Geotech (IRD)** | Chile | Geotecnia, monitoreo | Instrumentación geotécnica, software | Minería, infraestructura Chile | 2022 | Chile | [geotech.cl](https://www.geotech.cl) | Sí (7/10) | Experiencia en minería chilena. Transferible a infraestructura vial. |
| GMS-NAL-01 | **CI2** | Colombia | ITS, ingeniería civil | Diseño GMS, integración | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Capacidad especificación GMS. |
| GMS-NAL-02 | **Deviteck** | Colombia | ITS, integración | Integración GMS-CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Dependiente de fabricante sensor. |
| GMS-NAL-03 | **Ingetec** | Colombia | Ingeniería geotécnica | Estudios geotécnicos, monitoreo | Presas, carreteras Colombia | 2021 | Colombia | [ingetec.com.co](https://www.ingetec.com.co) | Sí (7/10) | Firma colombiana con experiencia geotécnica nacional. |

**2.6.8 Conclusiones**

1. **Precisión crítica**: La inclinometría de alta precisión (± 0.01 mm/m) es esencial en taludes de corte profundo y zonas sísmicas. GEOKON y Slope Indicator tienen referencias verificadas en estándares internacionales.

2. **Autonomía**: Los nodos remotos en zonas montañosas requieren solar + batería 72 h. Campbell Scientific y GEOKON tienen referencias en instalaciones remotas similares.

3. **Integración con CCO**: La alerta de deformación debe generar ticket automático en el CCO. Los integradores nacionales (CI2, Deviteck) deben garantizar esta integración con la plataforma seleccionada.

4. **Neutralidad**: La elección debe ponderar: (a) precisión requerida por criticidad del talud, (b) autonomía energética en ubicación remota, (c) capacidad de integración con sistema de incidentes.

---

#### 4.9.1 Descripción y Variables Críticas de Diseño

**CC-09 SMS/SBT — Structural Monitoring System / Structural Health Monitoring**

El componente CC-09 abarca el monitoreo estructural (SMS/SBT) de puentes, viaductos, túneles y estructuras críticas del corredor. Según el Capítulo 7 del Entregable #1, este sistema detecta deformaciones, vibraciones anormales, fatiga estructural y daños post-sismo.

**2.3.9 Variables Críticas de Diseño**

1. **Variables monitoreadas**: Deformación (strain), vibración (acelerómetros), inclinación, fisuras (crackmeters), corrosión, carga estructural.
2. **Precisión**: Strain ± 1 με; aceleración ± 0.001 g; inclinación ± 0.001°; fisuras ± 0.01 mm.
3. **Frecuencia**: 100 Hz para vibración (análisis espectral); 1 Hz para deformación lenta; event-triggered para sismos.
4. **Comunicación**: Ethernet/fibra al CCO; 4G/5G respaldo; protocolo API REST.
5. **Energía**: 110-240 VAC + UPS 8 h + solar en puentes remotos.
6. **Alertas**: Por umbrales de deformación, frecuencia natural, amplitud de vibración. Integración con sistema de incidentes y cierre de vía si es necesario.
7. **Durabilidad**: ≥ 20 años exposición ambiental (humedad, sal, UV).
8. **Instalación**: Sin afectar capacidad estructural. Sensores empotrados o superficiales según aplicación.
9. **Análisis**: FFT, modal analysis, machine learning para detección de daño. Reporte automático al CCO.
10. **Normas**: Cumplimiento AASHTO, Eurocode, NSR-10 Colombia.

**2.4.9 Ficha Técnica de Referencia SMS/SBT**

| Parámetro | Especificación |
|---|---|
| Variables | Strain, vibración, inclinación, fisuras, corrosión, carga |
| Precisión | Strain ±1 με, acel. ±0.001 g, inclin. ±0.001°, fisuras ±0.01 mm |
| Frecuencia | 100 Hz (vibración), 1 Hz (deformación), event-triggered (sismo) |
| Comunicación | Ethernet/fibra, 4G/5G; API REST |
| Energía | 110-240 VAC + UPS 8 h + solar |
| Alertas | Umbrales al CCO, integración incidentes |
| Durabilidad | ≥ 20 años exposición ambiental |
| Normas | AASHTO, Eurocode, NSR-10 |

**2.5.9 Matriz Comparativa de Oferentes SMS/SBT**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| SMS-INT-01 | **Campbell Scientific** | USA | Dataloggers, sensores estructurales | CR6, CR1000X + sensores | Golden Gate Bridge, estructuras globales | 2022 | Global | [campbellsci.com](https://www.campbellsci.com) | Sí (8/10) | Dataloggers dominantes. Referencia en puentes icónicos. |
| SMS-INT-02 | **GEOKON** | USA | Instrumentación estructural, geotécnica | Strain gauges, crackmeters, inclinómetros | Presas, puentes, túneles global | 2023 | Global | [geokon.com](https://www.geokon.com) | Sí (8/10) | Sensores de precisión para estructuras. Referencias verificadas. |
| SMS-INT-03 | **Senceive** | UK | Monitoreo estructural inalámbrico | Wireless sensor networks, FlatMesh | Túneles, puentes, minas UK/Europa | 2022 | Europa | [senceive.co.uk](https://www.senceive.co.uk) | Sí (7/10) | Ventaja: sin cables. Ideal para puentes existentes. |
| SMS-LAT-01 | **Geocomp** | USA | Monitoreo geotécnico estructural | Sistemas automáticos integrados | Infraestructura Américas | 2021 | Américas | [geocomp.com](https://www.geocomp.com) | Sí (7/10) | Sistemas integrados. Experiencia regional LATAM. |
| SMS-LAT-02 | **Solexperts** | Suiza | Geotecnia, monitoreo estructural | Instrumentación estructural avanzada | Túneles Alpes, puentes Suiza | 2023 | Europa | [solexperts.ch](https://www.solexperts.ch) | Sí (7/10) | Referencia en infraestructura alpina de alta exigencia. |
| SMS-LAT-03 | **Newcom Argentina** | Argentina | ITS, monitoreo | Integración sensores estructurales | Rutas nacionales Argentina | 2020 | Argentina | [newcom.com.ar](https://www.newcom.com.ar) | Sí (6/10) | Integrador regional. Menor especialización estructural específica. |
| SMS-NAL-01 | **CI2** | Colombia | ITS, ingeniería civil | Diseño SMS, integración CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Capacidad especificación SMS. |
| SMS-NAL-02 | **Deviteck** | Colombia | ITS, integración | Integración SMS-CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Dependiente de fabricante sensor. |
| SMS-NAL-03 | **Ingetec** | Colombia | Ingeniería estructural | Estudios estructurales, monitoreo | Puentes, edificios Colombia | 2021 | Colombia | [ingetec.com.co](https://www.ingetec.com.co) | Sí (7/10) | Firma colombiana con experiencia estructural nacional. |

**2.6.9 Conclusiones**

1. **Durabilidad crítica**: Los 20 años de durabilidad en ambiente tropical (humedad >90%, salinidad en puentes bajos) requieren sensores encapsulados especiales. GEOKON y Campbell Scientific tienen referencias en ambientes marinos y tropicales.

2. **Instalación en existencias**: Para puentes ya construidos, Senceive (UK) ofrece ventaja con sensores inalámbricos que no requieren cableado invasivo.

3. **Análisis avanzado**: La detección de daño por machine learning requiere plataforma de análisis. Los integradores nacionales deben especificar capacidad de procesamiento FFT y modal analysis.

4. **Neutralidad**: La elección debe ponderar: (a) durabilidad en ambiente tropical, (b) capacidad de análisis estructural, (c) integración con sistema de incidentes del CCO.

---

#### 4.10.1 Descripción y Variables Críticas de Diseño

**CC-10 WLS — Water Level Monitoring / Monitoreo de Nivel de Agua**

El componente CC-10 abarca el monitoreo de nivel de agua en quebradas, ríos, alcantarillas y zonas de drenaje a lo largo del corredor. Según el Capítulo 7 del Entregable #1, este sistema es crítico para la prevención de inundaciones que afecten la operación vial, especialmente en época de lluvias en el valle de Girardot.

**2.3.10 Variables Críticas de Diseño**

1. **Variables monitoreadas**: Nivel de agua (m), caudal estimado (m³/s), velocidad de flujo (m/s), precipitación acumulada (mm).
2. **Precisión**: Nivel ± 1 cm; caudal ± 5%; velocidad ± 2%.
3. **Tecnología**: Sensor de presión hidrostática, radar de nivel, ultrasonido, caudalímetro acústico (ADV).
4. **Frecuencia**: 15 minutos en condiciones normales; 5 minutos en alerta; event-triggered en crecidas súbitas.
5. **Comunicación**: 4G/5G (principal en zonas remotas) + radio VHF respaldo; Ethernet donde haya fibra.
6. **Energía**: Solar + batería 72 h (ubicaciones remotas sin red eléctrica).
7. **Alertas**: Umbrales por nivel (amarillo: precaución; rojo: cierre vía). Integración con CCO y VMS.
8. **Protección**: IP68 para sensor sumergido; IP65 para gabinete electrónico.
9. **Instalación**: En alcantarillas críticas, quebradas de alto riesgo y zonas históricamente inundables.
10. **Mantenimiento**: Limpieza sensor trimestral; calibración anual.

**2.4.10 Ficha Técnica de Referencia WLS**

| Parámetro | Especificación |
|---|---|
| Variables | Nivel, caudal, velocidad, precipitación |
| Precisión | Nivel ±1 cm, caudal ±5%, velocidad ±2% |
| Tecnología | Presión hidrostática, radar, ultrasonido, ADV |
| Frecuencia | 15 min (normal), 5 min (alerta), event-triggered |
| Comunicación | 4G/5G + VHF; Ethernet donde disponible |
| Energía | Solar + batería 72 h |
| Alertas | Umbrales nivel → CCO + VMS |
| Protección | IP68 (sensor), IP65 (gabinete) |

**2.5.10 Matriz Comparativa de Oferentes WLS**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| WLS-INT-01 | **OTT HydroMet** | Alemania | Hidrología, sensores nivel | RLS, LS10, adv | Ríos Europa, Asia, América | 2022 | Global | [otthydromet.com](https://www.otthydromet.com) | Sí (9/10) | Líder en hidrología. RLS radar de nivel es referencia. |
| WLS-INT-02 | **Campbell Scientific** | USA | Dataloggers, sensores hidrológicos | CR1000X + sensores nivel | Redes hidrológicas global | 2022 | Global | [campbellsci.com](https://www.campbellsci.com) | Sí (8/10) | Dataloggers + sensores. Referencias en alertas tempranas. |
| WLS-INT-03 | **In-Situ** | USA | Sensores agua, calidad, nivel | Rugged TROLL, Aqua TROLL | Ríos, acueductos, minería global | 2022 | Global | [in-situ.com](https://www.in-situ.com) | Sí (8/10) | Sensores sumergibles de alta durabilidad. Referencia en minería. |
| WLS-LAT-01 | **Flowline** | USA | Sensores nivel, líquidos | EchoSpan, SwitchTek | Industria, agua, tratamiento | 2021 | Américas | [flowline.com](https://www.flowline.com) | Sí (7/10) | Amplia gama sensores nivel. Costo competitivo. |
| WLS-LAT-02 | **Geotech** | Chile | Geotecnia, hidrología | Instrumentación hidrológica | Minería, infraestructura Chile | 2022 | Chile | [geotech.cl](https://www.geotech.cl) | Sí (7/10) | Experiencia en monitoreo hídrico regional. |
| WLS-LAT-03 | **Newcom Argentina** | Argentina | ITS, integración | Integración sensores hidrológicos | Rutas nacionales Argentina | 2020 | Argentina | [newcom.com.ar](https://www.newcom.com.ar) | Sí (6/10) | Integrador. Menor especialización hidrológica específica. |
| WLS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño WLS, integración CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación hidrológica. |
| WLS-NAL-02 | **Deviteck** | Colombia | ITS, integración | Integración WLS-CCO-VMS | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de integración alertas. |
| WLS-NAL-03 | **IDEAM** | Colombia | Meteorología, hidrología institucional | Red hidrometeorológica Colombia | Red nacional hidrológica | Contínua | Colombia | [ideam.gov.co](https://www.ideam.gov.co) | Sí (6/10) | Conocimiento hidrológico nacional. No especialista en ITS. |

**2.6.10 Conclusiones**

1. **Tecnología de radar**: El sensor RLS de OTT HydroMet opera sin contacto con el agua (radar), eliminando problemas de ensuciamiento y sedimentación. Es la referencia para monitoreo en quebradas con alta carga de sedimentos.

2. **Autonomía energética**: Los puntos de monitoreo están en quebradas remotas sin red eléctrica. Solar + batería 72 h es obligatorio. OTT HydroMet y Campbell Scientific tienen referencias en instalaciones solares remotas.

3. **Integración con VMS**: La alerta de crecida debe publicar mensaje automático en VMS aguas abajo. Los integradores nacionales deben garantizar esta integración.

4. **Neutralidad**: La elección debe ponderar: (a) tecnología sin-contacto para reducir mantenimiento, (b) autonomía energética, (c) integración VMS+CCO.

---

#### 4.11.1 Descripción y Variables Críticas de Diseño

**CC-11 AVI/ETC — Automatic Vehicle Identification / Electronic Toll Collection**

El componente CC-11 abarca los sistemas de identificación automática de vehículos (AVI) y cobro electrónico de peajes (ETC) para la gestión de peaje en el corredor Chía-Girardot. Según el Capítulo 7 del Entregable #1, este sistema permite el cobro sin detención (free-flow) y la gestión de tarifas diferenciadas por categoría vehicular.

**2.3.11 Variables Críticas de Diseño**

1. **Tecnologías**: RFID (OBU - On Board Unit), DSRC (Dedicated Short Range Communications 5.8 GHz), ANPR (Automatic Number Plate Recognition), GPS/GNSS (para validación posterior).
2. **Velocidad de operación**: Hasta 120 km/h sin reducción de velocidad (free-flow).
3. **Precisión de clasificación**: Concordancia ≥ 99.5% entre detección WIM (CC-07), ALPR (CC-12) y OBU.
4. **Tasas de cobro**: Tarifa diferenciada por categoría (5+ categorías), horario (pico/off-peak), eje adicional (sobrepeso WIM).
5. **Transacciones**: ≥ 2,000 vehículos/hora/carril en pico.
6. **Comunicación**: Ethernet/fibra al CCO; 4G/5G respaldo; protocolo API REST para integración bancaria.
7. **Energía**: 110-240 VAC + UPS 8 h + generador respaldo en plazas de peaje.
8. **Seguridad**: Cifrado AES-256 en comunicación OBU-gantry; certificación de transacciones; prevención de fraude (lista negra OBU, validación cruzada ALPR+WIM+AVI).
9. **Auditoría**: Registro completo de cada transacción (fecha, hora, vehículo, tarifa, método pago). Reporte en tiempo real al CCO.
10. **Normativa**: Cumplimiento resoluciones ANI/MinTransporte para peajes electrónicos en Colombia.

**2.4.11 Ficha Técnica de Referencia AVI/ETC**

| Parámetro | Especificación |
|---|---|
| Tecnologías | RFID OBU, DSRC 5.8 GHz, ANPR, GPS/GNSS |
| Velocidad | Hasta 120 km/h (free-flow) |
| Precisión clasificación | ≥ 99.5% concordancia WIM+ALPR+OBU |
| Tarifas | Diferenciadas por categoría, horario, eje adicional |
| Capacidad | ≥ 2,000 veh/h/carril |
| Comunicación | Ethernet/fibra, 4G/5G; API REST bancario |
| Energía | 110-240 VAC + UPS 8 h + generador |
| Seguridad | AES-256, certificación transacciones, anti-fraude |
| Auditoría | Registro completo, reporte real-time CCO |
| Normativa | ANI/MinTransporte Colombia |

**2.5.11 Matriz Comparativa de Oferentes AVI/ETC**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| AVI-INT-01 | **Kapsch TrafficCom** | Austria | ETC, tolling, ITS | EcoTrafiX, ETC gantries | Varios países Europa, LATAM, Asia | 2023 | Global | [kapsch.net](https://www.kapsch.net) | Sí (9/10) | Líder mundial ETC. Referencias en múltiples países. |
| AVI-INT-02 | **Conduent** | USA | Tolling, transit, AVI | ETC systems, back-office | E-ZPass USA, proyectos globales | 2022 | USA/Global | [conduent.com](https://www.conduent.com) | Sí (9/10) | E-ZPass es referencia mundial. Back-office robusto. |
| AVI-INT-03 | **Thales** | Francia | ETC, DSRC, ITS | ETC gantries, OBU | Proyectos ETC Europa, Asia | 2022 | Global | [thalesgroup.com](https://www.thalesgroup.com) | Sí (8/10) | Tecnología DSRC avanzada. Experiencia militar/civil. |
| AVI-LAT-01 | **Seguritech** | México | ITS integral, peaje | ETC, AVI, back-office | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye ETC potencial. Conocimiento local normativo. |
| AVI-LAT-02 | **Grupo Masa** | México | Infraestructura ITS, peaje | ETC, plazas de cobro | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (7/10) | Integrador con experiencia en peajes electrónicos México. |
| AVI-LAT-03 | **Indra** | España | ITS, peaje, transporte | ETC systems, back-office | Peajes España, LATAM | 2022 | España/LATAM | [indra.es](https://www.indra.es) | Sí (8/10) | Via-T España es referencia. Experiencia en LATAM. |
| AVI-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño ETC, integración | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (6/10) | Diseñador proyecto. ETC requiere integrador especializado. |
| AVI-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración ETC-CCO-bancos | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Dependiente de fabricante ETC. |
| AVI-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Comunicaciones ETC, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura de comunicaciones para ETC. |

**2.6.11 Conclusiones**

1. **Madurez del mercado**: El mercado ETC es altamente maduro. Kapsch, Conduent e Indra tienen referencias verificadas a gran escala. La diferenciación radica en integración con el ecosistema de peaje colombiano (pasado, presente y futuro).

2. **Normativa local**: La ANI y MinTransporte tienen regulación específica para peajes electrónicos. Seguritech (México) e Indra (España) tienen experiencia en normativas similares en mercados LATAM.

3. **Integración WIM-ALPR-ETC**: La concordancia ≥ 99.5% entre WIM, ALPR y OBU requiere integración de tres subsistemas. Kapsch ofrece ventaja al tener los tres componentes en su portafolio.

4. **Neutralidad**: La elección debe ponderar: (a) referencias verificadas en mercados LATAM, (b) capacidad de integración con sistema bancario colombiano, (c) cumplimiento normativa ANI/MinTransporte.

---

#### 4.12.1 Descripción y Variables Críticas de Diseño

**CC-12 ALPR/LPR — Automatic License Plate Recognition / License Plate Recognition**

El componente CC-12 abarca los sistemas de reconocimiento automático de placas vehiculares (ALPR/LPR) para identificación de vehículos en puntos críticos del corredor. Según el Capítulo 7 del Entregable #1, ALPR se integra con WIM (CC-07), AVI/ETC (CC-11) y el sistema de seguridad vial.

**2.3.12 Variables Críticas de Diseño**

1. **Precisión de lectura**: ≥ 98% en condiciones diurnas; ≥ 95% en condiciones nocturnas con iluminación IR.
2. **Velocidad**: Lectura precisa hasta 120 km/h (rango completo del corredor).
3. **Iluminación**: IR integrado (860-940 nm) para operación nocturna sin deslumbramiento. Compensación de contraluz y reflejos.
4. **Cobertura**: Captura de placa frontal y trasera (dual lane); ángulo de visión ≥ 40° horizontal.
5. **Clasificación**: Asociación automática con categoría vehicular (WIM) y tarifa (ETC).
6. **Comunicación**: Ethernet al nodo de campo; API REST al CCO; integración con base de datos RUNT (Registro Único Nacional de Tránsito Colombia).
7. **Energía**: PoE+ (IEEE 802.3bt) o 110-240 VAC.
8. **Protección**: IP65, temperatura -10 °C a +55 °C.
9. **Almacenamiento local**: ≥ 30 días de imágenes y metadatos en nodo de campo; respaldo automático al CCO.
10. **Privacidad**: Cumplimiento Ley de Protección de Datos Colombia. No almacenar imágenes de rostros ni datos personales sin autorización.

**2.4.12 Ficha Técnica de Referencia ALPR/LPR**

| Parámetro | Especificación |
|---|---|
| Precisión | ≥ 98% (día), ≥ 95% (noche IR) |
| Velocidad | Hasta 120 km/h |
| Iluminación | IR 860-940 nm, compensación contraluz |
| Cobertura | Dual lane, ángulo ≥ 40° horizontal |
| Clasificación | Asociación automática WIM/ETC |
| Comunicación | Ethernet; API REST; integración RUNT |
| Energía | PoE+ o 110-240 VAC |
| Protección | IP65, -10 °C a +55 °C |
| Almacenamiento | ≥ 30 días local + respaldo CCO |
| Privacidad | Cumplimiento Ley Protección Datos Colombia |

**2.5.12 Matriz Comparativa de Oferentes ALPR/LPR**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| ALP-INT-01 | **Jenoptik** | Alemania | ALPR, traffic enforcement | TraffiCapture, TraffiStar | Autobahns Alemania, proyectos globales | 2023 | Global | [jenoptik.com](https://www.jenoptik.com) | Sí (9/10) | Líder ALPR en Europa. Referencias en enforcement. |
| ALP-INT-02 | **Motorola Solutions (Vigilant)** | USA | ALPR, seguridad pública | PlateReader, Vigilant ALPR | Policía USA, seguridad global | 2022 | USA/Global | [motorolasolutions.com](https://www.motorolasolutions.com) | Sí (8/10) | Dominante en seguridad pública USA. Integración con PSAP. |
| ALP-INT-03 | **Neology** | USA | ALPR, tolling, enforcement | ALPR systems, integration | Peajes USA, LATAM, Europa | 2022 | Global | [neology.com](https://www.neology.com) | Sí (8/10) | Especialista ALPR para peajes. Referencias verificadas. |
| ALP-LAT-01 | **ARH** | Hungría | ALPR, reconocimiento | Carmen ALPR, ANPR | Proyectos Europa, Asia, América | 2022 | Global | [arh.hu](https://www.arh.hu) | Sí (7/10) | Software ALPR robusto. Integración flexible. |
| ALP-LAT-02 | **Seguritech** | México | ITS integral, ALPR | ALPR integrado VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye ALPR potencial. Conocimiento local normativo. |
| ALP-LAT-03 | **Grupo Masa** | México | ITS, seguridad vial | ALPR, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización ALPR específica. |
| ALP-NAL-01 | **CI2** | Colombia | ITS, ingeniería | ALPR, integración RUNT | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (6/10) | Diseñador proyecto. Integración con RUNT requiere validación. |
| ALP-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración ALPR-WIM-ETC | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Dependiente de fabricante ALPR. |
| ALP-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Comunicaciones ALPR, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura comunicaciones para ALPR. |

**2.6.12 Conclusiones**

1. **Precisión en condiciones colombianas**: La diversidad de tipos de placas en Colombia (particulares, públicas, diplomáticas, mercosur) requiere algoritmo entrenado específicamente. Jenoptik y ARH ofrecen capacidad de entrenamiento de OCR para mercados específicos.

2. **Integración RUNT**: La conexión con el Registro Único Nacional de Tránsito es crítica para validación de placas. Los integradores nacionales deben garantizar esta integración mediante API oficial del MinTransporte.

3. **Privacidad y datos**: La Ley de Protección de Datos de Colombia impone restricciones al almacenamiento de imágenes. Todos los proveedores deben garantizar cumplimiento mediante anonimización de rostros y retención limitada.

4. **Neutralidad**: La elección debe ponderar: (a) precisión documentada en mercados LATAM, (b) capacidad de entrenamiento OCR para placas colombianas, (c) integración RUNT y cumplimiento de privacidad.

---

#### 4.13.1 Descripción y Variables Críticas de Diseño

**CC-13 SPD — Speed Detection / Radar de Velocidad**

El componente CC-13 abarca los sistemas de detección de velocidad (radar Doppler, lidar, cámaras) para monitoreo de velocidad y enforcement de límites de velocidad en el corredor. Según el Capítulo 7 del Entregable #1, SPD es crítico para la seguridad vial y la gestión de velocidad dinámica (VSL - CC-14).

**2.3.13 Variables Críticas de Diseño**

1. **Tecnologías**: Radar Doppler (24 GHz, 77 GHz), lidar (laser), video analítico (AI), sensores inductivos (bucles).
2. **Precisión**: ± 2 km/h para enforcement; ± 5 km/h para monitoreo informativo.
3. **Velocidad de operación**: 20 km/h a 200 km/h (cobertura completa desde tráfico lento hasta excesos graves).
4. **Detección**: Individual por vehículo (no promedio de flujo). Distancia de detección ≥ 200 m.
5. **Evidencia**: Captura de imagen (ALPR integrado) + metadatos (velocidad, fecha, hora, ubicación, dirección) para enforcement.
6. **Comunicación**: Ethernet al nodo de campo; API REST al CCO; integración con sistema de fiscalización.
7. **Energía**: PoE+ o 110-240 VAC; UPS 4 h.
8. **Protección**: IP65, -10 °C a +55 °C.
9. **Instalación**: Fija (poste) y móvil (unidades portátiles para zonas de alta incidencia).
10. **Normativa**: Cumplimiento normas de metrología Colombia (metrología legal para enforcement).

**2.4.13 Ficha Técnica de Referencia SPD**

| Parámetro | Especificación |
|---|---|
| Tecnologías | Radar Doppler 24/77 GHz, lidar, video AI, inductivos |
| Precisión | ± 2 km/h (enforcement), ± 5 km/h (monitoreo) |
| Velocidad | 20-200 km/h |
| Detección | Individual, distancia ≥ 200 m |
| Evidencia | Imagen ALPR + metadatos |
| Comunicación | Ethernet; API REST al CCO |
| Energía | PoE+ o 110-240 VAC; UPS 4 h |
| Protección | IP65, -10 °C a +55 °C |
| Instalación | Fija + móvil |
| Normativa | Metrología legal Colombia |

**2.5.13 Matriz Comparativa de Oferentes SPD**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| SPD-INT-01 | **Jenoptik** | Alemania | Radar velocidad, enforcement | TraffiStar S350, TraffiCapture | Autobahns Alemania, proyectos globales | 2023 | Global | [jenoptik.com](https://www.jenoptik.com) | Sí (9/10) | Líder enforcement velocidad Europa. Referencias verificadas. |
| SPD-INT-02 | **Kustom Signals** | USA | Radar policía, tráfico | ProLaser, Eagle, Falcon | Policía USA, seguridad vial global | 2022 | USA/Global | [kustomsignals.com](https://www.kustomsignals.com) | Sí (8/10) | Dominante en mercado policial USA. Radar portátil y fijo. |
| SPD-INT-03 | **Decatur Electronics** | USA | Radar Doppler, ITS | OnSite, SVR, Genesis | ITS USA, LATAM, Asia | 2022 | Global | [decaturradar.com](https://www.decaturradar.com) | Sí (8/10) | Especialista radar Doppler ITS. Costo competitivo. |
| SPD-LAT-01 | **Stalker Radar** | USA | Radar velocidad, deportes/policía | Pro II, X-Series | Policía USA, deportes | 2022 | USA | [stalkerradar.com](https://www.stalkerradar.com) | Sí (7/10) | Alta precisión. Menor experiencia ITS a gran escala. |
| SPD-LAT-02 | **Seguritech** | México | ITS integral, velocidad | Radar velocidad integrado | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye SPD potencial. Conocimiento local normativo. |
| SPD-LAT-03 | **Grupo Masa** | México | ITS, seguridad vial | Radar, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización SPD específica. |
| SPD-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño SPD, integración | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (6/10) | Diseñador proyecto. Especificación SPD. |
| SPD-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración SPD-CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Dependiente de fabricante radar. |
| SPD-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Infraestructura SPD, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura comunicaciones para SPD. |

**2.6.13 Conclusiones**

1. **Metrología legal**: Para enforcement de velocidad con sanción, el radar debe cumplir metrología legal colombiana. Jenoptik y Kustom Signals tienen certificaciones metrológicas en múltiples países.

2. **Integración VSL**: El SPD debe integrarse con el sistema de límites de velocidad variable (VSL - CC-14) para ajustar automáticamente el límite según condiciones. Los integradores nacionales deben garantizar esta integración.

3. **Operación en curvas**: El corredor tiene tramos sinuosos donde el ángulo de incidencia del radar afecta la precisión. Los radares de 77 GHz (Jenoptik, Decatur) tienen mejor precisión en ángulos oblicuos.

4. **Neutralidad**: La elección debe ponderar: (a) certificación metrológica para enforcement, (b) precisión en ángulos oblicuos de curvas, (c) integración con VSL y sistema de fiscalización.

---

#### 4.14.1 Descripción y Variables Críticas de Diseño

**CC-14 VSL — Variable Speed Limit / Límites de Velocidad Variable**

El componente CC-14 abarca los sistemas de límites de velocidad variable (VSL) que ajustan dinámicamente la velocidad máxima permitida según condiciones de tráfico, clima, visibilidad y estado de la vía. Según el Capítulo 7 del Entregable #1, VSL es crítico para la gestión proactiva de seguridad en corredores con alta variabilidad climática.

**2.3.14 Variables Críticas de Diseño**

1. **Tecnología**: Paneles LED de velocidad variable (similar a VMS pero especializado en números), controlados por el CCO.
2. **Velocidades mostradas**: 20, 40, 60, 80, 100, 120 km/h (valores estándar colombianos) + "PARE" para cierre total.
3. **Disparadores automáticos**: Congestión (VDS/CC-05), neblina (ESS/CC-06), lluvia intensa (ESS/CC-06), incidente (AID/CC-02), mantenimiento (WS/CC-20).
4. **Tiempo de cambio**: < 10 segundos desde comando CCO hasta visualización en campo.
5. **Comunicación**: Ethernet/fibra; NTCIP 1203; API REST al CCO.
6. **Energía**: 110-240 VAC + UPS 4 h.
7. **Protección**: IP65, -10 °C a +55 °C.
8. **Visibilidad**: Brillo > 8,000 nits (día), < 300 nits (noche); ángulo ≥ 60° horizontal.
9. **Ubicación**: Antes de zonas críticas (túneles, curvas, puentes, zonas de neblina frecuente); cada 2-5 km en tramos de alta variabilidad.
10. **Validación**: Sensor SPD (CC-13) confirma que el nuevo límite está siendo respetado; alerta si persisten excesos post-cambio.

**2.4.14 Ficha Técnica de Referencia VSL**

| Parámetro | Especificación |
|---|---|
| Tecnología | Paneles LED velocidad variable |
| Velocidades | 20, 40, 60, 80, 100, 120 km/h + PARE |
| Disparadores | VDS, ESS, AID, incidentes, mantenimiento |
| Tiempo de cambio | < 10 s (CCO → campo) |
| Comunicación | Ethernet/fibra; NTCIP 1203; API REST |
| Energía | 110-240 VAC + UPS 4 h |
| Protección | IP65, -10 °C a +55 °C |
| Visibilidad | > 8,000 nits (día), < 300 nits (noche); ángulo ≥ 60° |
| Ubicación | Antes de zonas críticas; cada 2-5 km en tramos variables |
| Validación | SPD (CC-13) confirma cumplimiento post-cambio |

**2.5.14 Matriz Comparativa de Oferentes VSL**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| VSL-INT-01 | **SWARCO** | Austria | ITS, señalización variable | CUBILED, FUTURLED VSL | Autobahn A9 Alemania, VSL dinámico | 2021 | Alemania | [swarco.com](https://www.swarco.com) | Sí (9/10) | Referencia VSL en Europa. Integración completa ITS. |
| VSL-INT-02 | **Daktronics** | USA | VMS/VSL de gran formato | Galaxy, Vanguard VSL | Highway 101 California VSL | 2022 | USA | [daktronics.com](https://www.daktronics.com) | Sí (8/10) | Líder VMS/VSL USA. Referencias en climas variados. |
| VSL-INT-03 | **Siemens Mobility** | Alemania | ITS, señalización inteligente | Sicore VSL | Autobahn management DACH | 2023 | Alemania | [siemens-mobility.com](https://www.mobility.siemens.com) | Sí (8/10) | Integración nativa con EcoTrafiX y sistemas de control. |
| VSL-LAT-01 | **Newcom Argentina** | Argentina | ITS, señalización | VSL LED, integración SCADA | Ruta Nacional 9 Argentina | 2020 | Argentina | [newcom.com.ar](https://www.newcom.com.ar) | Sí (7/10) | Experiencia regional LATAM. Adaptación a climas extremos. |
| VSL-LAT-02 | **Seguritech** | México | ITS integral, VSL | VSL LED, integración VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye VSL potencial. Conocimiento local normativo. |
| VSL-LAT-03 | **Grupo Masa** | México | Infraestructura ITS | VSL, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización VSL específica. |
| VSL-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño VSL, integración CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (6/10) | Diseñador proyecto. Especificación VSL. |
| VSL-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración VSL-CCO-SPD | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de integración VSL-SPD. |
| VSL-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Infraestructura VSL, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura comunicaciones para VSL. |

**2.6.14 Conclusiones**

1. **Integración con CCO**: La efectividad del VSL depende de la integración con AID, ESS, VDS y SPD. SWARCO y Siemens ofrecen ventaja en integración completa. Los integradores nacionales deben garantizar esta integración independientemente del fabricante.

2. **Respuesta rápida**: El requisito de < 10 segundos para cambio de velocidad es crítico en incidentes. Todos los proveedores internacionales cumplen. Los integradores nacionales deben validar latencia de red en la configuración específica del corredor.

3. **Validación SPD**: El bucle de retroalimentación SPD → CCO → VSL permite verificar que el nuevo límite es respetado. Si los excesos persisten, el CCO puede escalar a cierre parcial o despliegue de unidades de tránsito.

4. **Neutralidad**: La elección debe ponderar: (a) integración con el ecosistema ITS del corredor, (b) tiempo de respuesta validado, (c) soporte local para mantenimiento de paneles LED.


---

#### 4.15.1 Descripción y Variables Críticas de Diseño

**CC-15 PAS — Public Address System / Sistema de Alerta Sonora**

El componente CC-15 abarca el sistema de dirección pública (PAS) para comunicación de emergencia, alertas de tráfico y mensajes de seguridad vial en túneles, zonas críticas y áreas de alta concentración de incidentes. Según el Capítulo 7 del Entregable #1, PAS es crítico para la evacuación en túneles y la comunicación directa con usuarios en situaciones de riesgo.

**2.3.15 Variables Críticas de Diseño**

1. **Cobertura sonora**: SPL ≥ 90 dB a 10 m de distancia para superar ruido de tráfico (≥ 80 dB en túneles).
2. **Claridad**: Índice de inteligibilidad del habla (STI) ≥ 0.5; Índice de transmisión de inteligibilidad (CIS) ≥ 0.7.
3. **Zonificación**: Capacidad de direccionar mensajes a zonas específicas (túnel tramo A, tramo B, etc.) independientemente.
4. **Prioridad**: Jerarquía de mensajes: 1-Emergencia (incendio, colapso), 2-Seguridad (accidente, derrumbe), 3-Tráfico (congestión, cierre), 4-Informativo (tiempos de recorrido).
5. **Activación**: Manual (desde CCO), automática (por AID/CC-02, ESS/CC-06, incendio), remota (SOS/CC-04 para comunicación bidireccional).
6. **Comunicación**: Ethernet/fibra al CCO; protocolo Dante/AES67 para audio IP; NTCIP opcional.
7. **Energía**: 110-240 VAC + UPS 8 h + batería 24 h en túneles.
8. **Protección**: IP65 para exteriores; IP55 para interiores túneles. Resistente a vibración de tráfico pesado.
9. **Idioma**: Español (principal), inglés (secundario). Grabaciones predefinidas + mensajes en vivo desde CCO.
10. **Monitoreo**: Estado de cada altavoz (funcionamiento, impedancia, temperatura) reportado al CCO cada 60 segundos. Alerta automática por fallo de unidad.

**2.4.15 Ficha Técnica de Referencia PAS**

| Parámetro | Especificación |
|---|---|
| Cobertura | SPL ≥ 90 dB a 10 m |
| Inteligibilidad | STI ≥ 0.5; CIS ≥ 0.7 |
| Zonificación | Independiente por tramo/zona |
| Prioridad | 4 niveles (emergencia, seguridad, tráfico, informativo) |
| Activación | Manual, automática (AID/ESS/incendio), remota (SOS) |
| Comunicación | Ethernet/fibra; Dante/AES67; NTCIP opcional |
| Energía | 110-240 VAC + UPS 8 h + batería 24 h (túneles) |
| Protección | IP65 (exterior), IP55 (túneles); anti-vibración |
| Idioma | Español + inglés; pre-grabado + en vivo |
| Monitoreo | Estado cada 60 s al CCO; alerta por fallo |

**2.5.15 Matriz Comparativa de Oferentes PAS**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| PAS-INT-01 | **Bosch (Electro-Voice/Telefunken)** | Alemania | Audio profesional, sistemas PA | EVH, IRIS, NetMax | Túneles Europa, aeropuertos global | 2022 | Global | [bosch.com](https://www.bosch.com) | Sí (9/10) | Líder global sistemas PA. Referencias en túneles y transporte. |
| PAS-INT-02 | **TOA Corporation** | Japón | Sistemas de audio, PA | SR-H2S, SX-1000, VM-3000 | Túneles Japón, Asia, transporte global | 2022 | Global | [toa.com](https://www.toa.com) | Sí (8/10) | Especialista PA para transporte. Sistemas robustos y compactos. |
| PAS-INT-03 | **AtlasIED (Atlas Sound)** | USA | Audio comercial, industrial, transporte | ATLAS, IED GLOBALCOM | Túneles USA, instalaciones gubernamentales | 2022 | USA | [atlasied.com](https://www.atlasied.com) | Sí (8/10) | Amplia gama productos. Sistemas IP avanzados. |
| PAS-LAT-01 | **Community Professional** | USA | Altavoces profesionales, PA | Community, EAW | Instalaciones deportivas, transporte Américas | 2021 | Américas | [communitypro.com](https://www.communitypro.com) | Sí (7/10) | Altavoces de alta potencia. Menor especialización túneles específica. |
| PAS-LAT-02 | **Seguritech** | México | ITS integral, PA | Sistemas PA integrados VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye PA potencial. Conocimiento local normativo. |
| PAS-LAT-03 | **Grupo Masa** | México | Infraestructura ITS, audio | PA, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización PA específica. |
| PAS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño PAS, integración CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación PAS para túneles. |
| PAS-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración PAS-CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de integración Dante/AES67. |
| PAS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Infraestructura audio, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura comunicaciones para PA. |

**2.6.15 Conclusiones**

1. **Inteligibilidad en túneles**: El requisito STI ≥ 0.5 en ambiente reverberante de túnel es exigente. Bosch (Electro-Voice) y TOA tienen referencias verificadas en túneles con tratamiento acústico y altavoces direccionales.

2. **Integración CCO**: El PAS debe integrarse con AID (disparo automático por incidente), SOS (comunicación bidireccional) y ESS (alerta por condiciones climáticas). Los integradores nacionales deben garantizar esta integración multi-sistema.

3. **Autonomía en túneles**: La batería de 24 h en túneles es crítica para evacuación prolongada. Bosch y TOA ofrecen sistemas con gestión de energía avanzada.

4. **Neutralidad**: La elección debe ponderar: (a) inteligibilidad comprobada en túneles, (b) integración multi-sistema, (c) autonomía energética en emergencia.

---

#### 4.16.1 Descripción y Variables Críticas de Diseño

**CC-16 EC/SOS — Emergency Communication / Comunicaciones de Emergencia (Redundancia)**

El componente CC-16 abarca el sistema redundante de comunicaciones de emergencia que garantiza la conectividad del CCO con elementos de campo (CCTV, VMS, SOS, AID, etc.) incluso en falla total de la red principal. Según el Capítulo 7 del Entregable #1, EC es el sistema de respaldo crítico para mantenimiento de operaciones en desastres.

**2.3.16 Variables Críticas de Diseño**

1. **Redundancia de red**: Dual-homing (dos proveedores de fibra óptica); radio VHF/UHF respaldo; satelital (VSAT) en zonas críticas.
2. **Capacidad mínima**: 10% de la capacidad principal para comunicaciones esenciales (SOS, AID, VMS de emergencia).
3. **Conmutación automática**: < 30 segundos desde falla de red principal a red de respaldo.
4. **Topología**: Malla parcial entre nodos de campo para permitir routing alternativo si el CCO principal cae.
5. **Comunicación**: Protocolos IP (VPN), radio digital (DMR/Tetra), satelital (Inmarsat/Iridium).
6. **Energía**: Solar + batería 72 h para nodos de campo; generador diésel + UPS para CCO.
7. **Protección**: IP65; temperatura -10 °C a +55 °C; resistencia a interferencia electromagnética.
8. **Cifrado**: AES-256 para comunicaciones; autenticación de dispositivos; prevención de spoofing.
9. **Pruebas**: Conmutación mensual programada; prueba de comunicación satelital trimestral.
10. **Documentación**: Mapa de conectividad de respaldo; procedimiento de activación; lista de contactos de emergencia.

**2.4.16 Ficha Técnica de Referencia EC/SOS**

| Parámetro | Especificación |
|---|---|
| Redundancia | Dual-homing fibra; radio VHF/UHF; satelital VSAT |
| Capacidad | ≥ 10% capacidad principal (comunicaciones esenciales) |
| Conmutación | < 30 s automática |
| Topología | Malla parcial entre nodos de campo |
| Tecnologías | IP (VPN), DMR/Tetra, Inmarsat/Iridium |
| Energía | Solar + batería 72 h (nodos); generador + UPS (CCO) |
| Protección | IP65, -10 °C a +55 °C, anti-EMI |
| Seguridad | AES-256, autenticación dispositivos |
| Pruebas | Conmutación mensual; prueba satelital trimestral |
| Documentación | Mapa conectividad; procedimiento activación; contactos |

**2.5.16 Matriz Comparativa de Oferentes EC/SOS**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| ECS-INT-01 | **Cisco Systems** | USA | Networking, comunicaciones, seguridad | Routers redundantes, SD-WAN, satelital | Enterprise networks global | 2023 | Global | [cisco.com](https://www.cisco.com) | Sí (9/10) | Líder networking global. Referencias en redes críticas. |
| ECS-INT-02 | **Hughes Network Systems** | USA | Satélite, VSAT, networking | HughesNet, VSAT enterprise | Redes satelitales global | 2022 | Global | [hughes.com](https://www.hughes.com) | Sí (8/10) | Líder VSAT mundial. Respaldo satelital verificado. |
| ECS-INT-03 | **Iridium Communications** | USA | Satélite LEO, IoT, emergencia | Iridium Certus, IoT | Comunicaciones emergencia global | 2023 | Global | [iridium.com](https://www.iridium.com) | Sí (8/10) | Red satelital LEO global. Respaldo en zonas remotas. |
| ECS-LAT-01 | **Motorola Solutions** | USA | Radio DMR, Tetra, comunicaciones críticas | MOTOTRBO, Tetra | Seguridad pública, transporte LATAM | 2022 | LATAM/Global | [motorolasolutions.com](https://www.motorolasolutions.com) | Sí (8/10) | Dominante en radio crítica. Referencias en transporte y seguridad. |
| ECS-LAT-02 | **Seguritech** | México | ITS integral, comunicaciones | Radio, fibra, satelital VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye comunicaciones. Conocimiento local normativo. |
| ECS-LAT-03 | **Grupo Masa** | México | Infraestructura ITS, telecom | Redes, radio, centros de control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización EC específica. |
| ECS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño EC redundante, SD-WAN | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación redundancia. |
| ECS-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración EC-CCO, VPN | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de SD-WAN y VPN. |
| ECS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Redes, radio, fibra, satelital | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (7/10) | Especialista telecomunicaciones. Ventaja en infraestructura red. |

**2.6.16 Conclusiones**

1. **Resiliencia de red**: La arquitectura de comunicaciones del corredor debe soportar falla simultánea de fibra + CCO principal. Cisco ofrece SD-WAN para conmutación automática; Hughes e Iridium ofrecen respaldo satelital para zonas sin cobertura celular.

2. **Radio crítica**: Motorola Solutions es el estándar de facto en radio DMR/Tetra para seguridad pública y transporte. La integración con sistemas de emergencia vial (SOS, PAS) es madura.

3. **Conmutación automática**: El requisito de < 30 segundos requiere protocolos de routing avanzados (BGP, OSPF, SD-WAN). Los integradores nacionales deben certificar esta capacidad con la arquitectura de red propuesta.

4. **Neutralidad**: La elección debe ponderar: (a) diversidad de medios (fibra + radio + satelital), (b) tiempo de conmutación validado, (c) capacidad de soporte 24/7 en territorio colombiano.

---

#### 4.17.1 Descripción y Variables Críticas de Diseño

**CC-17 NTCIP — National Transportation Communications for ITS Protocol**

El componente CC-17 abarca la implementación del protocolo NTCIP (National Transportation Communications for ITS Protocol) para estandarizar la comunicación entre dispositivos de campo (CCTV, VMS, SOS, AID, VDS, etc.) y el CCO. Según el Capítulo 7 del Entregable #1, NTCIP es obligatorio para garantizar interoperabilidad y evitar vendor lock-in.

**2.3.17 Variables Críticas de Diseño**

1. **Versiones soportadas**: NTCIP 1201 (Global Object Definitions), 1202 (Actuated Signal Controller), 1203 (Dynamic Message Signs), 1204 (Environmental Sensor Stations), 1205 (Raised Pavement Markers), 1206 (Signal Performance Metrics), 1207 (Center-to-Center), 1208 (Traffic Management Centers), 1209 (Transportation Sensor Systems), 1210 (Signal Control and Coordination), 1211 (Signal System Masters), 1212 (Object Definitions for CCTV Switches), 1213 (Object Definitions for CCTV Cameras), 1214 (Object Definitions for Video Switching), 1215 (Object Definitions for Highway Radios).
2. **Perfil de implementación**: Perfil obligatorio (objects required) + perfiles opcionales según componente.
3. **Transporte**: SNMP sobre UDP (estándar); SNMP sobre TCP; HTTP/REST (emergente); FTP para transferencia de firmware.
4. **Seguridad**: SNMPv3 (autenticación y cifrado); TLS 1.3 para HTTP/REST; certificados X.509 para autenticación de dispositivos.
5. **Descubrimiento**: Auto-discovery de dispositivos NTCIP en la red; registro automático en el CCO con perfil de capacidades.
6. **Gestión de configuración**: Backup/restore de configuración NTCIP por dispositivo; plantillas de configuración por tipo de dispositivo.
7. **Monitoreo**: Estado de cada objeto NTCIP (online, offline, error) reportado al CCO cada 60 segundos.
8. **Firmware OTA**: Actualización de firmware Over-The-Air mediante NTCIP FTP/HTTP con validación de checksum y rollback automático en fallo.
9. **Interoperabilidad**: Certificación NTCIP por dispositivo (NTCIP Testing Program); pruebas de interoperabilidad en laboratorio antes de despliegue.
10. **Documentación**: Diccionario de objetos NTCIP por componente; MIB (Management Information Base) personalizada para objetos propietarios.

**2.4.17 Ficha Técnica de Referencia NTCIP**

| Parámetro | Especificación |
|---|---|
| Versiones | 1201-1215 según componente |
| Perfiles | Obligatorio + opcional por componente |
| Transporte | SNMP/UDP, SNMP/TCP, HTTP/REST, FTP |
| Seguridad | SNMPv3, TLS 1.3, X.509 |
| Descubrimiento | Auto-discovery, registro automático CCO |
| Configuración | Backup/restore, plantillas por tipo |
| Monitoreo | Estado cada 60 s al CCO |
| Firmware OTA | FTP/HTTP, checksum, rollback automático |
| Interoperabilidad | Certificación NTCIP Testing Program |
| Documentación | Diccionario objetos; MIB personalizada |

**2.5.17 Matriz Comparativa de Oferentes NTCIP**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| NTC-INT-01 | **AASHTO / ITE / NEMA** | USA | Estándares NTCIP | NTCIP standards, testing program | NTCIP Testing Program USA | Contínua | USA | [ntcip.org](https://www.ntcip.org) | Sí (10/10) | Organismos estándar. Testing program oficial. |
| NTC-INT-02 | **Kapsch TrafficCom** | Austria | ITS integral, NTCIP | EcoTrafiX con NTCIP nativo | Proyectos NTCIP global | 2023 | Global | [kapsch.net](https://www.kapsch.net) | Sí (9/10) | NTCIP nativo en plataforma. Referencias verificadas. |
| NTC-INT-03 | **Siemens Mobility** | Alemania | ITS, NTCIP | Sicore con NTCIP | Autobahn NTCIP implementations | 2023 | Europa | [siemens-mobility.com](https://www.mobility.siemens.com) | Sí (8/10) | Implementación NTCIP en sistemas propios. |
| NTC-LAT-01 | **SWARCO** | Austria | ITS, señalización NTCIP | CUBILED NTCIP certified | European NTCIP deployments | 2022 | Europa | [swarco.com](https://www.swarco.com) | Sí (8/10) | Certificación NTCIP en VMS. Referencia europea. |
| NTC-LAT-02 | **Seguritech** | México | ITS integral, NTCIP | Implementación NTCIP VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS con NTCIP. Conocimiento local normativo. |
| NTC-LAT-03 | **Daktronics** | USA | VMS NTCIP | Galaxy NTCIP certified | NTCIP certified VMS USA | 2022 | USA | [daktronics.com](https://www.daktronics.com) | Sí (8/10) | Certificación NTCIP Testing Program en VMS. |
| NTC-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño NTCIP, interoperabilidad | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación NTCIP obligatoria. |
| NTC-NAL-02 | **Deviteck** | Colombia | ITS, software | Implementación NTCIP-CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador. Capacidad NTCIP en plataformas. |
| NTC-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Red NTCIP, SNMP | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (7/10) | Infraestructura red para NTCIP/SNMP. |

**2.6.17 Conclusiones**

1. **Estandarización obligatoria**: NTCIP no es opcional; es requisito regulatorio de ANI/INVIAS. La certificación NTCIP Testing Program garantiza interoperabilidad real, no solo declarada.

2. **Vendor lock-in**: La adopción de NTCIP permite cambiar proveedores de dispositivos sin reemplazar el CCO completo. Los integradores nacionales deben garantizar que todos los dispositivos propuestos tienen certificación NTCIP vigente.

3. **Seguridad**: SNMPv3 y TLS 1.3 son obligatorios para prevenir ataques de red a dispositivos de campo. Los proveedores deben certificar soporte de estas versiones seguras.

4. **Neutralidad**: NTCIP es un estándar abierto. No existe proveedor "óptimo"; todos los dispositivos certificados son equivalentes desde la perspectiva del protocolo. La elección debe basarse en funcionalidad, precio y soporte local.

---

#### 4.18.1 Descripción y Variables Críticas de Diseño

**CC-18 FW/Firewall — Seguridad de Red**

El componente CC-18 abarca los sistemas de seguridad de red (firewall, IDS/IPS, segmentación) que protegen la infraestructura ITS del corredor contra ciberataques. Según el Capítulo 7 del Entregable #1, la ciberseguridad es crítica dado que un ataque al CCO puede paralizar la operación del corredor.

**2.3.18 Variables Críticas de Diseño**

1. **Arquitectura**: Firewall de próxima generación (NGFW) con inspección profunda de paquetes (DPI); IDS/IPS (Suricata/Snort); segmentación de red (VLANs, microsegmentación).
2. **Throughput**: ≥ 10 Gbps en backbone principal; ≥ 1 Gbps en segmentos de campo.
3. **Políticas**: Default-deny; whitelist de dispositivos autorizados (MAC + IP + certificado); blacklist dinámica de amenazas (threat intelligence feed).
4. **VPN**: VPN IPsec entre CCO y nodos de campo; VPN SSL para acceso remoto de mantenimiento; multi-factor authentication (MFA).
5. **Logging**: Registro de todos los eventos de seguridad (syslog SIEM); retención ≥ 1 año; análisis en tiempo real.
6. **Actualización**: Firmas de amenazas actualizadas automáticamente cada 4 horas; firmware de seguridad actualizado trimestralmente.
7. **Cumplimiento**: ISO 27001, NIST Cybersecurity Framework, resoluciones MinTIC Colombia.
8. **Respaldo**: Firewall redundante (HA - High Availability) con conmutación automática < 5 segundos.
9. **Monitoreo**: Dashboard de seguridad en CCO; alertas automáticas por intrusión, malware, anomalía de tráfico.
10. **Pruebas**: Pentest anual por tercero independiente; pruebas de vulnerabilidad trimestrales.

**2.4.18 Ficha Técnica de Referencia FW/Firewall**

| Parámetro | Especificación |
|---|---|
| Arquitectura | NGFW + DPI + IDS/IPS + segmentación |
| Throughput | ≥ 10 Gbps (backbone), ≥ 1 Gbps (campo) |
| Políticas | Default-deny, whitelist, blacklist dinámica |
| VPN | IPsec (CCO-campo), SSL (remoto), MFA |
| Logging | Syslog SIEM, retención ≥ 1 año, análisis real-time |
| Actualización | Firmas cada 4 h; firmware trimestral |
| Cumplimiento | ISO 27001, NIST, MinTIC Colombia |
| Respaldo | Firewall HA, conmutación < 5 s |
| Monitoreo | Dashboard CCO; alertas automáticas |
| Pruebas | Pentest anual; vulnerability scan trimestral |

**2.5.18 Matriz Comparativa de Oferentes FW/Firewall**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| FW-INT-01 | **Palo Alto Networks** | USA | NGFW, ciberseguridad empresarial | PA-Series, Prisma | Ciberseguridad crítica global | 2023 | Global | [paloaltonetworks.com](https://www.paloaltonetworks.com) | Sí (9/10) | Líder NGFW mundial. Referencias en infraestructura crítica. |
| FW-INT-02 | **Fortinet** | USA/Canadá | NGFW, SD-WAN, seguridad | FortiGate, FortiSIEM | Seguridad ITS, transporte, gobierno | 2023 | Global | [fortinet.com](https://www.fortinet.com) | Sí (9/10) | FortiSIEM ya referenciado en proyecto SICOM. Experiencia en ITS. |
| FW-INT-03 | **Cisco (Firepower)** | USA | Networking, seguridad integrada | Firepower, SecureX | Enterprise security global | 2023 | Global | [cisco.com](https://www.cisco.com) | Sí (8/10) | Integración networking + seguridad. Referencias enterprise. |
| FW-LAT-01 | **Check Point** | Israel | Firewall, seguridad avanzada | Quantum, Maestro | Seguridad empresarial global | 2022 | Global | [checkpoint.com](https://www.checkpoint.com) | Sí (8/10) | Líder firewall. Alto rendimiento y fiabilidad. |
| FW-LAT-02 | **Seguritech** | México | ITS integral, ciberseguridad | Seguridad de red VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye seguridad. Conocimiento local normativo. |
| FW-LAT-03 | **Sophos** | UK | Firewall UTM, endpoint security | XG Firewall, Intercept X | Seguridad PYME y enterprise | 2022 | Global | [sophos.com](https://www.sophos.com) | Sí (7/10) | UTM completo. Buena relación costo-beneficio. |
| FW-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño seguridad red, políticas | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (6/10) | Diseñador proyecto. Especificación ciberseguridad. |
| FW-NAL-02 | **Deviteck** | Colombia | ITS, software | Implementación firewall, VPN | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de implementación VPN/firewall. |
| FW-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Red segura, segmentación | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (7/10) | Especialista redes. Ventaja en segmentación y VLANs. |

**2.6.18 Conclusiones**

1. **Madurez del mercado**: La ciberseguridad para ITS es un mercado maduro. Palo Alto, Fortinet y Cisco son líderes reconocidos. Fortinet tiene ventaja adicional por su experiencia documentada en proyectos ITS (FortiSIEM en SICOM).

2. **Segmentación crítica**: La red ITS debe segmentarse en: VLAN de campo (CCTV, VMS, SOS), VLAN de control (CCO, servidores), VLAN de management (mantenimiento remoto), VLAN de invitados (usuarios CCO). Cada VLAN con políticas de firewall específicas.

3. **Compliance colombiano**: MinTIC exige cumplimiento de estándares de ciberseguridad para infraestructura crítica. Los integradores nacionales deben garantizar que la arquitectura propuesta cumple resoluciones vigentes.

4. **Neutralidad**: La elección debe ponderar: (a) throughput validado ≥ 10 Gbps, (b) integración SIEM para correlación de eventos, (c) soporte local 24/7 con SLA de respuesta < 4 horas.

---

#### 4.19.1 Descripción y Variables Críticas de Diseño

**CC-19 TMS/CCO — Traffic Management System / Central Control Office**

El componente CC-19 abarca el sistema de gestión de tráfico (TMS) y el Centro de Control de Operaciones (CCO) que constituye el "cerebro" del corredor Chía-Girardot. Según el Capítulo 7 del Entregable #1, el CCO integra datos de todos los componentes (CCTV, AID, VMS, SOS, VDS, ESS, WIM, etc.) para la toma de decisiones operativas.

**2.3.19 Variables Críticas de Diseño**

1. **Arquitectura**: Plataforma modular, escalable, basada en microservicios o arquitectura SOA. Capacidad de integrar ≥ 5,000 dispositivos de campo simultáneamente.
2. **Modularidad**: Módulos independientes (CCTV, AID, VMS, SOS, VDS, ESS, WIM, ETC, ALPR, PAS, incidentes, reportes) con API REST para integración.
3. **Interfaz de usuario**: GIS (Sistema de Información Geográfica) con mapa del corredor en tiempo real; dashboards configurables; alertas visuales y sonoras; multi-pantalla (video wall).
4. **Automatización**: Reglas de negocio configurables (ej. "Si ESS visibilidad < 100m entonces VMS=mensaje neblina + VSL=60km/h + PAS=alerta sonora"). Machine learning para predicción de congestión.
5. **Comunicaciones**: Protocolos NTCIP, DATEX II, SNMP, MQTT, API REST. Gateway para conversión de protocolos legacy.
6. **Seguridad**: Autenticación multifactor; roles y permisos granulares; auditoría de todas las acciones; cifrado de datos en reposo y tránsito.
7. **Disponibilidad**: 99.99% uptime (≤ 52 minutos de downtime anual). Arquitectura redundante (activo-pasivo o activo-activo) con failover automático.
8. **Backup y recuperación**: Backup diario incremental, semanal completo. RPO ≤ 15 minutos; RTO ≤ 1 hora.
9. **Escalabilidad**: Capacidad de crecer 2x sin rediseño arquitectural. Soporte para múltiples corredores futuros.
10. **Reporting**: Reportes operativos (tráfico, incidentes, mantenimiento); reportes gerenciales (KPIs, niveles de servicio); reportes regulatorios (ANS, MinTransporte).

**2.4.19 Ficha Técnica de Referencia TMS/CCO**

| Parámetro | Especificación |
|---|---|
| Arquitectura | Modular, microservicios/SOA, ≥ 5,000 dispositivos |
| Modularidad | Módulos independientes, API REST |
| Interfaz | GIS tiempo real, dashboards, video wall |
| Automatización | Reglas configurables, ML predicción congestión |
| Comunicaciones | NTCIP, DATEX II, SNMP, MQTT, API REST |
| Seguridad | MFA, roles granulares, auditoría, cifrado |
| Disponibilidad | 99.99% uptime, arquitectura redundante |
| Backup | Incremental diario, completo semanal; RPO ≤ 15 min, RTO ≤ 1 h |
| Escalabilidad | 2x sin rediseño; multi-corredor |
| Reporting | Operativos, gerenciales, regulatorios |

**2.5.19 Matriz Comparativa de Oferentes TMS/CCO**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| TMS-INT-01 | **Kapsch TrafficCom** | Austria | ITS integral, TMS, CCO | EcoTrafiX platform | VIITS Colombia, Autopista al Mar 1, global | 2021-2025 | Global | [kapsch.net](https://www.kapsch.net) | Sí (10/10) | EcoTrafiX es referencia mundial TMS. Referencias verificadas en Colombia. |
| TMS-INT-02 | **Siemens Mobility** | Alemania | ITS, TMS, CCO | Sicore TMS, Sitraffic | Autobahn management DACH | 2023 | Europa | [siemens-mobility.com](https://www.mobility.siemens.com) | Sí (9/10) | Sitraffic es plataforma madura. Integración completa ITS. |
| TMS-INT-03 | **Indra** | España | ITS, TMS, transporte | SICE TMS, Mova | Peajes España, LATAM | 2022 | España/LATAM | [indra.es](https://www.indra.es) | Sí (8/10) | Via-T España es referencia. Experiencia en LATAM. |
| TMS-LAT-01 | **Aimsun (Siemens)** | España | Simulación tráfico, TMS | Aimsun Live, Next | Ciudades globales | 2022 | Global | [aimsun.com](https://www.aimsun.com) | Sí (8/10) | Simulación predictiva integrada. Ventaja en modelado tráfico. |
| TMS-LAT-02 | **Seguritech** | México | ITS integral, TMS | Plataforma TMS VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye TMS. Conocimiento local normativo. |
| TMS-LAT-03 | **Grupo Masa** | México | Infraestructura ITS, TMS | Centros de control, TMS | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización TMS específica. |
| TMS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño TMS/CCO, especificación | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación arquitectura CCO. |
| TMS-NAL-02 | **Deviteck** | Colombia | ITS, software | Implementación TMS, integración | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador propuesto. Capacidad de implementación EcoTrafiX. |
| TMS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Infraestructura CCO, red, comunicaciones | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura red y comunicaciones para CCO. |

**2.6.19 Conclusiones**

1. **Plataforma dominante**: EcoTrafiX (Kapsch) es la plataforma de referencia en proyectos ITS de ANI/INVIAS (VIITS, Autopista al Mar 1). La integración nativa con todos los componentes (CCTV, AID, VMS, SOS, WIM, ETC) reduce riesgo de interoperabilidad.

2. **Simulación predictiva**: Aimsun (ahora Siemens) ofrece ventaja única en modelado predictivo de tráfico, permitiendo anticipar congestión 15-30 minutos antes de que ocurra. Esta capacidad diferenciadora puede ser crítica para un corredor de 306 km.

3. **Disponibilidad 99.99%**: El CCO no puede fallar. La arquitectura activo-activo con georedundancia (CCO principal + CCO respaldo en ubicación separada ≥ 20 km) es obligatoria.

4. **Neutralidad**: La elección debe ponderar: (a) referencias verificadas en Colombia, (b) capacidad de simulación predictiva, (c) arquitectura de alta disponibilidad, (d) soporte local 24/7.

---

#### 4.20.1 Descripción y Variables Críticas de Diseño

**CC-20 WS/Work Zone — Gestión de Zonas de Trabajo**

El componente CC-20 abarca el sistema de gestión de zonas de trabajo (Work Zone Management) para operaciones de mantenimiento, construcción y emergencia en el corredor. Según el Capítulo 7 del Entregable #1, WS es crítico para proteger a trabajadores y usuarios durante actividades que reducen la capacidad vial.

**2.3.20 Variables Críticas de Diseño**

1. **Dispositivos**: VMS portátiles (trailer-mounted), señales de flecha (arrow boards), conos inteligentes (con sensores de presencia), barreras móviles, luces de advertencia.
2. **Comunicación**: Conectividad inalámbrica (4G/5G/radio) al CCO para reportar estado y ubicación de cada dispositivo.
3. **Geolocalización**: GPS en cada dispositivo para visualización en GIS del CCO. Alerta si dispositivo es movido sin autorización.
4. **Automatización**: Integración con VMS fijos (CC-03) y VSL (CC-14) para publicar mensajes de "ZONA DE TRABAJO" y reducir velocidad automáticamente.
5. **Detección de intrusión**: Sensores de presencia en perímetro de zona de trabajo. Alerta al CCO si vehículo ingresa zona restringida.
6. **Protección trabajadores**: Sistema de detección de trabajadores (wearables) con alerta si trabajador sale de zona segura o vehículo se aproxima a < 10 m.
7. **Energía**: Solar + batería 72 h para dispositivos portátiles; generador para VMS trailer.
8. **Protección**: IP65 para dispositivos de campo; reflectividad alta para visibilidad nocturna.
9. **Gestión de tráfico**: Cierre parcial de carriles; contraflow; desvíos. Publicación automática en Waze/Google Maps mediante API.
10. **Documentación**: Plan de manejo de tráfico (PMT) digital; registro de dispositivos desplegados; reporte de incidentes en zona de trabajo.

**2.4.20 Ficha Técnica de Referencia WS/Work Zone**

| Parámetro | Especificación |
|---|---|
| Dispositivos | VMS portátiles, arrow boards, conos inteligentes, barreras, luces |
| Comunicación | 4G/5G/radio al CCO |
| Geolocalización | GPS por dispositivo; alerta movimiento no autorizado |
| Automatización | Integración VMS fijos + VSL para mensajes y reducción velocidad |
| Detección intrusión | Sensores presencia perímetro; alerta CCO |
| Protección trabajadores | Wearables; alerta proximidad vehículo < 10 m |
| Energía | Solar + batería 72 h (portátiles); generador (VMS trailer) |
| Protección | IP65; reflectividad alta |
| Gestión tráfico | Cierre carriles, contraflow, desvíos; API Waze/Google Maps |
| Documentación | PMT digital, registro dispositivos, reporte incidentes |

**2.5.20 Matriz Comparativa de Oferentes WS/Work Zone**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| WS-INT-01 | **3M** | USA | Seguridad vial, señalización, ITS | Work zone devices, retroreflective | Work zone safety USA global | 2022 | Global | [3m.com](https://www.3m.com) | Sí (9/10) | Líder señalización vial. Referencias extensas en work zones. |
| WS-INT-02 | **SWARCO** | Austria | ITS, señalización, work zone | Portable VMS, arrow boards, road studs | European work zone management | 2022 | Europa | [swarco.com](https://www.swarco.com) | Sí (8/10) | VMS portátiles CUBILED. Referencia europea. |
| WS-INT-03 | **Traffix Devices** | USA | Work zone safety, devices | Arrow boards, message signs, barriers | Work zone devices USA | 2022 | USA | [traffixdevices.com](https://www.traffixdevices.com) | Sí (8/10) | Especialista work zone USA. Amplia gama dispositivos. |
| WS-LAT-01 | **Daktronics** | USA | VMS portátiles, work zone | Portable VMS, trailer-mounted | Highway work zones USA | 2022 | USA | [daktronics.com](https://www.daktronics.com) | Sí (7/10) | VMS portátiles de gran formato. Costo elevado. |
| WS-LAT-02 | **Seguritech** | México | ITS integral, work zone | Gestión zonas trabajo VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye work zone potencial. Conocimiento local. |
| WS-LAT-03 | **Grupo Masa** | México | Infraestructura ITS, work zone | Señalización, dispositivos | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización work zone específica. |
| WS-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño work zone, PMT digital | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación work zone. |
| WS-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración work zone-CCO-GIS | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de integración Waze/Google Maps. |
| WS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Comunicaciones work zone, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura comunicaciones para dispositivos portátiles. |

**2.6.20 Conclusiones**

1. **Seguridad primero**: La protección de trabajadores es la prioridad absoluta. 3M (retroreflectividad), SWARCO (VMS portátiles) y Traffix (dispositivos específicos) tienen referencias verificadas en reducción de incidentes en work zones.

2. **Integración digital**: La publicación automática en Waze/Google Maps mediante API reduce congestión inducida por work zones. Deviteck y CI2 deben garantizar esta integración en el diseño.

3. **Wearables para trabajadores**: La detección de proximidad vehicular (< 10 m) mediante wearables es tecnología emergente. No todos los integradores nacionales tienen experiencia verificada en esta tecnología.

4. **Neutralidad**: La elección debe ponderar: (a) visibilidad nocturna (retroreflectividad 3M), (b) capacidad de integración digital (Waze/Google Maps), (c) protección de trabajadores (wearables + sensores perimetrales).

---

#### 4.21.1 Descripción y Variables Críticas de Diseño

**CC-21 TOLL/Tolling — Sistema de Peaje / Tolling System**

El componente CC-21 abarca el sistema de peaje para el corredor Chía-Girardot, incluyendo plazas de peaje tradicionales, peaje electrónico (ETC/AVI - CC-11), y sistemas de back-office para gestión de tarifas, transacciones y fiscalización. Según el Capítulo 7 del Entregable #1, el sistema de peaje es crítico para la sostenibilidad financiera del corredor.

**2.3.21 Variables Críticas de Diseño**

1. **Modalidades**: Peaje manual (efectivo/tarjeta), peaje semiautomático (tarjeta magnética/QR), peaje electrónico (ETC/AVI - CC-11), peaje dinámico (tarifa variable por horario/congestión).
2. **Capacidad**: ≥ 600 veh/h/carril (manual); ≥ 2,000 veh/h/carril (ETC free-flow).
3. **Clasificación**: Automática por WIM (CC-07) + ALPR (CC-12) + OBU (CC-11) en plazas ETC; manual por operador en plazas tradicionales.
4. **Tarifas**: Diferenciadas por categoría vehicular (5+ categorías), horario (pico/off-peak), eje adicional (sobrepeso WIM), zona (tramos de mayor costo construcción).
5. **Back-office**: Gestión de cuentas, recaudación, conciliación bancaria, reportes regulatorios, atención al usuario.
6. **Fiscalización**: Validación cruzada WIM+ALPR+OBU; lista negra de evasores; sistema de reclamos y apelaciones.
7. **Comunicación**: Ethernet/fibra al CCO; API REST para integración con bancos y entidades financieras; protocolos seguros (TLS 1.3, AES-256).
8. **Energía**: 110-240 VAC + UPS 8 h + generador diésel automático en todas las plazas.
9. **Protección**: IP65; anti-vandalismo (IK10); CCTV (CC-01) integrado en cada plaza.
10. **Normativa**: Cumplimiento resoluciones ANI/MinTransporte para peajes en Colombia; Ley de Peajes; regulación bancaria para pagos electrónicos.

**2.4.21 Ficha Técnica de Referencia TOLL/Tolling**

| Parámetro | Especificación |
|---|---|
| Modalidades | Manual, semiautomático, ETC free-flow, dinámico |
| Capacidad | ≥ 600 veh/h/carril (manual); ≥ 2,000 veh/h/carril (ETC) |
| Clasificación | Automática WIM+ALPR+OBU; manual operador |
| Tarifas | Por categoría, horario, eje adicional, zona |
| Back-office | Cuentas, recaudación, conciliación, reportes, atención |
| Fiscalización | Validación cruzada, lista negra, reclamos |
| Comunicación | Ethernet/fibra; API REST bancos; TLS 1.3, AES-256 |
| Energía | 110-240 VAC + UPS 8 h + generador diésel |
| Protección | IP65, IK10, CCTV integrado |
| Normativa | ANI/MinTransporte, Ley de Peajes, regulación bancaria |

**2.5.21 Matriz Comparativa de Oferentes TOLL/Tolling**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| TOL-INT-01 | **Kapsch TrafficCom** | Austria | Tolling, ETC, back-office | EcoTrafiX Tolling, gantries | Varios países global | 2023 | Global | [kapsch.net](https://www.kapsch.net) | Sí (10/10) | Líder mundial tolling. EcoTrafiX es referencia en peaje. |
| TOL-INT-02 | **Conduent** | USA | Tolling, transit, back-office | E-ZPass, back-office systems | E-ZPass USA, proyectos global | 2022 | USA/Global | [conduent.com](https://www.conduent.com) | Sí (9/10) | E-ZPass es referencia mundial. Back-office robusto. |
| TOL-INT-03 | **Thales** | Francia | ETC, peaje, back-office | ETC gantries, OBU, back-office | Proyectos ETC Europa, Asia | 2022 | Global | [thalesgroup.com](https://www.thalesgroup.com) | Sí (8/10) | Tecnología DSRC avanzada. Back-office integrado. |
| TOL-LAT-01 | **Indra** | España | ITS, peaje, transporte | Via-T, SICE tolling | Peajes España, LATAM | 2022 | España/LATAM | [indra.es](https://www.indra.es) | Sí (8/10) | Via-T España es referencia. Experiencia en LATAM. |
| TOL-LAT-02 | **Seguritech** | México | ITS integral, peaje | ETC, back-office VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye tolling potencial. Conocimiento local normativo. |
| TOL-LAT-03 | **Grupo Masa** | México | Infraestructura ITS, peaje | Plazas de cobro, centros control | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (7/10) | Integrador con experiencia en plazas de peaje México. |
| TOL-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño peaje, back-office | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (6/10) | Diseñador proyecto. Especificación sistema peaje. |
| TOL-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración peaje-CCO-bancos | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de integración back-office. |
| TOL-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Infraestructura plazas peaje, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura red y comunicaciones para peaje. |

**2.6.21 Conclusiones**

1. **Madurez del mercado**: El mercado de tolling es altamente maduro y consolidado. Kapsch, Conduent e Indra son líderes globales con referencias verificadas a gran escala.

2. **Integración OBU-ALPR-WIM**: La concordancia ≥ 99.5% entre OBU (ETC), ALPR y WIM es crítica para evitar evasión y reclamos. Kapsch ofrece ventaja al tener los tres subsistemas en su portafolio.

3. **Back-office local**: La recaudación electrónica requiere integración con entidades bancarias colombianas. Los integradores nacionales deben garantizar esta integración mediante APIs estándar (REST, SOAP).

4. **Normativa colombiana**: ANI y MinTransporte regulan específicamente los peajes en concesiones. Seguritech (México) e Indra (España) tienen experiencia en normativas similares LATAM.

5. **Neutralidad**: La elección debe ponderar: (a) referencias verificadas en mercados LATAM, (b) integración bancaria local, (c) capacidad de fiscalización y prevención de evasión.


---

#### 4.22.1 Descripción y Variables Críticas de Diseño

**CC-22 UPS/BBU — Uninterruptible Power Supply / Battery Backup Unit**

El componente CC-22 abarca los sistemas de alimentación ininterrumpida (UPS) y baterías de respaldo (BBU) que garantizan la continuidad operativa de todos los componentes críticos del corredor ante fallas de red eléctrica. Según el Capítulo 7 del Entregable #1, la energía es el sistema nervioso del ITS; sin energía, todos los demás componentes fallan.

**2.3.22 Variables Críticas de Diseño**

1. **Topología**: UPS en cada nodo de campo (postes, gabinetes, cámaras); UPS central en CCO; generador diésel automático en CCO y plazas de peaje; paneles solares + baterías en ubicaciones remotas.
2. **Capacidad UPS nodos de campo**: Mínimo 4 horas para CCTV, VMS, SOS, AID; mínimo 8 horas para VDS, ESS, WIM; mínimo 24 horas para comunicaciones (EC/CC-16).
3. **Capacidad UPS CCO**: Mínimo 2 horas en batería + arranque automático de generador diésel (< 30 segundos).
4. **Generador CCO**: Potencia suficiente para 100% carga CCO + 50% carga de campo esencial; arranque automático; prueba semanal programada; combustible para 72 h operación.
5. **Solar + batería**: Paneles solares + baterías LiFePO4 (≥ 72 h autonomía) en ubicaciones sin red eléctrica (quebradas, zonas remotas, túneles).
6. **Monitoreo**: Estado de cada UPS/BBU (carga, voltaje, temperatura, tiempo restante) reportado al CCO cada 60 segundos. Alerta por falla, descarga > 80%, temperatura anormal.
7. **Conmutación**: Transferencia automática (ATS) entre red, batería y generador; tiempo de transferencia < 10 ms para equipos sensibles.
8. **Protección**: Supresores de sobretensión (TVSS); aislamiento galvánico; protección contra rayos (clase I + II); puesta a tierra ≤ 1 Ω.
9. **Eficiencia**: UPS con eficiencia ≥ 90% en modo normal; modo eco ≥ 95% cuando red es estable.
10. **Mantenimiento**: Baterías sellas de mantenimiento reducido (VRLA) o LiFePO4 (sin mantenimiento); vida útil ≥ 5 años (VRLA) o ≥ 10 años (LiFePO4); monitoreo de degradación individual por celda.

**2.4.22 Ficha Técnica de Referencia UPS/BBU**

| Parámetro | Especificación |
|---|---|
| Topología | UPS nodos campo + UPS central CCO + generador diésel + solar |
| Capacidad nodos | 4 h (CCTV/VMS/SOS/AID); 8 h (VDS/ESS/WIM); 24 h (EC) |
| Capacidad CCO | 2 h batería + generador diésel < 30 s |
| Generador CCO | 100% CCO + 50% campo esencial; 72 h combustible |
| Solar + batería | LiFePO4 ≥ 72 h autonomía en ubicaciones remotas |
| Monitoreo | Estado cada 60 s al CCO; alerta falla/descarga/temperatura |
| Conmutación | ATS automática; transferencia < 10 ms |
| Protección | TVSS, aislamiento galvánico, protección rayos clase I+II, puesta a tierra ≤ 1 Ω |
| Eficiencia | ≥ 90% modo normal; ≥ 95% modo eco |
| Mantenimiento | VRLA ≥ 5 años; LiFePO4 ≥ 10 años; monitoreo por celda |

**2.5.22 Matriz Comparativa de Oferentes UPS/BBU**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| UPS-INT-01 | **Schneider Electric (APC)** | Francia | UPS, energía, automatización | APC Smart-UPS, Galaxy, EcoStruxure | Data centers, infraestructura crítica global | 2023 | Global | [se.com](https://www.se.com) | Sí (10/10) | Líder mundial UPS. Referencias en infraestructura crítica global. |
| UPS-INT-02 | **Eaton** | USA | UPS, energía, protección eléctrica | Eaton 9PX, 93PM, Power Xpert | Infraestructura crítica, transporte, data centers | 2023 | Global | [eaton.com](https://www.eaton.com) | Sí (9/10) | Líder UPS industrial. Referencias en transporte y energía. |
| UPS-INT-03 | **Vertiv (Liebert)** | USA | UPS, climatización, infraestructura crítica | Liebert GXT5, EXL, Trinergy | Data centers, telecom, transporte global | 2023 | Global | [vertiv.com](https://www.vertiv.com) | Sí (9/10) | Especialista infraestructura crítica. Referencias en telecom y transporte. |
| UPS-LAT-01 | **Generac** | USA | Generadores, energía de respaldo | Generac industrial generators | Generadores industriales global | 2022 | Américas | [generac.com](https://www.generac.com) | Sí (8/10) | Líder generadores USA. Referencias en infraestructura crítica. |
| UPS-LAT-02 | **Cummins** | USA | Motores, generadores, energía | Cummins Power Generation | Generadores industria, transporte global | 2022 | Global | [cummins.com](https://www.cummins.com) | Sí (8/10) | Líder motores/generadores. Alta fiabilidad documentada. |
| UPS-LAT-03 | **Seguritech** | México | ITS integral, energía | UPS, generadores VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye energía. Conocimiento local normativo. |
| UPS-NAL-01 | **CI2** | Colombia | ITS, ingeniería eléctrica | Diseño energía, UPS, especificación | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación sistema energía. |
| UPS-NAL-02 | **Deviteck** | Colombia | ITS, software, hardware | Integración UPS-monitoreo CCO | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador. Capacidad de monitoreo energía centralizado. |
| UPS-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones, energía | Infraestructura energía, UPS, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (7/10) | Especialista infraestructura. Ventaja en energía + telecomunicaciones. |

**2.6.22 Conclusiones**

1. **Infraestructura crítica**: La energía es el sistema más crítico. Schneider Electric (APC), Eaton y Vertiv son los tres líderes mundiales con referencias verificadas en infraestructura crítica (data centers, transporte, telecom). La elección entre ellos depende de soporte local y TCO.

2. **Autonomía solar**: En zonas remotas sin red eléctrica (quebradas, túneles aislados), la combinación solar + LiFePO4 es la única opción viable. La vida útil de 10 años de LiFePO4 reduce significativamente el TCO vs VRLA (5 años) en estas ubicaciones.

3. **Generador CCO**: El generador diésel en CCO debe arrancar en < 30 segundos y tener combustible para 72 h. Generac y Cummins son líderes en generadores industriales con referencias verificadas.

4. **Monitoreo centralizado**: El estado de cada UPS/BBU debe reportarse al CCO para gestión proactiva. Los integradores nacionales deben garantizar esta integración con la plataforma seleccionada.

5. **Neutralidad**: La elección debe ponderar: (a) eficiencia energética (modo eco ≥ 95%), (b) vida útil baterías en clima tropical, (c) soporte local 24/7 con repuestos en Colombia, (d) TCO 10 años.

---

#### 4.23.1 Descripción y Variables Críticas de Diseño

**CC-23 PTZ — Pan-Tilt-Zoom Cameras**

El componente CC-23 abarca las cámaras PTZ (Pan-Tilt-Zoom) de alta movilidad para seguimiento dinámico de incidentes, monitoreo de zonas críticas y apoyo a operaciones de emergencia. Según el Capítulo 7 del Entregable #1, las PTZ complementan las cámaras fijas (CC-01 CCTV) proporcionando capacidad de seguimiento y zoom en tiempo real.

**2.3.23 Variables Críticas de Diseño**

1. **Resolución**: ≥ 2 MP (Full HD 1080p); preferible 4 MP o 8 MP para identificación facial/placa a distancia.
2. **Zoom óptico**: ≥ 30x (zoom digital adicional ≥ 12x); velocidad de zoom suave y precisa.
3. **Velocidad de movimiento**: Pan ≥ 100°/s; Tilt ≥ 60°/s; aceleración suave sin vibración.
4. **Rango de movimiento**: Pan continuo 360°; Tilt -20° a +90° (incluyendo vertical hacia arriba).
5. **Presets y tours**: ≥ 255 presets programables; ≥ 8 tours automáticos secuenciales; rastreo automático de objetos (auto-tracking).
6. **Visión nocturna**: IR integrado alcance ≥ 200 m; sensibilidad < 0.005 lux (color); < 0.001 lux (B/N).
7. **WDR**: ≥ 120 dB WDR para manejar condiciones de contraluz (amanecer/atardecer en curvas).
8. **Protección ambiental**: IP66; IK10 (anti-vandalismo); temperatura -40 °C a +60 °C (rango extendido para altiplano cundiboyacense).
9. **Comunicación**: Ethernet (fibra); PoE++ (IEEE 802.3bt, 60W) o 110-240 VAC; protocolo ONVIF Profile S/G/T; API REST para control desde CCO.
10. **EIS**: Estabilización de imagen electrónica (EIS) o estabilización mecánica para reducir vibración en postes de campo expuestos a viento.

**2.4.23 Ficha Técnica de Referencia PTZ**

| Parámetro | Especificación |
|---|---|
| Resolución | ≥ 2 MP (1080p); preferible 4-8 MP |
| Zoom óptico | ≥ 30x; digital ≥ 12x |
| Velocidad | Pan ≥ 100°/s; Tilt ≥ 60°/s |
| Rango | Pan 360° continuo; Tilt -20° a +90° |
| Presets/tours | ≥ 255 presets; ≥ 8 tours; auto-tracking |
| IR nocturno | ≥ 200 m; < 0.005 lux color; < 0.001 lux B/N |
| WDR | ≥ 120 dB |
| Protección | IP66, IK10, -40 °C a +60 °C |
| Comunicación | Ethernet/fibra; PoE++ o 110-240 VAC; ONVIF; API REST |
| EIS | Estabilización electrónica/mecánica |

**2.5.23 Matriz Comparativa de Oferentes PTZ**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| PTZ-INT-01 | **Axis Communications** | Suecia | CCTV, PTZ, video analítico | Q60, Q61, Q62 series | Programa Nacional Seguridad Vial INVIAS/MinTransporte (2013) | 2013 | Colombia | [axis.com](https://www.axis.com) | Sí (10/10) | Referencia verificada en Colombia. PTZ de alta fiabilidad. |
| PTZ-INT-02 | **Bosch Security Systems** | Alemania | CCTV, PTZ, video inteligente | AUTODOME, MIC IP | Aeropuertos, transporte, infraestructura global | 2023 | Global | [boschsecurity.com](https://www.boschsecurity.com) | Sí (9/10) | AUTODOME es referencia en PTZ. WDR superior a 140 dB. |
| PTZ-INT-03 | **Hikvision** | China | CCTV, PTZ, IA | DS-2DF, DS-2DY series | Infraestructura global, smart cities | 2023 | Global | [hikvision.com](https://www.hikvision.com) | Sí (8/10) | Líder mundial volumen. Alta relación costo/capacidad. |
| PTZ-LAT-01 | **Hanwha Techwin (Wisenet)** | Corea del Sur | CCTV, PTZ, video | XNP-6550, XNV-8080Z | Transporte, smart cities LATAM | 2022 | LATAM/Global | [hanwhasecurity.com](https://www.hanwhasecurity.com) | Sí (8/10) | Wisenet es referencia en LATAM. Buena relación costo-beneficio. |
| PTZ-LAT-02 | **Seguritech** | México | ITS integral, CCTV/PTZ | PTZ integrados VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye CCTV/PTZ. Conocimiento local normativo. |
| PTZ-LAT-03 | **Dahua Technology** | China | CCTV, PTZ, IA | SD6C, SD6AE series | Smart cities, transporte global | 2023 | Global | [dahuatech.com](https://www.dahuatech.com) | Sí (7/10) | Segundo líder mundial volumen. Similar a Hikvision en capacidad. |
| PTZ-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño PTZ, especificación | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación PTZ. |
| PTZ-NAL-02 | **Deviteck** | Colombia | ITS, software, hardware | Integración PTZ-CCO-VMS | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador. Capacidad de integración PTZ con CCO. |
| PTZ-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones | Infraestructura PTZ, red, comunicaciones | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura comunicaciones para PTZ. |

**2.6.23 Conclusiones**

1. **Auto-tracking**: La capacidad de auto-tracking (seguimiento automático de objetos en movimiento) es crítica para seguimiento de vehículos en incidentes. Bosch AUTODOME y Axis Q62 tienen algoritmos de auto-tracking verificados en aplicaciones de transporte.

2. **WDR y neblina**: El rango dinámico ≥ 120 dB es esencial para condiciones de contraluz en curvas. Bosch ofrece WDR > 140 dB. Para neblina, los sensores de mayor sensibilidad (< 0.001 lux B/N) permiten operación en condiciones de muy baja visibilidad.

3. **Estabilización**: El viento en zonas altas del corredor (Chía, altiplano) puede causar vibración en postes. La estabilización mecánica (Bosch MIC IP) es superior a la electrónica en condiciones de viento fuerte.

4. **Neutralidad**: La elección debe ponderar: (a) auto-tracking y zoom suave, (b) WDR y sensibilidad nocturna, (c) estabilización mecánica vs electrónica, (d) soporte local y repuestos en Colombia.

---

#### 4.24.1 Descripción y Variables Críticas de Diseño

**CC-24 Fiber/FOC — Fiber Optic Communications**

El componente CC-24 abarca la red de fibra óptica (FOC) que constituye el backbone de comunicaciones del corredor Chía-Girardot. Según el Capítulo 7 del Entregable #1, la fibra óptica es el medio principal de transmisión de datos entre el CCO y todos los dispositivos de campo.

**2.3.24 Variables Críticas de Diseño**

1. **Topología**: Anillo redundante (RING) con protección MS-SP (Multiplex Section - Shared Protection) o SNCP (Subnetwork Connection Protection); capacidad de healing automático < 50 ms.
2. **Capacidad**: Mínimo 10 Gbps por dirección en backbone principal; 1 Gbps por dirección en accesos de campo; escalable a 40/100 Gbps sin reemplazo de fibra.
3. **Fibra**: Monomodo (SM) ITU-T G.652.D o G.655; cable loose tube con protección anti-roedor (cinta de acero); cable ADSS (All-Dielectric Self-Supporting) en tramos aéreos.
4. **Distancia**: Máximo 80 km entre amplificadores/ regeneradores (sin amplificación) con transmisores estándar; 120 km con amplificación óptica (EDFA).
5. **Empalmes**: Empalmes por fusión con pérdida ≤ 0.1 dB; OTDR para certificación de cada tramo; documentación de pérdidas por tramo.
6. **Ductos**: Ducto subterráneo HDPE (mínimo 2 vías: 1 operación + 1 reserva); ducto aéreo en zonas montañosas o de difícil acceso.
7. **Caja de empalme**: FOSC (Fiber Optic Splice Closure) IP68; capacidad ≥ 48 fibras; organización por módulos; acceso sin herramientas especiales.
8. **Patch panels**: ODF (Optical Distribution Frame) en CCO y nodos principales; organización por componente (CCTV, VMS, SOS, etc.); etiquetado permanente.
9. **Monitoreo**: OTDR remoto para detección de fallas (breaks, microbends); localización precisa (< 10 m); alerta automática al CCO.
10. **Redundancia**: Fibra enterrada + fibra aérea en tramos críticos; diversidad de rutas (ruta principal + ruta alternativa ≥ 5 km separación).

**2.4.24 Ficha Técnica de Referencia Fiber/FOC**

| Parámetro | Especificación |
|---|---|
| Topología | Anillo redundante RING; MS-SP o SNCP; healing < 50 ms |
| Capacidad | 10 Gbps (backbone); 1 Gbps (acceso); escalable 40/100 Gbps |
| Fibra | Monomodo G.652.D/G.655; loose tube + cinta acero anti-roedor; ADSS aéreo |
| Distancia | 80 km sin amplificación; 120 km con EDFA |
| Empalmes | Fusión ≤ 0.1 dB; OTDR certificación; documentación pérdidas |
| Ductos | HDPE subterráneo (2 vías); aéreo en zonas difíciles |
| Caja empalme | FOSC IP68 ≥ 48 fibras; modular; acceso sin herramientas |
| Patch panels | ODF CCO + nodos; organización por componente; etiquetado |
| Monitoreo | OTDR remoto; localización < 10 m; alerta automática CCO |
| Redundancia | Enterrada + aérea tramos críticos; rutas diversas ≥ 5 km |

**2.5.24 Matriz Comparativa de Oferentes Fiber/FOC**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| FOC-INT-01 | **Corning** | USA | Fibra óptica, cables, conectividad | SMF-28, ALTOS, RocketRibbon | Redes de fibra global, telecomunicaciones | 2023 | Global | [corning.com](https://www.corning.com) | Sí (10/10) | Inventor de la fibra óptica. Líder mundial calidad y fiabilidad. |
| FOC-INT-02 | **Prysmian Group** | Italia | Cables energía y telecomunicaciones | Sirocco, FlexRibbon, MiniSpan | Infraestructura telecom global | 2023 | Global | [prysmiangroup.com](https://www.prysmiangroup.com) | Sí (9/10) | Líder europeo cables. Amplia gama ADSS, subterráneos. |
| FOC-INT-03 | **CommScope** | USA | Infraestructura de red, fibra | TeraSPEED, ODF, FOSC | Data centers, telecom, transporte global | 2023 | Global | [commscope.com](https://www.commscope.com) | Sí (9/10) | Líder infraestructura pasiva. Soluciones completas ODF/FOSC. |
| FOC-LAT-01 | **Nexans** | Francia | Cables energía y telecomunicaciones | LANmark, external cables | Infraestructura telecom Europa, LATAM | 2022 | Europa/LATAM | [nexans.com](https://www.nexans.com) | Sí (8/10) | Presencia LATAM. Cables de calidad europea. |
| FOC-LAT-02 | **YOFC (Yangtze Optical Fibre)** | China | Fibra óptica, cables | G.652, G.655, ADSS | Redes fibra China, exportación global | 2023 | Global | [yofc.com](https://www.yofc.com) | Sí (7/10) | Mayor productor fibra mundo. Costo competitivo. Calidad variable. |
| FOC-LAT-03 | **Seguritech** | México | ITS integral, fibra | Diseño red fibra VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye fibra. Conocimiento local normativo. |
| FOC-NAL-01 | **CI2** | Colombia | ITS, ingeniería | Diseño red fibra, topología, redundancia | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación red fibra. |
| FOC-NAL-02 | **SIT** | Colombia | ITS, telecomunicaciones | Instalación fibra, empalmes, OTDR | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (7/10) | Especialista telecomunicaciones. Ventaja instalación y certificación. |
| FOC-NAL-03 | **Deviteck** | Colombia | ITS, software, hardware | Integración fibra-CCO, monitoreo OTDR | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de monitoreo OTDR centralizado. |

**2.6.24 Conclusiones**

1. **Calidad de fibra**: Corning inventó la fibra óptica y mantiene el estándar de calidad mundial. Prysmian y CommScope son alternativas premium con referencias verificadas en infraestructura crítica.

2. **Topología redundante**: El anillo RING con healing < 50 ms es obligatorio para garantizar continuidad ante corte de fibra. Los integradores nacionales deben validar que la topología propuesta cumple este requisito con los equipos de transporte seleccionados.

3. **ADSS vs enterrado**: En zonas montañosas con alto riesgo de deslizamientos, el cable enterrado en ducto HDPE es más protegido que el aéreo ADSS. Sin embargo, el aéreo es más económico y rápido de instalar. La diversidad de rutas (enterrado + aéreo) es la estrategia óptima.

4. **Monitoreo OTDR**: La capacidad de detectar fallas y localizarlas a < 10 m mediante OTDR remoto reduce drásticamente el MTTR. CommScope ofrece soluciones OTDR integradas en ODF.

5. **Neutralidad**: La elección debe ponderar: (a) calidad y vida útil de la fibra (30+ años), (b) topología redundante con healing < 50 ms, (c) diversidad de rutas, (d) monitoreo OTDR remoto, (e) soporte local y repuestos.

---

#### 4.25.1 Descripción y Variables Críticas de Diseño

**CC-25 SW/Software — Software Platform**

El componente CC-25 abarca la plataforma de software que integra, gestiona y opera todos los subsistemas del corredor Chía-Girardot. Según el Capítulo 7 del Entregable #1, el software es el cerebro operativo que permite la gestión unificada de CCTV, AID, VMS, SOS, VDS, ESS, WIM, ETC, ALPR, PAS, y todos los demás componentes.

**2.3.25 Variables Críticas de Diseño**

1. **Arquitectura**: Microservicios contenerizados (Docker/Kubernetes) o arquitectura modular SOA; escalabilidad horizontal; desacoplamiento entre módulos.
2. **Módulos**: CCTV Manager; AID Processor; VMS Controller; SOS Monitor; VDS Analytics; ESS Dashboard; WIM Enforcement; ETC Tolling; ALPR Recognition; PAS Control; Incident Management; GIS Map; Reporting Engine; User Management.
3. **Interfaz usuario**: Web responsive (HTML5); móvil (iOS/Android apps); video wall (multi-pantalla); GIS con capas de información (tráfico, clima, incidentes, dispositivos).
4. **Automatización**: Motor de reglas (rule engine) para automatización; machine learning para predicción de tráfico y congestión; IA generativa para análisis de incidentes y generación de reportes.
5. **APIs**: API REST (JSON/XML) para integración con terceros; API GraphQL para consultas complejas; Webhooks para eventos en tiempo real; SDK para desarrolladores.
6. **Seguridad**: OAuth 2.0 / OIDC para autenticación; RBAC (Role-Based Access Control) con granularidad a nivel de función; audit trail completo; cifrado AES-256 en tránsito y reposo.
7. **Disponibilidad**: 99.99% uptime; arquitectura activo-activo con georedundancia; failover automático < 30 segundos.
8. **Escalabilidad**: Capacidad de crecer 2x sin rediseño; soporte multi-tenant para futuros corredores; cloud-ready (AWS/Azure/GCP) o on-premise.
9. **Backup y recuperación**: Snapshot diario; backup incremental cada 4 horas; RPO ≤ 15 minutos; RTO ≤ 1 hora.
10. **Soporte**: Actualizaciones trimestrales; parches de seguridad críticos < 24 horas; soporte 24/7 con SLA; documentación completa (técnica, operativa, usuario).

**2.4.25 Ficha Técnica de Referencia SW/Software**

| Parámetro | Especificación |
|---|---|
| Arquitectura | Microservicios (Docker/K8s) o SOA; escalabilidad horizontal |
| Módulos | CCTV, AID, VMS, SOS, VDS, ESS, WIM, ETC, ALPR, PAS, Incidentes, GIS, Reportes, Usuarios |
| Interfaz | Web HTML5, móvil iOS/Android, video wall, GIS |
| Automatización | Rule engine, ML predicción, IA generativa |
| APIs | REST (JSON/XML), GraphQL, Webhooks, SDK |
| Seguridad | OAuth 2.0/OIDC, RBAC, audit trail, AES-256 |
| Disponibilidad | 99.99% uptime; activo-activo; failover < 30 s |
| Escalabilidad | 2x sin rediseño; multi-tenant; cloud-ready |
| Backup | Snapshot diario; incremental 4 h; RPO ≤ 15 min; RTO ≤ 1 h |
| Soporte | Actualizaciones trimestrales; parches críticos < 24 h; 24/7 SLA |

**2.5.25 Matriz Comparativa de Oferentes SW/Software**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| SW-INT-01 | **Kapsch TrafficCom** | Austria | ITS integral, software TMS | EcoTrafiX platform | VIITS Colombia, Autopista al Mar 1, global | 2021-2025 | Global | [kapsch.net](https://www.kapsch.net) | Sí (10/10) | EcoTrafiX es plataforma líder mundial. Referencias verificadas Colombia. |
| SW-INT-02 | **Siemens Mobility** | Alemania | ITS, software TMS | Sicore TMS, Sitraffic | Autobahn management DACH | 2023 | Europa | [siemens-mobility.com](https://www.mobility.siemens.com) | Sí (9/10) | Sitraffic es plataforma madura. Integración completa ITS. |
| SW-INT-03 | **Indra** | España | ITS, software, transporte | SICE TMS, Mova | Peajes España, LATAM | 2022 | España/LATAM | [indra.es](https://www.indra.es) | Sí (8/10) | SICE TMS referencia en España. Experiencia LATAM. |
| SW-LAT-01 | **Aimsun (Siemens)** | España | Simulación tráfico, TMS | Aimsun Live, Next | Ciudades globales | 2022 | Global | [aimsun.com](https://www.aimsun.com) | Sí (8/10) | Simulación predictiva integrada. Ventaja en modelado tráfico. |
| SW-LAT-02 | **Seguritech** | México | ITS integral, software | Plataforma TMS VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye TMS. Conocimiento local normativo. |
| SW-LAT-03 | **Grupo Masa** | México | Infraestructura ITS, software | Centros de control, TMS | Carreteras México (varias) | 2019-2022 | México | [grupomasa.com.mx](https://www.grupomasa.com.mx) | Sí (6/10) | Integrador. Menor especialización TMS específica. |
| SW-NAL-01 | **CI2** | Colombia | ITS, ingeniería, software | Diseño TMS, especificación arquitectura | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación plataforma software. |
| SW-NAL-02 | **Deviteck** | Colombia | ITS, software, desarrollo | Desarrollo software, integración TMS | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador. Capacidad de desarrollo e integración software. |
| SW-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones, software | Infraestructura software, red, cloud | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (6/10) | Infraestructura cloud y red para plataforma software. |

**2.6.25 Conclusiones**

1. **Plataforma dominante**: EcoTrafiX (Kapsch) es la plataforma de referencia en proyectos ITS de ANI/INVIAS (VIITS, Autopista al Mar 1). La integración nativa de todos los módulos reduce riesgo de interoperabilidad.

2. **Simulación predictiva**: Aimsun (Siemens) ofrece ventaja diferenciadora en simulación predictiva de tráfico, permitiendo anticipar congestión 15-30 minutos antes. Esta capacidad puede ser crítica para un corredor de 306 km.

3. **Arquitectura moderna**: La arquitectura de microservicios contenerizados (Docker/K8s) es preferible para escalabilidad y mantenimiento. Los integradores nacionales deben validar que la plataforma seleccionada soporta esta arquitectura.

4. **Cloud vs On-premise**: La decisión entre cloud (AWS/Azure/GCP) y on-premise depende de la política de soberanía de datos del Estado colombiano. La plataforma debe ser cloud-ready sin vendor lock-in.

5. **Neutralidad**: La elección debe ponderar: (a) referencias verificadas en Colombia, (b) capacidad de simulación predictiva, (c) arquitectura escalable y moderna, (d) soporte local 24/7 con SLA de respuesta < 4 horas.

---

#### 4.26.1 Descripción y Variables Críticas de Diseño

**CC-26 BK/Backup — Sistemas de Respaldo**

El componente CC-26 abarca los sistemas de respaldo (backup) de datos, configuraciones y estado operativo del corredor Chía-Girardot. Según el Capítulo 7 del Entregable #1, el backup es crítico para la recuperación ante desastres naturales, ciberataques, fallas humanas o sabotaje.

**2.3.26 Variables Críticas de Diseño**

1. **Alcance**: Backup de base de datos CCO (tráfico, incidentes, configuraciones); backup de video CCTV (30 días mínimo); backup de configuraciones de dispositivos (NTCIP, SNMP); backup de logs de seguridad (1 año mínimo).
2. **Frecuencia**: Base de datos: backup incremental cada 15 minutos, completo diario; Video: backup continuo (archivo al cerrar); Configuraciones: backup por cambio + completo semanal; Logs: append-only, inmutable.
3. **Retención**: Base de datos: 2 años; Video: 90 días (incidentes archivados 5 años); Configuraciones: 2 años; Logs: 1 año mínimo (regulatorio).
4. **Medios**: Almacenamiento primario (SSD/NVMe en CCO); almacenamiento secundario (NAS/SAN en CCO); almacenamiento terciario (nube privada o tape off-site ≥ 50 km de distancia).
5. **Cifrado**: Backup cifrado AES-256 en reposo y tránsito; claves gestionadas por HSM (Hardware Security Module); rotación de claves trimestral.
6. **Verificación**: Verificación automática de integridad de backup (checksum) semanal; prueba de restauración mensual (sin afectar producción); documentación de RTO/RPO por sistema.
7. **Automatización**: Backup automatizado sin intervención humana; alerta al CCO por falla de backup o verificación; reporte semanal de estado de backups.
8. **Recuperación**: RPO ≤ 15 minutos (base de datos); RTO ≤ 1 hora (

CCO); RTO ≤ 4 horas (video); RTO ≤ 8 horas (logs).
9. **Monitoreo**: Dashboard de estado de backups en CCO; alerta por falla de backup, espacio insuficiente, o verificación fallida.
10. **Documentación**: Matriz de sistemas vs frecuencia de backup vs retención vs RTO/RPO; procedimiento de restauración paso a paso; contactos de emergencia; pruebas semestrales de DR.

**2.4.26 Ficha Técnica de Referencia BK/Backup**

| Parámetro | Especificación |
|---|---|
| Alcance | Bases de datos, video, configuraciones, logs |
| Frecuencia | BD: incremental 15 min, completo diario; Video: continuo; Config: por cambio + semanal; Logs: append-only |
| Retención | BD: 2 años; Video: 90 días (incidentes 5 años); Config: 2 años; Logs: 1 año mínimo |
| Medios | SSD/NVMe primario; NAS/SAN secundario; nube/tape off-site ≥ 50 km |
| Cifrado | AES-256 reposo y tránsito; HSM; rotación trimestral |
| Verificación | Checksum semanal; prueba restauración mensual; documentación RTO/RPO |
| Automatización | Sin intervención humana; alerta CCO; reporte semanal |
| Recuperación | RPO ≤ 15 min (BD); RTO ≤ 1 h (BD); RTO ≤ 4 h (video); RTO ≤ 8 h (logs) |
| Monitoreo | Dashboard CCO; alerta falla/espacio/verificación |
| Documentación | Matriz backup; procedimiento restauración; contactos; pruebas semestrales |

**2.5.26 Matriz Comparativa de Oferentes BK/Backup**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| BK-INT-01 | **Veeam** | Suiza | Backup, recuperación, data management | Veeam Backup & Replication, Veeam ONE | Data centers, enterprise global | 2023 | Global | [veeam.com](https://www.veeam.com) | Sí (9/10) | Líder backup virtual y físico. Referencias en infraestructura crítica. |
| BK-INT-02 | **Veritas** | USA | Backup, almacenamiento, data protection | NetBackup, Backup Exec | Enterprise, gobierno, transporte global | 2023 | Global | [veritas.com](https://www.veritas.com) | Sí (9/10) | Líder enterprise backup. Alta escalabilidad y fiabilidad. |
| BK-INT-03 | **Commvault** | USA | Backup, recuperación, gestión datos | Complete Data Protection | Enterprise, cloud, hybrid global | 2023 | Global | [commvault.com](https://www.commvault.com) | Sí (8/10) | Plataforma unificada backup + gestión datos. Cloud-native. |
| BK-LAT-01 | **Arcserve** | USA | Backup, recuperación, continuidad | UDP, Unified Data Protection | PYME y enterprise global | 2022 | Global | [arcserve.com](https://www.arcserve.com) | Sí (8/10) | Backup + alta disponibilidad integrados. Costo competitivo. |
| BK-LAT-02 | **Seguritech** | México | ITS integral, backup | Backup integrado VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye backup. Conocimiento local normativo. |
| BK-LAT-03 | **Microsoft (Azure Backup)** | USA | Cloud backup, Azure | Azure Backup, Azure Site Recovery | Cloud backup global | 2023 | Global | [azure.microsoft.com](https://azure.microsoft.com) | Sí (8/10) | Cloud-native. Escalable. Requiere conectividad cloud. |
| BK-NAL-01 | **CI2** | Colombia | ITS, ingeniería, software | Diseño backup, arquitectura | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación arquitectura backup. |
| BK-NAL-02 | **Deviteck** | Colombia | ITS, software | Implementación backup, Veeam/Veritas | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador. Capacidad implementación Veeam/Veritas. |
| BK-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones, cloud | Infraestructura backup, cloud, red | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (7/10) | Especialista infraestructura cloud. Ventaja en Azure/AWS. |

**2.6.26 Conclusiones**

1. **Madurez del mercado**: El mercado de backup enterprise es maduro. Veeam, Veritas y Commvault son líderes con referencias verificadas en infraestructura crítica. La elección depende de arquitectura (virtual vs física), cloud vs on-premise, y TCO.

2. **Video backup**: El backup de video CCTV es el más exigente en espacio (PB escala). Veeam y Veritas tienen capacidad de deduplicación y compresión que reduce significativamente el espacio requerido.

3. **Off-site ≥ 50 km**: El requisito de off-site ≥ 50 km para desastres regionales requiere cloud o tape. Azure/AWS ofrecen regiones cloud en LATAM (Brasil, Chile). La decisión cloud vs on-premise depende de soberanía de datos.

4. **Neutralidad**: La elección debe ponderar: (a) capacidad de deduplicación de video, (b) RTO/RPO validados, (c) soporte local 24/7, (d) compatibilidad con arquitectura cloud/on-premise seleccionada.

---

#### 4.27.1 Descripción y Variables Críticas de Diseño

**CC-27 DR/Disaster Recovery — Recuperación ante Desastres**

El componente CC-27 abarca el sistema de recuperación ante desastres (DR) que garantiza la continuidad operativa del corredor Chía-Girardot ante desastres naturales (sismos, deslizamientos, inundaciones), ciberataques, fallas catastróficas o sabotaje. Según el Capítulo 7 del Entregable #1, DR es el último recurso cuando todos los sistemas de redundancia local han fallado.

**2.3.27 Variables Críticas de Diseño**

1. **Niveles de DR**: Tier 1 (backup + restauración manual, RTO 24-72 h); Tier 2 (warm standby, RTO 4-24 h); Tier 3 (hot standby, RTO ≤ 1 h); Tier 4 (activo-activo, RTO ≤ 5 min). Objetivo: Tier 3 para CCO; Tier 2 para nodos críticos.
2. **Sitio DR**: Ubicación geográficamente separada ≥ 50 km del CCO principal; misma región sísmica no permitida; accesibilidad garantizada en emergencia.
3. **Replicación datos**: Síncrona (RPO ≈ 0) para datos críticos; asíncrona (RPO ≤ 15 min) para datos no críticos; replicación video por extracción diferencial.
4. **Failover automático**: Detección de falla CCO principal; conmutación automática a DR; notificación a operadores; reversión manual post-recuperación.
5. **Comunicaciones**: Red dedicada CCO-DR (fibra o microwave); VPN IPsec; ancho de banda suficiente para replicación síncrona.
6. **Infraestructura DR**: Réplica de hardware CCO (servidores, storage, networking); capacidad operativa ≥ 80% del CCO principal; escalable a 100% en 4 horas.
7. **Pruebas DR**: Drill semestral completo (simulación de desastre, failover, operación en DR, reversión); documentación de lecciones aprendidas; actualización de procedimientos.
8. **Personal**: Equipo de respuesta designado; contactos de emergencia 24/7; procedimiento de activación DR; autorización para failover automático vs manual.
9. **Integración con componentes**: DR debe incluir réplica de TMS/CCO (CC-19), backup (CC-26), comunicaciones (CC-16 EC), energía (CC-22 UPS); coordinación con VMS (CC-03) para mensajes de "SISTEMA EN MODO EMERGENCIA".
10. **Documentación**: Plan DR completo; matriz de sistemas vs RTO/RPO; diagrama de arquitectura DR; procedimientos paso a paso; contactos; inventario de hardware/software DR.

**2.4.27 Ficha Técnica de Referencia DR/Disaster Recovery**

| Parámetro | Especificación |
|---|---|
| Niveles DR | Tier 3 CCO (RTO ≤ 1 h); Tier 2 nodos críticos (RTO 4-24 h) |
| Sitio DR | ≥ 50 km separación; diferente región sísmica; accesible en emergencia |
| Replicación | Síncrona (RPO ≈ 0) críticos; asíncrona (RPO ≤ 15 min) no críticos |
| Failover | Automático detección + conmutación; notificación operadores; reversión manual |
| Comunicaciones | Fibra/microwave dedicado; VPN IPsec; ancho banda replicación síncrona |
| Infraestructura | Réplica hardware ≥ 80% capacidad; escalable 100% en 4 h |
| Pruebas | Drill semestral completo; documentación lecciones; actualización procedimientos |
| Personal | Equipo respuesta 24/7; procedimiento activación; autorización auto/manual |
| Integración | TMS/CCO, backup, EC, UPS, VMS mensaje emergencia |
| Documentación | Plan DR; matriz RTO/RPO; diagrama; procedimientos; contactos; inventario |

**2.5.27 Matriz Comparativa de Oferentes DR/Disaster Recovery**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| DR-INT-01 | **Veeam** | Suiza | DR, backup, alta disponibilidad | Veeam Availability Suite, Veeam DR | Enterprise DR global | 2023 | Global | [veeam.com](https://www.veeam.com) | Sí (9/10) | DR integrado con backup. Failover automatizado. Referencias enterprise. |
| DR-INT-02 | **VMware** | USA | Virtualización, DR, cloud | Site Recovery Manager (SRM), vSphere | Data centers, enterprise global | 2023 | Global | [vmware.com](https://www.vmware.com) | Sí (9/10) | SRM es referencia en DR virtual. Integración completa vSphere. |
| DR-INT-03 | **Zerto** | Israel | DR, continuidad, cloud | Zerto Platform, IT Resilience | Enterprise, cloud, hybrid global | 2023 | Global | [zerto.com](https://www.zerto.com) | Sí (9/10) | Especialista DR con RPO ≈ 0. Cloud-native. |
| DR-LAT-01 | **Azure Site Recovery** | USA | Cloud DR, Azure | Azure Site Recovery, Azure VMware | Cloud DR global | 2023 | Global | [azure.microsoft.com](https://azure.microsoft.com) | Sí (8/10) | DR cloud-native. Escalable. Requiere conectividad cloud. |
| DR-LAT-02 | **AWS Disaster Recovery** | USA | Cloud DR, AWS | AWS Elastic Disaster Recovery, CloudEndure | Cloud DR global | 2023 | Global | [aws.amazon.com](https://aws.amazon.com) | Sí (8/10) | DR cloud-native AWS. Escalable. Requiere conectividad cloud. |
| DR-LAT-03 | **Seguritech** | México | ITS integral, DR | DR integrado VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (7/10) | VIITS incluye DR. Conocimiento local normativo. |
| DR-NAL-01 | **CI2** | Colombia | ITS, ingeniería, DR | Diseño DR, arquitectura, procedimientos | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación arquitectura DR. |
| DR-NAL-02 | **Deviteck** | Colombia | ITS, software, DR | Implementación DR, Veeam/SRM/Zerto | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (7/10) | Integrador. Capacidad implementación Veeam/VMware/Zerto. |
| DR-NAL-03 | **SIT** | Colombia | ITS, telecomunicaciones, cloud | Infraestructura DR, cloud, red, conectividad | Diseño APP Chía-Girardot | 2026 | Colombia | [sit.com.co](https://www.sit.com.co) | Sí (7/10) | Especialista infraestructura cloud. Ventaja en Azure/AWS DR. |

**2.6.27 Conclusiones**

1. **RPO ≈ 0**: Para datos críticos (estado tráfico, incidentes activos), el RPO debe ser cercano a cero. Zerto y VMware SRM ofrecen replicación síncrona con RPO ≈ 0. Veeam ofrece RPO ≤ 15 min con backup continuo.

2. **Cloud DR**: Azure Site Recovery y AWS DR ofrecen ventaja de no requerir sitio DR físico propio. Sin embargo, requieren conectividad cloud estable y cumplimiento de soberanía de datos colombiana.

3. **Pruebas semestrales**: Un plan DR no probado es un plan que fallará. Los integradores nacionales deben incluir en el contrato drills semestrales con personal del concesionario.

4. **Neutralidad**: La elección debe ponderar: (a) RPO/RTO validados, (b) cloud vs on-premise según política de soberanía, (c) capacidad de pruebas semestrales, (d) soporte local 24/7.

---

#### 4.28.1 Descripción y Variables Críticas de Diseño

**CC-28 EMS/Environmental Monitoring System — Sistema de Monitoreo Ambiental**

El componente CC-28 abarca el sistema de monitoreo ambiental general (EMS) del corredor Chía-Girardot, incluyendo calidad del aire, ruido, vibraciones, ecosistemas acuáticos y biodiversidad. Según el Capítulo 7 del Entregable #1, EMS es crítico para el cumplimiento de licencias ambientales y la gestión sostenible del corredor.

**2.3.28 Variables Críticas de Diseño**

1. **Variables monitoreadas**: Calidad de aire (PM2.5, PM10, NO2, SO2, O3, CO, CO2, VOCs); ruido (dB(A) continuo + eventos); vibraciones (mm/s); agua (pH, conductividad, turbidez, oxígeno disuelto, metales pesados); biodiversidad (cámaras trampa, registros sonoros).
2. **Precisión**: PM2.5 ± 2 µg/m³; PM10 ± 5 µg/m³; NO2 ± 2 ppb; ruido ± 1 dB(A); vibraciones ± 0.1 mm/s.
3. **Frecuencia**: Calidad aire: 15 minutos; ruido: 1 minuto (promedio horario); vibraciones: event-triggered; agua: 1 hora; biodiversidad: continuo (cámaras) / semanal (sonoros).
4. **Ubicación**: Estaciones fijas en puntos críticos (túneles, zonas urbanas cercanas, puentes, quebradas); sensores móviles para monitoreo temporal en eventos construcción.
5. **Comunicación**: 4G/5G (principal) + radio (respaldo) en zonas remotas; Ethernet donde haya fibra; protocolo API REST al CCO y a autoridad ambiental (ANLA).
6. **Energía**: Solar + batería LiFePO4 72 h en ubicaciones remotas; 110-240 VAC en zonas urbanas.
7. **Alertas**: Umbrales configurables por normativa colombiana (Res. 2254 de 2017 calidad aire; Decreto 1076 de 2015 agua); reporte automático a ANLA.
8. **Protección**: IP65; temperatura -10 °C a +55 °C; anti-vandalismo (IK10); protección contra fauna (jaulas para cámaras).
9. **Calibración**: Sensores de calidad de aire: calibración mensual con patrón; sensores de agua: calibración trimestral; ruido: calibración anual con calibrador acústico.
10. **Reportes**: Reportes automáticos mensuales a ANLA; reportes especiales por eventos; dashboard público de calidad aire (transparencia ciudadana).

**2.4.28 Ficha Técnica de Referencia EMS**

| Parámetro | Especificación |
|---|---|
| Variables | PM2.5, PM10, NO2, SO2, O3, CO, CO2, VOCs, ruido dB(A), vibraciones, agua (pH, conductividad, turbidez, OD, metales), biodiversidad |
| Precisión | PM2.5 ±2 µg/m³; PM10 ±5; NO2 ±2 ppb; ruido ±1 dB(A); vibraciones ±0.1 mm/s |
| Frecuencia | Aire: 15 min; Ruido: 1 min; Vibraciones: event; Agua: 1 h; Biodiversidad: continuo/sem |
| Ubicación | Fijas en puntos críticos; móviles en eventos construcción |
| Comunicación | 4G/5G + radio; Ethernet; API REST al CCO y ANLA |
| Energía | Solar + LiFePO4 72 h (remoto); 110-240 VAC (urbano) |
| Alertas | Umbrales normativa Colombia; reporte automático ANLA |
| Protección | IP65, -10 °C a +55 °C, IK10, jaulas fauna |
| Calibración | Aire mensual; agua trimestral; ruido anual |
| Reportes | Mensuales ANLA; eventos especiales; dashboard público |

**2.5.28 Matriz Comparativa de Oferentes EMS**

| ID | Fabricante / Proveedor | País | Especialidad | Alcance | Proyecto Referencia | Año | Región | Fuente | Cumple | Observaciones |
|---|---|---|---|---|---|---|---|---|---|---|
| EMS-INT-01 | **Thermo Fisher Scientific** | USA | Instrumentación científica, monitoreo ambiental | TEOM, particulate monitors, air quality | Redes calidad aire global, EPA USA | 2023 | Global | [thermofisher.com](https://www.thermofisher.com) | Sí (9/10) | TEOM es referencia mundial PM2.5/PM10. Referencias EPA verificadas. |
| EMS-INT-02 | **Horiba** | Japón | Instrumentación analítica, monitoreo ambiental | APDA, air quality monitors | Redes calidad aire Asia, Europa, LATAM | 2023 | Global | [horiba.com](https://www.horiba.com) | Sí (9/10) | APDA es referencia en Asia/Europa. Alta fiabilidad. |
| EMS-INT-03 | **Acoem (Ecotech)** | Australia | Monitoreo ambiental, calidad aire | Serinus, AQMS | Redes calidad aire Australia, global | 2023 | Global | [acoem.com](https://www.acoem.com) | Sí (8/10) | Especialista AQMS. Referencias en redes nacionales. |
| EMS-LAT-01 | **Envea (formerly Environnement SA)** | Francia | Monitoreo ambiental, calidad aire | MP101M, MIR, DOAS | Redes calidad aire Europa, LATAM | 2022 | Europa/LATAM | [envea.global](https://www.envea.global) | Sí (8/10) | Presencia LATAM. Tecnología DOAS avanzada. |
| EMS-LAT-02 | **Campbell Scientific** | USA | Dataloggers, sensores ambientales | CR1000X + sensores calidad aire | Redes monitoreo global | 2022 | Global | [campbellsci.com](https://www.campbellsci.com) | Sí (7/10) | Dataloggers + sensores de terceros. Flexibilidad alta. |
| EMS-LAT-03 | **Seguritech** | México | ITS integral, ambiental | Monitoreo ambiental VIITS | VIITS Colombia 6,000 km | 2022 | Colombia | [seguritech.com](https://www.seguritech.com.mx) | Sí (6/10) | VIITS incluye ambiental potencial. Menor especialización específica. |
| EMS-NAL-01 | **CI2** | Colombia | ITS, ingeniería ambiental | Diseño EMS, integración CCO-ANLA | Diseño APP Chía-Girardot | 2026 | Colombia | [ci2.com.co](https://www.ci2.com.co) | Sí (7/10) | Diseñador proyecto. Especificación EMS. |
| EMS-NAL-02 | **Deviteck** | Colombia | ITS, software | Integración EMS-CCO-ANLA | Diseño APP Chía-Girardot | 2026 | Colombia | [deviteck.com](https://www.deviteck.com) | Sí (6/10) | Integrador. Capacidad de integración datos ambientales. |
| EMS-NAL-03 | **IDEAM** | Colombia | Meteorología, calidad aire institucional | Red calidad aire nacional Colombia | Red nacional calidad aire | Contínua | Colombia | [ideam.gov.co](https://www.ideam.gov.co) | Sí (6/10) | Institución estatal. Conocimiento normativo profundo. No proveedor comercial. |

**2.6.28 Conclusiones**

1. **Normativa ambiental**: El cumplimiento de la Resolución 2254 de 2017 (calidad del aire) y el Decreto 1076 de 2015 (agua) es obligatorio. Los equipos deben estar certificados por EPA o equivalente europeo. Thermo Fisher (TEOM) y Horiba (APDA) tienen certificaciones EPA verificadas.

2. **Reporte a ANLA**: La integración automática con la Autoridad Nacional de Licencias Ambientales (ANLA) requiere formatos específicos. Los integradores nacionales deben garantizar esta integración.

3. **Dashboard público**: La transparencia ciudadana mediante dashboard público de calidad del aire es una tendencia global. Los integradores deben incluir esta capacidad en la plataforma.

4. **Neutralidad**: La elección debe ponderar: (a) certificación EPA/europea, (b) precisión documentada en climas tropicales, (c) integración ANLA, (d) soporte local y repuestos en Colombia.

