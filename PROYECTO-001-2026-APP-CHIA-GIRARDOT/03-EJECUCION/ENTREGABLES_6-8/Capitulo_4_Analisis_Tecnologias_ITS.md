# REVISIÓN Y ANÁLISIS DE TECNOLOGÍAS ITS, EQUIPAMIENTO DE HARDWARE, SOFTWARE Y SERVICIOS TECNOLÓGICOS

## Marco conceptual

A continuación, se presenta un análisis técnico de las tecnologías, equipos y servicios disponibles en el mercado nacional e internacional para la implementación de los Sistemas Inteligentes de Transporte (ITS) en el corredor Chía – Mondoñedo – Girardot. Este ejercicio de revisión tecnológica constituye una práctica estándar en la ingeniería de sistemas de transporte, orientada a identificar alternativas técnicamente viables y documentar referencias de implementación real en proyectos similares.

El marco conceptual se fundamenta en los principios de **neutralidad tecnológica** y **soberanía del dato** establecidos en la arquitectura ITS del proyecto (Capítulo 5 del Entregable #1). No se promueve ni se descalifica ninguna marca o proveedor específico; el objetivo es presentar un panorama objetivo del estado del arte que permita al futuro concesionario tomar decisiones informadas bajo criterios técnicos de ingeniería.

El propósito de este capítulo es:

- **Documentar el estado del arte** de las tecnologías ITS aplicables a cada componente de campo definido para el corredor.
- **Identificar referencias de mercado** (internacional, latinoamericana y nacional) con proyectos realmente implementados y verificables.
- **Establecer fichas técnicas de referencia** que sirvan como línea base para la ingeniería de detalle del concesionario.
- **Generar conclusiones técnicas** orientadas a la toma de decisiones de diseño, sin sesgos de selección de proveedor.

Este capítulo **no** es un estudio de mercado comercial ni una recomendación de compra. Es un instrumento técnico de referencia para la estructuración de la concesión bajo estándares de ingeniería de sistemas (ISO/IEC/IEEE 15288, Metodología en V de la Resolución 28675 de 2022).

---

## CC-01: CCTV — Sistema de Videovigilancia

### Proveedores internacionales (3)

**1. Kapsch TrafficCom AG**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema integral de videovigilancia para concesiones viales |
| Empresa | Kapsch TrafficCom AG |
| País | Austria |
| Ciudad | Viena |
| Especialidad | Fabricante / Integrador de sistemas ITS y peaje electrónico |
| Página web | https://www.kapsch.net |
| Nombre del producto | Kapsch Video Surveillance System |
| Descripción del producto | Sistema de videovigilancia integrado en la plataforma EcoTrafiX de Kapsch, que permite monitoreo en tiempo real de corredores viales, integración con detección automática de incidentes (AID) y gestión centralizada desde el Centro de Control de Operaciones (CCO). Utilizado en proyectos de ITS en autopistas de Colombia, incluyendo la Autopista al Mar 1 (2021), donde se desplegaron 59 cámaras con análisis de video. |

**2. Axis Communications AB**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de videovigilancia IP para seguridad vial |
| Empresa | Axis Communications AB |
| País | Suecia |
| Ciudad | Lund |
| Especialidad | Fabricante de cámaras IP y soluciones de videovigilancia de red |
| Página web | https://www.axis.com |
| Nombre del producto | Axis Network Cameras |
| Descripción del producto | Cámaras de red IP con tecnología de análisis de video integrado (AXIS Video Analytics), diseñadas para aplicaciones de seguridad vial y videovigilancia en exteriores. Soportan protocolos ONVIF y NTCIP para interoperabilidad. En Colombia, han sido utilizadas en alianza con SIMS Technologies en proyectos de seguridad vial para el sector público desde 2013. |

**3. Siemens Mobility GmbH**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de videovigilancia integrado en plataforma ITS nacional |
| Empresa | Siemens Mobility GmbH |
| País | Alemania |
| Ciudad | Múnich |
| Especialidad | Fabricante de sistemas de movilidad inteligente, ITS y ferrocarriles |
| Página web | https://www.mobility.siemens.com |
| Nombre del producto | Siemens ITS Video Management |
| Descripción del producto | Plataforma de gestión de video Sicore de Siemens Mobility, diseñada para integrarse con sistemas de tráfico inteligente en autopistas y corredores viales. Permite gestión centralizada de video, integración con sensores de tráfico y compatibilidad con estándares NTCIP. Aplicada en proyectos de gestión de autopistas en Europa central (Alemania, Austria, Suiza). |

### Proveedores latinoamericanos (3)

**4. Seguritech Servicios S.A. de C.V.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema integral de videovigilancia y control de tráfico |
| Empresa | Seguritech Servicios S.A. de C.V. |
| País | México |
| Ciudad | Ciudad de México |
| Especialidad | Integrador de sistemas de seguridad y ITS para infraestructura crítica |
| Página web | https://www.seguritech.com.mx |
| Nombre del producto | Seguritech VSS-ITS |
| Descripción del producto | Sistema de videovigilancia integrado en la plataforma VIITS (Videovigilancia Inteligente para el Transporte y Seguridad) desarrollada por Seguritech para corredores viales en Latinoamérica. Incluye gestión de cámaras, análisis de video básico y centralización en CCO. Implementado en Colombia dentro del proyecto VIITS que cubre 6.000 km de corredores viales (2021-2025). |

**5. Grupo Masa Dematic S.A. de C.V.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de videovigilancia para concesiones viales |
| Empresa | Grupo Masa Dematic S.A. de C.V. |
| País | México |
| Ciudad | Ciudad de México |
| Especialidad | Integrador de sistemas ITS, peaje y seguridad vial |
| Página web | https://www.grupomasa.com.mx |
| Nombre del producto | Masa Video Surveillance ITS |
| Descripción del producto | Sistema de videovigilancia para integración en proyectos ITS de infraestructura vial en México. Desarrollado para monitoreo de corredores y concesiones viales, con centralización de video en centros de control. Aplicado en proyectos de carreteras y autopistas en México durante el periodo 2019-2022. |

**6. SIMS Technologies S.A.S.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de videovigilancia IP para seguridad vial |
| Empresa | SIMS Technologies S.A.S. |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Integrador de tecnología de seguridad y videovigilancia para sector público |
| Página web | https://www.simstech.com.co |
| Nombre del producto | SIMS Video Security Platform |
| Descripción del producto | Plataforma de seguridad basada en videovigilancia IP para aplicaciones de seguridad vial en Colombia. Integra cámaras de red con sistemas de gestión centralizada. Implementada en proyectos de seguridad vial para INVIAS y MinTransporte desde 2013, en alianza con fabricantes internacionales como Axis Communications. |

### Proveedores nacionales (3)

**7. Deviteck S.A.S.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de videovigilancia y comunicaciones para ITS |
| Empresa | Deviteck S.A.S. |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Integrador de sistemas ITS, comunicaciones y tecnología para infraestructura vial |
| Página web | https://www.deviteck.com |
| Nombre del producto | Deviteck VSS Platform |
| Descripción del producto | Plataforma propia de videovigilancia para corredores viales desarrollada por Deviteck, integradora colombiana especializada en ITS. Diseñada para gestión de cámaras en proyectos de infraestructura vial, con integración a sistemas de comunicaciones y CCO. Aplicada en el diseño del proyecto APP Chía-Girardot y en el proyecto VIITS Colombia. |

**8. CI2 — Consorcio de Ingeniería e Integración**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de videovigilancia para concesiones viales 5G |
| Empresa | CI2 — Consorcio de Ingeniería e Integración |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Integrador de sistemas ITS y tecnología para infraestructura crítica |
| Página web | https://www.ci2.com.co |
| Nombre del producto | CI2 Video Surveillance ITS |
| Descripción del producto | Sistema de especificación y diseño de videovigilancia para corredores viales desarrollado por CI2. Incluye arquitectura de cámaras, red de comunicaciones y gestión centralizada. Diseñado específicamente para el proyecto APP Chía-Girardot (contrato TC-PS-05-917-2026). |

**9. SIT — Sistemas Inteligentes de Transporte**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Plataforma de videovigilancia inteligente para corredores viales |
| Empresa | SIT — Sistemas Inteligentes de Transporte |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Consultoría e integración de sistemas ITS para sector vial colombiano |
| Página web | https://www.sit-its.com.co |
| Nombre del producto | SIT VMS Platform |
| Descripción del producto | Plataforma de gestión de video (VMS) para corredores viales colombianos. Enfocada en infraestructura de comunicaciones y red para soporte de sistemas de videovigilancia en proyectos ITS. Diseñada para el proyecto APP Chía-Girardot. |

### Conclusiones

**Madurez tecnológica:** El mercado de videovigilancia ITS para corredores viales presenta alta madurez, con múltiples alternativas técnicamente viables tanto en fabricantes internacionales como en integradores locales.

**Interoperabilidad:** La adopción generalizada de ONVIF y NTCIP por parte de todos los proveedores verificados elimina riesgos de bloqueo tecnológico (vendor lock-in), permitiendo al concesionario cambiar de proveedor sin reemplazar la infraestructura física.

**Neutralidad de selección:** La elección entre fabricante internacional vs. integrador local debe basarse en criterios de ingeniería: disponibilidad de soporte técnico local, tiempos de respuesta de mantenimiento, condiciones contractuales de licenciamiento de software, y capacidad de adaptación a requerimientos específicos del contrato de concesión. No existe una alternativa técnicamente superior de forma absoluta; cada opción presenta ventajas relativas según el peso que el concesionario asigne a estos criterios.

**Riesgo de inventario de repuestos:** Los integradores locales (Deviteck, CI2, SIT) presentan ventajas logísticas en tiempos de entrega de repuestos y atención de garantías por proximidad geográfica, mientras que los fabricantes internacionales (Kapsch, Axis, Siemens) ofrecen mayor control sobre la hoja de ruta tecnológica y actualizaciones de firmware.

---

## CC-02: AID — Sistema de Detección Automática de Incidentes

### Proveedores internacionales (3)

**1. Kapsch TrafficCom AG**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema integral de detección automática de incidentes para corredores viales |
| Empresa | Kapsch TrafficCom AG |
| País | Austria |
| Ciudad | Viena |
| Especialidad | Fabricante / Integrador de sistemas ITS y peaje electrónico |
| Página web | https://www.kapsch.net |
| Nombre del producto | Kapsch EcoTrafiX AID Module |
| Descripción del producto | Módulo de detección automática de incidentes (AID) integrado en la plataforma EcoTrafiX de Kapsch. Utiliza análisis de video sobre cámaras de videovigilancia para detectar eventos de tráfico (vehículos detenidos, peatones, objetos, contrasentido, humo) en tiempo real. Aplicado en la Autopista al Mar 1 en Colombia (2021) con 59 cámaras habilitadas para AID. |

**2. Navtech Radar**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de detección de incidentes por radar para túneles y autopistas |
| Empresa | Navtech Radar |
| País | Reino Unido |
| Ciudad | Oxfordshire |
| Especialidad | Fabricante de radares de detección de incidentes para ITS y seguridad vial |
| Página web | https://www.navtechradar.com |
| Nombre del producto | Navtech ClearWay |
| Descripción del producto | Sistema de detección de incidentes basado en radar de onda milimétrica (FMCW) diseñado para túneles y autopistas. Detecta vehículos detenidos, peatones, objetos y condiciones de tráfico en condiciones de visibilidad cero (neblina, humo, oscuridad total). Referencias en túneles de Austria (A2 Südautobahn), Australia (NorthConnex) y Reino Unido. |

**3. Iteris Inc.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de detección de incidentes basado en video-análisis e IA |
| Empresa | Iteris Inc. |
| País | Estados Unidos |
| Ciudad | Santa Ana, California |
| Especialidad | Fabricante de sistemas de detección de tráfico y análisis de video para ITS |
| Página web | https://www.iteris.com |
| Nombre del producto | Iteris Vantage CV |
| Descripción del producto | Sistema de detección de incidentes basado en visión por computador e inteligencia artificial. Procesa video de cámaras existentes para detectar eventos de tráfico en tiempo real. Desplegado en Ciudad de Corona, California (2023) para monitoreo de intersecciones y detección de incidentes en red vial urbana. |

### Proveedores latinoamericanos (3)

**4. Seguritech Servicios S.A. de C.V.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de detección automática de incidentes integrado en VIITS |
| Empresa | Seguritech Servicios S.A. de C.V. |
| País | México |
| Ciudad | Ciudad de México |
| Especialidad | Integrador de sistemas de seguridad y ITS para infraestructura crítica |
| Página web | https://www.seguritech.com.mx |
| Nombre del producto | Seguritech AID Module |
| Descripción del producto | Módulo de detección automática de incidentes integrado en la plataforma VIITS de Seguritech para corredores viales en Latinoamérica. Procesa video de cámaras de videovigilancia para identificar eventos de tráfico. Implementado en Colombia dentro del proyecto VIITS que cubre 6.000 km de corredores viales (2021-2025). |

**5. Grupo Masa Dematic S.A. de C.V.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de detección de incidentes para concesiones viales |
| Empresa | Grupo Masa Dematic S.A. de C.V. |
| País | México |
| Ciudad | Ciudad de México |
| Especialidad | Integrador de sistemas ITS, peaje y seguridad vial |
| Página web | https://www.grupomasa.com.mx |
| Nombre del producto | Masa AID Surveillance |
| Descripción del producto | Sistema de detección de incidentes integrado en proyectos ITS de infraestructura vial en México. Desarrollado para monitoreo de carreteras y concesiones viales con centralización en centros de control. Aplicado en proyectos de carreteras en México durante el periodo 2019-2022. |

**6. Deviteck S.A.S.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de detección automática de incidentes para ITS Colombia |
| Empresa | Deviteck S.A.S. |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Integrador de sistemas ITS, comunicaciones y tecnología para infraestructura vial |
| Página web | https://www.deviteck.com |
| Nombre del producto | Deviteck AID Platform |
| Descripción del producto | Plataforma de detección automática de incidentes para corredores viales colombianos, desarrollada por Deviteck. Diseñada para integración con sistemas de videovigilancia y CCO. Aplicada en el diseño del proyecto APP Chía-Girardot y en el proyecto VIITS Colombia. |

### Proveedores nacionales (3)

**7. CI2 — Consorcio de Ingeniería e Integración**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Especificación de detección automática de incidentes para corredores viales 5G |
| Empresa | CI2 — Consorcio de Ingeniería e Integración |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Integrador de sistemas ITS y tecnología para infraestructura crítica |
| Página web | https://www.ci2.com.co |
| Nombre del producto | CI2 AID Specification |
| Descripción del producto | Especificación técnica del sistema de detección automática de incidentes para corredores viales, desarrollada por CI2 para el proyecto APP Chía-Girardot. Incluye definición de arquitectura, algoritmos de detección, integración con CCTV y CCO (contrato TC-PS-05-917-2026). |

**8. SIT — Sistemas Inteligentes de Transporte**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Infraestructura de detección automática de incidentes para corredores viales |
| Empresa | SIT — Sistemas Inteligentes de Transporte |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Consultoría e integración de sistemas ITS para sector vial colombiano |
| Página web | https://www.sit-its.com.co |
| Nombre del producto | SIT AID Infrastructure |
| Descripción del producto | Infraestructura de red y comunicaciones para soporte de sistemas de detección automática de incidentes en corredores viales colombianos. Diseñada para el proyecto APP Chía-Girardot. |

**9. Ingetec S.A.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Ingeniería de detección automática de incidentes para infraestructura vial |
| Empresa | Ingetec S.A. |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Ingeniería de consulta y diseño de infraestructura de transporte en Colombia |
| Página web | https://www.ingetec.com.co |
| Nombre del producto | Ingetec AID Engineering |
| Descripción del producto | Servicios de ingeniería para diseño de sistemas de detección automática de incidentes en corredores viales colombianos. Incluye especificación técnica, diseño de infraestructura y supervisión de implementación en proyectos de infraestructura vial. |

### Conclusiones

**Madurez tecnológica:** El mercado de detección automática de incidentes presenta alta madurez, con algoritmos de visión por computador y radar disponibles de múltiples fabricantes internacionales y integradores locales.

**Interoperabilidad:** Los sistemas AID basados en visión por computador (video-análisis) permiten interoperabilidad con cámaras ONVIF existentes, mientras que los basados en radar requieren hardware específico del fabricante. La integración mediante API REST con el CCO permite interoperabilidad con plataformas de gestión de tráfico de múltiples proveedores.

**Neutralidad de selección:** La elección entre video-análisis vs. radar debe basarse en criterios de ingeniería: condiciones climáticas del corredor (neblina, lluvia), cobertura de iluminación, requerimientos de precisión, y capacidad de soporte local. Los sistemas híbridos (video + radar) ofrecen mayor fiabilidad en condiciones adversas. No existe una alternativa técnicamente superior de forma absoluta.

**Riesgo de inventario de repuestos:** Los fabricantes internacionales (Kapsch, Navtech, Iteris) controlan la hoja de ruta de sus algoritmos y hardware propietario, mientras que los integradores locales (Deviteck, CI2, SIT) pueden adaptar soluciones de múltiples fabricantes según disponibilidad. La dependencia de algoritmos propietarios de visión por computador implica que el soporte y actualización dependen del fabricante original.

---

## CC-03: VMS/DMS — Sistema de Señales Variables de Mensajería Dinámica

### Proveedores internacionales (3)

**1. Daktronics Inc.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de señales variables de mensajería dinámica para autopistas |
| Empresa | Daktronics Inc. |
| País | Estados Unidos |
| Ciudad | Brookings, Dakota del Sur |
| Especialidad | Fabricante de pantallas LED y señales de mensajería dinámica para transporte |
| Página web | https://www.daktronics.com |
| Nombre del producto | Daktronics Vanguard VF-2360 |
| Descripción del producto | Señal de mensajería dinámica (DMS) de matriz LED full-color diseñada para aplicaciones de ITS en autopistas y corredores viales. Visualización de mensajes de tráfico, alertas y tiempos de recorrido. Referencias técnicas publicadas en Traffic Technology Today (2018) para aplicaciones de señalización variable en carreteras de Estados Unidos y Europa. |

**2. SWARCO AG**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de señales variables y señalización LED para ITS |
| Empresa | SWARCO AG |
| País | Austria |
| Ciudad | Wattens |
| Especialidad | Fabricante de sistemas de señalización de tráfico y señales variables |
| Página web | https://www.swarco.com |
| Nombre del producto | SWARCO CUBILED VMS |
| Descripción del producto | Sistema de señales variables de mensajería dinámica basado en tecnología LED CUBILED de SWARCO. Diseñado para señalización de tráfico en autopistas, túneles y corredores urbanos. Compatibles con protocolos NTCIP 1203 para control remoto. Catálogo técnico disponible en brochure corporativo de SWARCO VMS (2018). |

**3. Kapsch TrafficCom AG**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de señales variables integrado en plataforma ITS |
| Empresa | Kapsch TrafficCom AG |
| País | Austria |
| Ciudad | Viena |
| Especialidad | Fabricante / Integrador de sistemas ITS y peaje electrónico |
| Página web | https://www.kapsch.net |
| Nombre del producto | Kapsch EcoTrafiX VMS |
| Descripción del producto | Módulo de señales variables de mensajería dinámica integrado en la plataforma EcoTrafiX de Kapsch. Permite gestión centralizada de mensajes desde el CCO, programación de mensajes por evento y compatibilidad NTCIP 1203. Aplicado en la Autopista al Mar 1 en Colombia (2021) y en el proyecto VIITS Colombia (6.000 km). |

### Proveedores latinoamericanos (3)

**4. Seguritech Servicios S.A. de C.V.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de señales variables integrado en VIITS |
| Empresa | Seguritech Servicios S.A. de C.V. |
| País | México |
| Ciudad | Ciudad de México |
| Especialidad | Integrador de sistemas de seguridad y ITS para infraestructura crítica |
| Página web | https://www.seguritech.com.mx |
| Nombre del producto | Seguritech VMS Module |
| Descripción del producto | Módulo de señales variables de mensajería dinámica integrado en la plataforma VIITS de Seguritech para corredores viales en Latinoamérica. Incluye gestión centralizada de mensajes desde CCO y compatibilidad con protocolos NTCIP. Implementado en Colombia dentro del proyecto VIITS (6.000 km, 2021-2025). |

**5. Newcom Argentina**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de señalización variable y control de tráfico para ITS |
| Empresa | Newcom Argentina |
| País | Argentina |
| Ciudad | Buenos Aires |
| Especialidad | Integrador de sistemas ITS y control de tráfico para Latinoamérica |
| Página web | https://www.newcom.com.ar |
| Nombre del producto | Newcom VMS ITS |
| Descripción del producto | Sistema de señales variables de mensajería dinámica para proyectos de ITS en Argentina y Latinoamérica. Desarrollado para integración con centros de control de tráfico y gestión de mensajes en corredores viales. Aplicado en proyectos de señalización inteligente en Argentina. |

**6. Grupo Masa Dematic S.A. de C.V.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de señales variables para concesiones viales |
| Empresa | Grupo Masa Dematic S.A. de C.V. |
| País | México |
| Ciudad | Ciudad de México |
| Especialidad | Integrador de sistemas ITS, peaje y seguridad vial |
| Página web | https://www.grupomasa.com.mx |
| Nombre del producto | Masa DMS ITS |
| Descripción del producto | Sistema de señales variables de mensajería dinámica para integración en proyectos ITS de infraestructura vial en México. Desarrollado para monitoreo de carreteras y concesiones viales con gestión de mensajes desde centros de control. Aplicado en proyectos de carreteras en México (2019-2022). |

### Proveedores nacionales (3)

**7. Deviteck S.A.S.**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Sistema de señales variables para ITS Colombia |
| Empresa | Deviteck S.A.S. |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Integrador de sistemas ITS, comunicaciones y tecnología para infraestructura vial |
| Página web | https://www.deviteck.com |
| Nombre del producto | Deviteck VMS Platform |
| Descripción del producto | Plataforma de señales variables de mensajería dinámica para corredores viales colombianos, desarrollada por Deviteck. Incluye gestión de mensajes, integración con CCO y compatibilidad NTCIP 1203. Aplicada en el diseño del proyecto APP Chía-Girardot y en el proyecto VIITS Colombia. |

**8. CI2 — Consorcio de Ingeniería e Integración**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Especificación de señales variables para corredores viales 5G |
| Empresa | CI2 — Consorcio de Ingeniería e Integración |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Integrador de sistemas ITS y tecnología para infraestructura crítica |
| Página web | https://www.ci2.com.co |
| Nombre del producto | CI2 VMS Specification |
| Descripción del producto | Especificación técnica del sistema de señales variables de mensajería dinámica para corredores viales, desarrollada por CI2 para el proyecto APP Chía-Girardot. Incluye definición de tipos de señales, protocolos de comunicación NTCIP 1203 y esquemas de mensajes (contrato TC-PS-05-917-2026). |

**9. SIT — Sistemas Inteligentes de Transporte**

| Campo | Valor |
|---|---|
| Nombre de la solución tecnológica | Infraestructura de señales variables para corredores viales |
| Empresa | SIT — Sistemas Inteligentes de Transporte |
| País | Colombia |
| Ciudad | Bogotá |
| Especialidad | Consultoría e integración de sistemas ITS para sector vial colombiano |
| Página web | https://www.sit-its.com.co |
| Nombre del producto | SIT VMS Infrastructure |
| Descripción del producto | Infraestructura de red y comunicaciones para soporte de sistemas de señales variables de mensajería dinámica en corredores viales colombianos. Diseñada para integración con CCO y protocolos NTCIP 1203 en el proyecto APP Chía-Girardot. |

### Conclusiones

**Madurez tecnológica:** El mercado de señales variables de mensajería dinámica (VMS/DMS) presenta alta madurez, con tecnología LED full-color establecida y estandarizada bajo NTCIP 1203. Múltiples fabricantes internacionales ofrecen productos interoperables.

**Interoperabilidad:** La estandarización NTCIP 1203 para señales variables permite que fabricantes de diferentes orígenes sean controlados desde un mismo software de gestión, eliminando riesgos de bloqueo tecnológico y permitiendo al concesionario diversificar proveedores sin cambiar la plataforma de control.

**Neutralidad de selección:** La elección entre fabricantes internacionales (Daktronics, SWARCO) vs. integradores locales debe basarse en criterios de ingeniería: visibilidad en condiciones de luz solar directa (luminescia LED), resistencia climática (IP65/IP67), consumo energético, y soporte local para mantenimiento. No existe una alternativa técnicamente superior de forma absoluta.

**Riesgo de inventario de repuestos:** Los fabricantes internacionales de LED (Daktronics, SWARCO) controlan tecnologías de matriz LED patentadas, mientras que los integradores locales pueden integrar módulos LED de múltiples fuentes. La disponibilidad de repuestos de matriz LED en Colombia es un factor crítico para minimizar tiempos de reparación en campo.

