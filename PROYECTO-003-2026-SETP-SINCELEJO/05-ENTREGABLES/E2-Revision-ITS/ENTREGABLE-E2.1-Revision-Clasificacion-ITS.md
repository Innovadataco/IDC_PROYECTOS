# ENTREGABLE 2.1 — REVISIÓN Y CLASIFICACIÓN DE SERVICIOS ITS

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E2.1  
**Versión:** 2.0 — Reescritura argumentada y fluida  
**Fecha:** 15 de junio de 2026  
**Elaborado por:** ZEUS — InnovaDataCo  
**Revisión:** V2.0 — Borrador para validación del CEO

---

## RESUMEN EJECUTIVO

El presente documento presenta la revisión y clasificación de los Servicios de Sistemas Inteligentes de Transporte (ITS) y subsistemas tecnológicos aplicables al Sistema Estratégico de Transporte Público de Sincelejo (SETP). Esta revisión no se realiza sobre un lienzo en blanco: el SETP Sincelejo acumula una historia tecnológica de más de una década que define, de manera concreta, qué sistemas son pertinentes y cuáles no lo son para este proyecto específico.

**Hallazgo principal:** De los cinco dominios de servicios ITS definidos en la taxonomía internacional (ISO 14813), únicamente los servicios de **Transporte Público** y **Pago Electrónico** resultan directamente aplicables al SETP Sincelejo, dado que este es un sistema de transporte público urbano con recaudo centralizado. Los servicios de Gestión de Tráfico Vial, Logística de Mercancías, Seguridad Vial extendida y Servicios Complementarios (meteorología, reservas multimodales) quedan descartados por no corresponder a la tipología real del sistema: un SETP de 46 vehículos en una ciudad de tamaño medio que no opera peajes, no gestiona carga y no requiere integración con modos de transporte interurbanos. Esta delimitación evita la inclusión de subsistemas innecesarios que encarecerían la contratación y complicarían la operación sin aportar valor real.

**Los cuatro sistemas definidos desde 2015** —SRC, SGCF, SIU y SST— se mapean con precisión a los subsistemas ITS de la normativa colombiana. El Sistema de Recaudo Centralizado (SRC) abarca los subsistemas de Pago Electrónico y Gestión Tarifaria; el Sistema de Gestión y Control de Flota (SGCF) abarca los subsistemas de Gestión de Flota y Centro de Control; el Sistema de Información al Usuario (SIU) abarca el subsistema de Información al Usuario; y el Sistema de Seguridad de Transacciones (SST) transversaliza los componentes de seguridad en todos los subsistemas. Este mapeo no es una formalidad burocrática: es la base técnica sobre la cual se construirán las especificaciones, los requerimientos y los criterios de evaluación de la contratación.

---

## 1. CONTEXTO Y ANTECEDENTES

### 1.1 La historia tecnológica del SETP Sincelejo como marco de referencia

El Sistema Estratégico de Transporte Público de Sincelejo no es un proyecto nacido en 2026. Su componente tecnológico fue definido en **2015** por la Unión Temporal Steer Davies Gleave + GSD+, que estructuró tres sistemas originales: el Sistema de Recaudo Centralizado (SRC), el Sistema de Gestión y Control de Flota (SGCF) y el Sistema de Información al Usuario (SIU). Esta estructuración no fue genérica: fue el resultado de un estudio de prefactibilidad que analizó la demanda de transporte de Sincelejo, la red de rutas propuesta, los actores institucionales y los estándares tecnológicos disponibles en ese momento.

En **2022**, la empresa A4 Asociados SAS actualizó el modelo de transporte bajo el contrato CM-001-2022, manteniendo vigentes los tres sistemas originales y confirmando que la tecnología definida en 2015 seguía siendo pertinente para el modelo actualizado. En **2023**, el Ministerio de Transporte lanzó un proceso de contratación ITS que agregó un cuarto sistema: el Sistema de Seguridad de Transacciones (SST), y definió una flota de 46 vehículos. Este proceso no se adjudicó, pero dejó documentada una arquitectura tecnológica de cuatro sistemas que es la base de esta consultoría.

En **2025**, Metro Sabanas S.A.S. lanzó un RFI que integra tres contratos (flota + tecnología + operación), y en **2026** contrata a Innovadataco para estructurar los componentes tecnológicos. Esta consultoría, por tanto, no inventa subsistemas nuevos: **mapea, valida y estructura** los cuatro sistemas definidos históricamente con la taxonomía ITS de la normativa colombiana, para producir un Estudio Previo ITS que alimente el proceso de licitación.

### 1.2 La importancia de la clasificación ITS para la contratación

La clasificación de servicios ITS no es un ejercicio académico. Es una herramienta práctica que permite: (a) definir qué subsistemas deben incluirse en los pliegos de contratación; (b) establecer qué subsistemas son prioridad y cuáles pueden diferirse; (c) identificar los componentes de hardware, software e interfaces que cada subsistema requiere; y (d) estructurar los requerimientos funcionales y no funcionales de manera trazable a subsistemas concretos.

Una clasificación incorrecta —por ejemplo, incluir subsistemas de gestión de tráfico urbano o control de peajes en un SETP que no los requiere— genera sobredimensionamiento, costos innecesarios y complejidad operativa. Por el contrario, una clasificación correcta que se limite a los subsistemas realmente pertinentes permite una contratación enfocada, con especificaciones claras y criterios de evaluación acotados.

---

## 2. MARCO NORMATIVO Y ESTÁNDARES

### 2.1 La normativa colombiana como base de la clasificación

La normativa colombiana de ITS proporciona el marco regulatorio sobre el cual se construye la clasificación de subsistemas. No es un mero formalismo: es la base técnica que los oferentes de la licitación deberán cumplir, y que el Ministerio de Transporte verificará en la supervisión del contrato.

El **Decreto 393 de 2010**, modificado por el **Decreto 482 de 2023**, establece la regulación del transporte público en Colombia, incluyendo los lineamientos para la implementación de sistemas tecnológicos en los SETP. El **Decreto 2060 de 2015** define la Estrategia Nacional de ITS, estableciendo las prioridades de despliegue de estos sistemas en el país. La **Resolución 20203040034065 del Ministerio de Transporte (2020)** es el documento más relevante para esta consultoría: establece los estándares técnicos de ITS, define los subsistemas, los componentes de campo, los centros de control y las arquitecturas de comunicación que deben cumplir los sistemas desplegados en Colombia. La **Resolución 28675 de 2022** y la **Resolución 20223040028675** actualizan el Plan Maestro de ITS Colombia (PMITS), estableciendo prioridades y lineamientos para el despliegue en corredores viales y sistemas de transporte público.

### 2.2 Los estándares internacionales como referencia técnica

Adicionalmente a la normativa colombiana, los estándares internacionales proporcionan un marco de referencia técnica que asegura la interoperabilidad y la calidad de los sistemas. La serie **ISO 14813** es particularmente relevante: la parte 1 (Framework de ITS) establece la arquitectura de referencia; la parte 5 (Referencia de servicios ITS) define la taxonomía de servicios; y la parte 6 (Identificación de usuarios) establece los mecanismos de identificación en sistemas de transporte. La norma **NTC 6203** adopta los estándares internacionales de ITS para el contexto colombiano, asegurando que los sistemas desplegados en el país cumplan con estándares globales de calidad y interoperabilidad.

Estos estándares no son opcionales: son la base sobre la cual los proveedores tecnológicos diseñan sus sistemas, y sobre la cual Metro Sabanas S.A.S. evaluará las ofertas en el proceso de contratación. Un Estudio Previo ITS que no cite estos estándares corre el riesgo de generar sistemas que no sean interoperables con la red nacional de ITS ni con los sistemas de otros SETP en Colombia.

---

## 3. CLASIFICACIÓN DE SERVICIOS ITS PARA EL SETP SINCELEJO

### 3.1 La taxonomía ISO 14813 y su aplicación selectiva

La taxonomía internacional de servicios ITS (ISO 14813) organiza los servicios en cinco dominios principales: Servicios de Tráfico y Gestión Vial, Servicios de Transporte Público, Servicios de Mercancías y Logística, Servicios de Seguridad Vial, y Servicios de Apoyo y Complementarios. Esta taxonomía es exhaustiva: cubre desde el control de tráfico urbano hasta la gestión de vehículos peligrosos, pasando por la información meteorológica y las reservas multimodales.

Sin embargo, la exhaustividad de la taxonomía no implica que todos los dominios sean aplicables a todos los proyectos. La aplicación debe ser **selectiva y justificada**, basada en la tipología real del sistema de transporte. Para el SETP Sincelejo, un sistema de transporte público urbano de 46 vehículos en una ciudad de tamaño medio, la aplicación de la taxonomía revela que solo dos dominios son directamente pertinentes: **Transporte Público** y **Pago Electrónico** (que en la taxonomía se clasifica como Servicio de Apoyo, pero para un SETP es un componente central del recaudo).

Los otros dominios quedan descartados por las siguientes razones. Los **Servicios de Tráfico y Gestión Vial** (control de tráfico urbano, gestión de incidentes, control de peajes) no son pertinentes porque el SETP Sincelejo no opera sobre corredores viales con peajes, ni requiere sistemas de control de tráfico urbano integrados: el sistema se enfoca en la gestión de la flota de buses, no en la gestión del tráfico general de la ciudad. Los **Servicios de Mercancías y Logística** (gestión de flotas comerciales, intercambio electrónico de datos) son irrelevantes porque el SETP es un sistema de transporte de pasajeros, no de carga. Los **Servicios de Seguridad Vial extendida** (asistencia en emergencias, gestión de vehículos peligrosos, prevención de accidentes) quedan fuera del alcance porque, aunque la seguridad es importante, estos subsistemas específicos corresponden a sistemas de carreteras y corredores viales, no a un SETP urbano. Los **Servicios de Apoyo y Complementarios** (información meteorológica, reservas y viajes combinados) no son pertinentes porque Sincelejo no requiere integración con modos de transporte interurbanos ni sistemas de reserva multimodal.

Esta selectividad no es una limitación: es una **precisión**. Incluir subsistemas innecesarios en la contratación generaría costos adicionales, complejidad operativa y riesgos de fallo en componentes que no aportan valor al sistema. La clasificación correcta es, por tanto, una herramienta de optimización de recursos.

### 3.2 Los subsistemas ITS pertinentes para el SETP Sincelejo

Dentro de los dominios pertinentes, se identifican cinco subsistemas ITS que mapean directamente a los cuatro sistemas definidos históricamente para el SETP Sincelejo. Estos subsistemas no son una creación de esta consultoría: son la traducción de los sistemas SRC, SGCF, SIU y SST al lenguaje técnico de la normativa ITS colombiana.

**El subsistema de Gestión de Flota** corresponde al SGCF y abarca la localización satelital de buses mediante GPS/GNSS, el diagnóstico a bordo mediante OBD-II, la transmisión de datos de flota mediante comunicaciones M2M (machine-to-machine), y la información al pasajero a bordo mediante pantallas. Este subsistema es prioritario porque sin él no es posible conocer la ubicación de los buses, su estado mecánico ni transmitir información a los pasajeros en tiempo real.

**El subsistema de Centro de Control** corresponde también al SGCF y abarca la plataforma de visualización de la operación (software CVP), la infraestructura computacional (servidores), la videovigilancia (CCTV) y la base de datos histórica (almacenamiento). Este subsistema es el cerebro operativo del sistema: sin un centro de control funcional, la gestión de flota se reduce a rastreo pasivo sin capacidad de supervisión ni toma de decisiones en tiempo real.

**El subsistema de Información al Usuario** corresponde al SIU y abarca la aplicación móvil para información en tiempo real, las pantallas LED en paradas para tiempos de espera, las notificaciones SMS/WhatsApp y el portal web para planificación de viajes. Este subsistema es prioritario porque es la interfaz directa entre el sistema y los pasajeros: sin información clara y oportuna, los usuarios no pueden planificar sus viajes ni confiar en el sistema.

**El subsistema de Pago Electrónico** corresponde al SRC y abarca los validadores a bordo para lectura de tarjetas, el sistema backoffice para conciliación financiera, las tarjetas sin contacto como medio de pago y el portal de recargas en línea. Este subsistema es crítico porque es el mecanismo de recaudo del sistema: sin un pago electrónico confiable, el sistema no puede financiar su operación ni ofrecer tarifas integradas.

**El subsistema de Gestión Tarifaria** corresponde también al SRC y abarca el motor tarifario para cálculo de tarifas, la integración con subsidios de transporte y los reportes financieros de consolidación. Este subsistema es prioritario porque define cómo se calculan las tarifas, cómo se aplican los subsidios y cómo se reporta la recaudación a las autoridades.

---

## 4. MAPEO SISTEMAS SETP ↔ SUBSISTEMAS ITS

### 4.1 La coherencia entre la historia del proyecto y la normativa

El mapeo entre los cuatro sistemas definidos históricamente para el SETP Sincelejo y los subsistemas ITS de la normativa colombiana no es una traducción mecánica: es una **validación de coherencia**. Si los sistemas definidos en 2015 no se mapean de manera lógica a los subsistemas ITS, eso indicaría una inconsistencia en la arquitectura original que debería ser corregida. Por el contrario, si el mapeo es coherente, confirma que la arquitectura definida en 2015 sigue siendo válida y puede ser la base de la contratación actual.

En este caso, el mapeo es coherente y directo. El **Sistema de Recaudo Centralizado (SRC)** se compone de los subsistemas de Pago Electrónico y Gestión Tarifaria. Esto es lógico porque el recaudo centralizado implica tanto el mecanismo de pago (validadores, tarjetas, backoffice) como la lógica de tarifas (cálculo, subsidios, reportes). El **Sistema de Gestión y Control de Flota (SGCF)** se compone de los subsistemas de Gestión de Flota y Centro de Control. Esto es lógico porque la gestión de flota requiere tanto los dispositivos a bordo (GPS, comunicaciones) como la infraestructura de supervisión (centro de control, servidores, visualización). El **Sistema de Información al Usuario (SIU)** se compone del subsistema de Información al Usuario, con componentes compartidos del Centro de Control (servidores, base de datos). Esto es lógico porque la información al usuario proviene de los datos de operación que se procesan en el centro de control. El **Sistema de Seguridad de Transacciones (SST)** transversaliza los componentes de seguridad en todos los subsistemas: cifrado de comunicaciones, autenticación de usuarios, auditoría de transacciones. Esto es lógico porque la seguridad no es un subsistema aislado: es una propiedad que debe estar presente en todos los componentes del sistema.

### 4.2 Los tres escenarios institucionales como marco de contratación

Los tres escenarios institucionales definidos en 2015 no son una curiosidad histórica: son un **marco de referencia para la estructura de la contratación**. El RFI 2025 de Metro Sabanas integra tres contratos (flota + tecnología + operación), y la forma en que esos contratos se agrupan o separan depende de qué escenario institucional se adopte.

El **escenario "Base"** asume que un concesionario externo opera el SRC (el sistema más complejo técnicamente y con mayor riesgo financiero), mientras que Metro Sabanas opera directamente el SGCF y el SIU. Este escenario implica una contratación separada para el SRC y una operación directa para los otros sistemas. El **escenario "Socio tecnológico"** asume que un único concesionario opera los cuatro sistemas (SRC, SGCF, SIU, SST). Este escenario simplifica la contratación —un solo contrato tecnológico— pero concentra el riesgo en un único proveedor. El **escenario "Operador recaudador"** asume que el operador de transporte asume la operación de los cuatro sistemas. Este escenario da mayor control operativo a Metro Sabanas pero requiere mayor capacidad técnica interna.

Estos escenarios no son mutuamente excluyentes: el RFI 2025 permite a la empresa operadora proponer modelos integrados donde un mismo proveedor asuma uno, dos o los tres contratos, o se asocie con otros proveedores. Los escenarios de 2015, por tanto, son las **opciones estructurales** que los oferentes pueden proponer, y esta consultoría las documenta para que el proceso de contratación las reconozca y evalúe.

---

## 5. PRIORIZACIÓN DE SUBSISTEMAS

### 5.1 La lógica de la priorización

La priorización de subsistemas no se basa en una intuición subjetiva, sino en una **evaluación multidimensional** que considera tres factores: el impacto operativo (qué tan crítico es el subsistema para la operación del SETP), la complejidad técnica (qué tan difícil es implementar y operar el subsistema) y el costo (qué tan caro es adquirir, instalar y mantener el subsistema). La combinación de estos tres factores produce una priorización que permite a Metro Sabanas S.A.S. decidir qué subsistemas deben contratarse primero, cuáles pueden agruparse en un mismo contrato y cuáles pueden diferirse a una fase posterior.

Los subsistemas de **Gestión de Flota, Centro de Control y Pago Electrónico** se clasifican como **prioridad 1 (Crítico)**. Esto se debe a que: (a) tienen alto impacto operativo —sin ellos, el sistema no puede operar—; (b) tienen alta complejidad técnica —requieren integración de hardware, software y comunicaciones—; y (c) tienen costo medio a alto —requieren inversión significativa en equipos e infraestructura. La combinación de estos tres factores indica que estos subsistemas deben ser el foco de la contratación principal, con especificaciones detalladas, criterios de evaluación rigurosos y garantías extendidas.

Los subsistemas de **Información al Usuario y Gestión Tarifaria** se clasifican como **prioridad 2 (Importante)**. Esto se debe a que: (a) tienen impacto operativo medio —son importantes para la calidad del servicio pero el sistema puede operar sin ellos en una fase inicial—; (b) tienen complejidad técnica media —requieren desarrollo de software y diseño de interfaces pero no integración de hardware complejo—; y (c) tienen costo medio —son menos caros que los subsistemas críticos. La combinación de estos factores indica que estos subsistemas pueden contratarse junto con los críticos o en una fase posterior, dependiendo de la estructura de contratación que adopte Metro Sabanas.

### 5.2 Implicaciones de la priorización para la contratación

La priorización de subsistemas tiene implicaciones directas en la estructura del RFI y el RFQ. Si Metro Sabanas adopta el escenario "Socio tecnológico" (un solo proveedor para los cuatro sistemas), todos los subsistemas se contratan simultáneamente y la priorización sirve para definir los hitos de entrega: los críticos primero, los importantes después. Si Metro Sabanas adopta el escenario "Base" (SRC separado, SGCF+SIU directo), la priorización sirve para definir qué subsistemas van en el contrato de tecnología (SRC) y cuáles en la operación directa (SGCF+SIU). Si Metro Sabanas adopta una estructura de contratación por fases, la priorización define cuáles subsistemas se contratan en la fase 1 y cuáles en la fase 2.

---

## 6. INTEROPERABILIDAD Y ESTÁNDARES DE COMUNICACIÓN

### 6.1 La interoperabilidad como requisito transversal

La interoperabilidad no es un subsistema aislado: es una **propiedad transversal** que debe estar presente en todos los componentes del sistema. Sin interoperabilidad, los cuatro sistemas (SRC, SGCF, SIU, SST) operarían como silos independientes, sin capacidad de compartir datos ni de coordinar acciones. Esto generaría duplicación de información, inconsistencias operativas y pérdida de eficiencia.

La interoperabilidad del SETP Sincelejo se fundamenta en tres capas. La primera es la **interoperabilidad interna**: los cuatro sistemas deben comunicarse entre sí mediante protocolos estándar. El SGCF debe enviar la ubicación de los buses al SIU para que la app muestre tiempos de llegada; el SRC debe enviar la recaudación al SGCF para que el centro de control genere reportes de productividad; el SST debe proteger todas las comunicaciones entre sistemas. La segunda es la **interoperabilidad con sistemas nacionales**: si en el futuro Colombia implementa un sistema nacional de recaudo o un sistema nacional de información de transporte, el SETP Sincelejo debe poder integrarse sin rediseño completo. La tercera es la **interoperabilidad con estándares internacionales**: los sistemas deben usar protocolos y formatos reconocidos globalmente (GTFS-RT para información de transporte, NTCIP para comunicaciones de campo, IEEE 802.11p para comunicaciones de corto alcance) para facilitar la integración con tecnologías de proveedores internacionales.

### 6.2 Los estándares de comunicación como base de la interoperabilidad

Los estándares de comunicación no son opciones técnicas: son **requisitos de diseño** que aseguran la interoperabilidad. Para el SETP Sincelejo, se identifican cuatro estándares fundamentales.

**DSRC (Dedicated Short Range Communications)** mediante WAVE IEEE 802.11p es el estándar para comunicaciones de corto alcance entre vehículos e infraestructura. Aunque el SETP Sincelejo no requiere comunicaciones V2I (vehículo a infraestructura) en una primera fase, la adopción de este estándar asegura que los validadores a bordo puedan comunicarse con las paradas equipadas en el futuro, sin necesidad de reemplazar el hardware.

**Celular 4G/LTE (5G ready)** es el estándar para comunicaciones de largo alcance entre los buses y el centro de control. La red celular es la infraestructura de comunicaciones más viable para un SETP urbano, dado que no requiere despliegue de infraestructura propia de radiofrecuencia. La especificación "5G ready" asegura que los dispositivos a bordo sean compatibles con la evolución de la red celular sin necesidad de reemplazo masivo.

**GPS/GNSS y GLONASS** son los estándares para localización satelital. La adopción de múltiples constelaciones (GPS estadounidense y GLONASS ruso) mejora la precisión y la disponibilidad de la señal, especialmente en entornos urbanos donde la visibilidad del cielo puede estar limitada por edificios.

**Protocolos de aplicación: NTCIP, SAE J2735, GTFS-RT** son los estándares para el formato de los datos intercambiados. NTCIP (National Transportation Communications for ITS Protocol) es el estándar para comunicaciones entre centros de control y dispositivos de campo. SAE J2735 es el estándar para mensajes de seguridad y movilidad en ITS. GTFS-RT (General Transit Feed Specification - Realtime) es el estándar para información de transporte público en tiempo real, adoptado globalmente por Google Maps, Apple Maps y otras aplicaciones de movilidad. La adopción de GTFS-RT asegura que la información del SETP Sincelejo pueda ser consumida por aplicaciones de terceros, aumentando la visibilidad del sistema.

---

## 7. RECOMENDACIONES ESTRATÉGICAS

La revisión y clasificación de servicios ITS para el SETP Sincelejo produce cinco recomendaciones estratégicas que deben guiar la estructuración de la contratación.

**Primera:** Priorizar los subsistemas críticos (Gestión de Flota, Centro de Control, Pago Electrónico) en la estructura del RFI y el RFQ. Estos subsistemas deben tener especificaciones más detalladas, criterios de evaluación más rigurosos y garantías más extendidas que los subsistemas de prioridad 2. La contratación debe asegurar que estos subsistemas sean operativos antes de la inauguración del sistema.

**Segunda:** Adoptar una arquitectura modular que permita la escalabilidad futura. El SETP Sincelejo inicia con 46 vehículos, pero la flota puede crecer en el futuro. Los subsistemas deben diseñarse para soportar un crecimiento de al menos 100 vehículos sin rediseño completo de la arquitectura. Esto implica servidores con capacidad de expansión, software con licencias escalables y comunicaciones con ancho de banda suficiente para el crecimiento.

**Tercera:** Garantizar la interoperabilidad con sistemas nacionales desde el diseño. Aunque el SETP Sincelejo es un sistema local, la normativa colombiana exige que los sistemas ITS sean interoperables con la red nacional. Esto implica adoptar los estándares definidos en la Resolución 20203040034065, usar protocolos reconocidos internacionalmente y documentar las interfaces para futuras integraciones.

**Cuarta:** Considerar soluciones cloud-híbridas para reducir el CAPEX inicial. Un centro de control completamente on-premise requiere inversión significativa en servidores, almacenamiento, redes eléctricas y climatización. Una solución cloud-híbrida, donde la infraestructura de cómputo está en la nube y los dispositivos de campo son locales, puede reducir el CAPEX inicial y trasladar parte del costo a un modelo OPEX (operativo). Sin embargo, esta decisión debe evaluarse considerando la disponibilidad de conectividad en Sincelejo, la latencia requerida para el control en tiempo real y los requisitos de seguridad de la información.

**Quinta:** Planificar la implementación por fases de prioridad operacional. Aunque esta consultoría no cubre la implementación, la estructuración de la contratación debe permitir una implementación por fases. La fase 1 debería incluir los subsistemas críticos (Gestión de Flota, Centro de Control, Pago Electrónico); la fase 2 debería incluir los subsistemas importantes (Información al Usuario, Gestión Tarifaria); y la fase 3 debería incluir mejoras y expansiones (por ejemplo, integración con aplicaciones de terceros, analytics avanzado, inteligencia artificial para predicción de demanda).

---

## 8. GLOSARIO DE TÉRMINOS TÉCNICOS

| Término | Definición |
|---------|------------|
| **ITS** | Intelligent Transportation Systems — Sistemas Inteligentes de Transporte |
| **SETP** | Sistema Estratégico de Transporte Público |
| **SRC** | Sistema de Recaudo Centralizado |
| **SGCF** | Sistema de Gestión y Control de Flota |
| **SIU** | Sistema de Información al Usuario |
| **SST** | Sistema de Seguridad de Transacciones |
| **ATMS** | Advanced Traffic Management System — Sistema Avanzado de Gestión de Tráfico |
| **APTS** | Advanced Public Transportation System — Sistema Avanzado de Transporte Público |
| **CVP** | Centro de Visualización y Procesamiento |
| **OBD-II** | On-Board Diagnostics — Diagnóstico a Bordo |
| **DSRC** | Dedicated Short Range Communications — Comunicaciones de Corto Alcance Dedicadas |
| **GTFS-RT** | General Transit Feed Specification - Realtime — Especificación General de Feeds de Transporte en Tiempo Real |
| **CAPEX** | Capital Expenditure — Gasto de Capital |
| **OPEX** | Operating Expenditure — Gasto Operativo |

---

**Documento elaborado por ZEUS — InnovaDataCo | 2026-06-15 | Versión 2.0**
