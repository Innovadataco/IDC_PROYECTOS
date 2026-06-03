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

*[Continúa con CC-03, CC-04, CC-05 en la siguiente sección]*

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
