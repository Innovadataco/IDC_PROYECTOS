# CAPÍTULO: TECNOLOGÍAS ITS COMO HERRAMIENTAS PARA LA MEJORA DE LA PRESTACIÓN DEL SERVICIO EN CONCESIONES VIALES 5G

## Documento de Orientación para el Proyecto APP Chía-Girardot

---

## 1. INTRODUCCIÓN

El presente capítulo desarrolla una orientación sobre las tecnologías de Sistemas Inteligentes de Transporte (ITS) que pueden ser consideradas por el futuro concesionario del corredor APP Chía-Girardot como herramientas para mejorar la prestación del servicio vial. Esta orientación no constituye una especificación técnica obligatoria ni una lista cerrada de tecnologías a implementar, sino un ejercicio de prospectiva que presenta opciones verificadas en proyectos reales, dejando en manos del concesionario la valoración de su aplicabilidad, priorización y adopción según su modelo de negocio, su estrategia de riesgo y las condiciones contractuales que defina la autoridad concedente.

La concesión APP Chía-Girardot, con una extensión de 306 kilómetros, una vía arterial de 158 km, vías colectoras de 148 km, y un Tráfico Promedio Diario Anual (TPDA) aproximado de 40.000 vehículos, opera bajo una modalidad Brownfield donde la infraestructura ya existe y requiere actualización. El modelo de quinta generación (5G) bajo el que se estructura esta concesión orienta la tecnología hacia la protección de la vida, la eficiencia operativa y la sostenibilidad contractual, sin que ello implique una tecnología única o un camino obligatorio. La Ley 1702 de 2013, el Decreto 2060 de 2015 y la Resolución 28675 de 2022 del Ministerio de Transporte establecen el marco normativo para los ITS en Colombia, pero no prescriben tecnologías específicas: definen funciones, estándares de interoperabilidad y soberanía del dato, dejando abierto el espacio para que el concesionario seleccione las herramientas que mejor respondan a las necesidades del corredor.

Este documento se fundamenta en proyectos reales verificables donde las tecnologías que se presentan a continuación ya están operando. No se incluyen proyecciones especulativas, ni se asumen como únicas las tecnologías mencionadas: el mercado de ITS es amplio, diverso y en constante evolución, y el concesionario podrá evalar alternativas no mencionadas aquí siempre que cumplan con los estándares de interoperabilidad y la gobernanza de datos que exige el marco regulatorio colombiano.

---

## 2. PRINCIPIO DE NEUTRALIDAD TECNOLÓGICA

Antes de desarrollar las tecnologías, es necesario establecer un principio fundamental que debe regir toda la estructuración del componente ITS de esta concesión: la neutralidad tecnológica. El futuro concesionario no estará obligado a implementar ninguna de las tecnologías que se presentan en este documento. Este capítulo es, en rigor, un instrumento de información que amplía el espectro de posibilidades que el concesionario podrá evaluar durante la estructuración de su oferta técnica y económica.

La neutralidad tecnológica implica que la autoridad concedente (ICCU, con estándares de la ANI) debe definir los resultados esperados —reducción de siniestralidad, nivel de servicio, disponibilidad de la vía, información al usuario, eficiencia energética— sin prescribir los medios tecnológicos para alcanzarlos. El concesionario, a su vez, deberá proponer las tecnologías, combinaciones y estrategias que considere más eficientes para cumplir con esos resultados, asumiendo el riesgo técnico y financiero de su elección. Esta lógica es coherente con el modelo 5G, donde el concesionario asume riesgos de construcción, operación y demanda, y donde la innovación tecnológica es una herramienta de diferenciación competitiva, no una obligación estandarizada.

Este enfoque también protege la soberanía del dato: el Decreto 2060 de 2015 establece que la información generada por los ITS es un activo de utilidad pública, independientemente de la tecnología que la produzca. El concesionario es el custodio técnico, no el propietario, y debe garantizar que los datos sean interoperables, auditables y reportables a las autoridades de Inspección, Vigilancia y Control (IVC) y a las entidades del sector transporte, sin importar la marca o el modelo de los equipos desplegados.

---

## 3. TECNOLOGÍAS DE IDENTIFICACIÓN VEHICULAR Y COBRO ELECTRÓNICO

### 3.1 Contexto de aplicabilidad en el corredor

La identificación vehicular es una función ITS que puede mejorar significativamente la prestación del servicio en múltiples dimensiones: gestión de tráfico, seguridad vial, fiscalización de cargas, y generación de información para la toma de decisiones. En el corredor Chía-Girardot, esta función puede ser especialmente relevante en túneles, zonas de alta siniestralidad, y puntos de control donde el conocimiento del flujo vehicular permite anticipar congestión y responder proactivamente a incidentes.

El modelo 5G de la concesión no incluye peaje tradicional como fuente de ingresos, pero esto no elimina la utilidad de la identificación vehicular. Por el contrario, libera la tecnología de su función restrictiva (cobro) para expandirla hacia funciones de gestión operativa: conteo de vehículos por tipo, detección de patrones de flujo, identificación de vehículos detenidos o en contravía, y generación de estadísticas de uso del corredor que alimenten la planificación de mantenimiento y la gestión de la demanda.

### 3.2 Tecnologías disponibles y proyectos de referencia

El mercado ofrece múltiples tecnologías para la identificación vehicular, cada una con distintas capacidades, costos y condiciones de aplicación. La comunicación de corto alcance (DSRC) permite el intercambio de datos entre vehículos equipados y la infraestructura de la vía, con alcance de hasta 300 metros y latencia muy baja. Esta tecnología ya opera en autopistas de España, donde la concesionaria Audasa la utiliza en la A-1 para peaje free flow, y en Brasil, donde el sistema Telepase la emplea en múltiples corredores con una penetración significativa en el parque automotor. El reconocimiento de placas por video (LPR/ANPR) es una tecnología madura que permite identificar vehículos sin requerir equipamiento embarcado, operando en proyectos como la autopista Palmillas–Apaseo en México, donde se instala cada 7 kilómetros para integridad vehicular. El RFID pasivo, de menor costo y menor alcance, se utiliza en el Tag de Chile y en el Telepase de Brasil para identificación de baja complejidad. Los sistemas basados en GPS/GNSS permiten el rastreo por ubicación sin infraestructura física de lectura, aunque su aplicación masiva para peaje aún está en fase de pilotos en Europa y no tiene despliegue significativo en Latinoamérica.

Ninguna de estas tecnologías es excluyente. Un concesionario podría optar por una combinación: DSRC para flotas comerciales que voluntariamente se equipen, LPR para fiscalización general y estadísticas de tráfico, y RFID para servicios específicos de suscripción. La elección dependerá de la estrategia comercial del concesionario, la demanda de servicios por parte de los usuarios, y la disposición de la autoridad a permitir la recolección de datos de identificación bajo los límites de la Ley 1581 de 2012 de protección de datos personales.

### 3.3 Aplicabilidad al corredor Chía-Girardot

Para el corredor Chía-Girardot, la identificación vehicular puede ser una herramienta de gestión del tráfico y de seguridad, no necesariamente de cobro. Los túneles del corredor requieren monitoreo constante del flujo; la identificación permite detectar vehículos detenidos, calcular tiempos de recorrido por tramo, y generar alertas automáticas cuando el flujo excede la capacidad diseñada. La vía arterial, con sus 158 kilómetros, presenta zonas de alta siniestralidad donde la identificación de vehículos en contravía o a velocidades anómalas puede ser una herramienta preventiva. Las vías colectoras, con alta interacción con tráfico local, pueden beneficiarse de sistemas de identificación que detecten patrones de congestión en tiempo real.

El concesionario podría también ofrecer, como servicio voluntario, tarjetas de identificación para flotas comerciales que circulan regularmente por el corredor —transporte de carga, distribución de mercancías, transporte público— generando datos de movimiento que el concesionario utilice para optimizar la gestión del tráfico y que el usuario utilice para planificar sus rutas. Este modelo, ya probado en concesiones chilenas y brasileñas, convierte la identificación vehicular en un servicio de valor agregado, no en una imposición.

---

## 4. TECNOLOGÍAS DE MOVILIDAD CONECTADA

### 4.1 Estado real de la comunicación vehículo-infraestructura

La movilidad conectada —bajo sus distintas modalidades de comunicación entre vehículos, infraestructura y centros de control— es una de las áreas más dinámicas del sector ITS, pero también una de las más desmitificadas. Es importante establecer con claridad que, al cierre de 2026, la comunicación vehículo-infraestructura (V2I) no es una tecnología de despliegue masivo comercial: es una tecnología de piloto y de capacidad reservada. Su penetración en el parque automotor global es inferior al 1%, y no existe regulación obligatoria en Colombia ni en la mayoría de países latinoamericanos.

Esto no significa que la tecnología sea irrelevante para el corredor Chía-Girardot. Significa que su aplicación debe ser estratégica, no masiva: instalarse donde aporte valor tangible en condiciones específicas, y no como un despliegue obligatorio en toda la extensión del corredor. La tecnología V2I requiere la instalación de unidades de carretera (RSU) que se comunican con unidades embarcadas en los vehículos (OBU). Los estándares incluyen el DSRC (IEEE 802.11p) y el C-V2X (basado en celular 4G/5G). Ambos son tecnológicamente viables, pero la decisión de cuál adoptar —o si adoptar ambos en diferentes tramos— es una decisión del concesionario que dependerá de la evolución del mercado automotriz, la regulación colombiana, y la demanda de servicios por parte de flotas específicas.

### 4.2 Proyectos de referencia donde se evalúa la tecnología

El corredor Bizkaia en España opera desde 2023 un piloto de 60 kilómetros con 25 unidades de carretera (RSU) en la autopista A-8, comunicándose con vehículos equipados con unidades embarcadas. Este proyecto es financiado con fondos públicos y privados, y su objetivo es la validación técnica, no la generación de ingresos comerciales directos. En Estados Unidos, el proyecto Smart Columbus en Ohio completó un piloto de corredor conectado entre 2018 y 2020, financiado por el Departamento de Transporte federal. La Universidad de Michigan opera el campus Mcity como laboratorio de pruebas V2I con semáforos conectados. En Madrid, el ayuntamiento ejecutó un piloto en la Avenida de la Ilustración con semáforos conectados y RSU. Estos proyectos comparten una característica: son pilotos de investigación y validación, no servicios comerciales masivos.

### 4.3 Aplicabilidad al corredor Chía-Girardot

Para el corredor Chía-Girardot, la tecnología de movilidad conectada debe concebirse como una **capacidad de reserva**, no como una obligación de despliegue inmediato. La concesión tiene 306 kilómetros de extensión, y la instalación masiva de RSU a lo largo de todo el corredor sería una inversión significativa sin una base de usuarios que la justifique económicamente. Sin embargo, la concesión puede diseñar su infraestructura de telecomunicaciones —fibra óptica, energía eléctrica, torres de comunicación— de manera que, en el futuro, la instalación de RSU en zonas críticas sea técnicamente posible sin requerir obra civil adicional.

Las zonas críticas donde la movilidad conectada podría aportar valor tangible son los túneles, donde la comunicación entre vehículos y el centro de control permite alertas inmediatas sobre incendios, detenciones, o objetos en la calzada; las curvas peligrosas y zonas de niebla frecuente, donde la alerta anticipada de condiciones adversas puede reducir la siniestralidad; y las intersecciones de alta complejidad, donde la coordinación entre vehículos e infraestructura puede optimizar el flujo. En estas zonas, el concesionario podría instalar RSU como una inversión de preparación para el futuro, ofreciendo en el corto plazo un servicio premium a flotas específicas —emergencias, transporte de carga de alto valor, flotas corporativas— que voluntariamente equipen sus vehículos con unidades embarcadas.

Este enfoque de "capacidad reservada" minimiza el riesgo financiero a corto plazo, preserva la opción de explotación futura, y alinea la inversión con la evolución tecnológica del mercado automotriz y la regulación colombiana.

---

## 5. TECNOLOGÍAS DE INFRAESTRUCTURA DE CARGA PARA VEHÍCULOS ELÉCTRICOS

### 5.1 Contexto de aplicabilidad en concesiones viales

La instalación de infraestructura de carga para vehículos eléctricos —electrolineras— en corredores viales es una tendencia que ha demostrado viabilidad comercial en múltiples jurisdicciones. A diferencia de otras tecnologías emergentes, las electrolineras no dependen de una penetración masiva previa en el parque automotor para ser viables: cada evento de carga es una transacción comercial independiente, y su modelo de negocio puede evaluarse con los métodos financieros convencionales de punto de equilibrio. Las áreas de servicio de las autopistas son emplazamientos naturales para electrolineras porque los usuarios de vehículos eléctricos necesitan cargar durante los viajes de larga distancia, y el tiempo de carga (15-30 minutos con tecnología rápida) coincide con el tiempo de descanso del usuario.

### 5.2 Proyectos de referencia y modelos de aplicación

En Chile, la concesionaria de la Ruta 68 ha instalado electrolineras en sus áreas de servicio, operándolas como parte de su modelo de negocio. La concesión Vespucio Norte Express, también en Chile, ha desplegado estaciones de carga rápida en puntos estratégicos. En Portugal, la concesionaria Brisa ha integrado una red de electrolineras en sus áreas de servicio, operando algunas directamente y arrendando espacio a operadores especializados en otras. En España, la concesionaria Abertis ha incorporado electrolineras en múltiples áreas de servicio como parte de su estrategia de diversificación de ingresos. En Italia, Autostrade per l'Italia está expandiendo su red de carga como parte de su plan de recuperación. En Estados Unidos, Electrify America opera una red de carga rápida en corredores interestatales, con un modelo de ubicación en corredores de alta circulación que replica la lógica de las concesiones viales.

Estos proyectos demuestran que existen múltiples modelos de aplicación: operación directa por el concesionario, arrendamiento de espacio a operadores especializados, joint venture compartido, o servicio premium de alta potencia para flotas comerciales. Ningún modelo es inherentemente superior: la elección depende de la estrategia de riesgo del concesionario, sus capacidades operativas, y el marco regulatorio local.

### 5.3 Aplicabilidad al corredor Chía-Girardot

El corredor Chía-Girardot presenta condiciones particularmente favorables para la evaluación de electrolineras como servicio complementario. Colombia posee una matriz energética predominantemente hidroeléctrica (más del 70%), lo que convierte a la energía suministrada en un producto de baja huella de carbono, diferenciador comercialmente atractivo. El gobierno colombiano, a través de la Ley de Transición Energética de 2021, impulsa la electromovilidad. La Resolución 181495 de 2020 del MinMinas establece el marco regulatorio para la instalación y operación de electrolineras. La Resolución CREG 030 de 2018 permite el autoconsumo y la venta de excedentes de energía a la red, lo que habilita a la concesión a generar ingresos no solo por la venta directa de carga, sino también por la venta de energía fotovoltaica excedente.

El corredor tiene múltiples áreas de servicio potenciales donde pueden evaluarse estaciones de carga rápida. Dado que la concesión opera bajo modelo 5G sin peajes, los ingresos por electrolineras pueden constituir una fuente de compensación parcial del flujo de caja, diversificando la dependencia del pago por disponibilidad de la vía. Adicionalmente, el transporte público de Bogotá está en proceso de electrificación de flotas de buses, lo que generará una demanda de carga en los corredores de acceso a la ciudad que puede ser atendida por las electrolineras del concesionario, si éste decide incluirlas en su oferta.

El concesionario podría evaluar la instalación de paneles solares en techos de áreas de servicio y estaciones de carga, generando energía para autoconsumo y vendiendo excedentes a la red, dentro del marco de la CREG. Esta integración de generación, almacenamiento y carga —conocida como estación de carga solar— es una configuración que ya opera en múltiples concesiones europeas y que el concesionario de Chía-Girardot podría considerar como una opción de diferenciación.

---

## 6. TECNOLOGÍAS DE GESTIÓN DE DEMANDA Y TARIFICACIÓN DIFERENCIADA

### 6.1 Contexto de aplicabilidad en corredores con alta variabilidad de tráfico

La gestión de la demanda del corredor —entendida como la capacidad de influir en los patrones de uso de la vía para optimizar el nivel de servicio— es una función ITS que puede mejorar la prestación sin requerir inversión en capacidad física adicional. El corredor Chía-Girardot conecta Bogotá con el sur del país, y los patrones de tráfico muestran horas pico bien definidas: flujo predominante hacia Bogotá en las mañanas, y hacia el sur en las tardes. Esta asimetría horaria crea condiciones donde la congestión en horas pico reduce el nivel de servicio para todos los usuarios, mientras que en horas valle la capacidad de la vía está subutilizada.

La tecnología ITS ofrece herramientas para gestionar esta variabilidad: la tarificación diferenciada por horario, los carriles de alta ocupación, la información en tiempo real sobre tiempos de viaje, y los sistemas de navegación optimizada que desvían tráfico hacia rutas alternas. Estas herramientas no son nuevas: operan en múltiples ciudades y corredores desde hace décadas, con efectos medibles en la reducción de congestión y la mejora del nivel de servicio.

### 6.2 Proyectos de referencia y mecanismos de gestión de demanda

Singapur opera desde 1998 el sistema ERP (Electronic Road Pricing), donde las tarifas varían cada media hora según el nivel de congestión medido en tiempo real, demostrando una reducción sostenida del tráfico en zonas de aplicación del 20-25% durante horas pico. Londres implementó en 2003 el Congestion Charge, una tarifa por ingreso a la zona central que, aunque no varía por hora, estableció el precedente de cobrar por el uso del espacio vial con fines de gestión de demanda. Estocolmo y Gotemburgo, en Suecia, operan desde 2007 y 2013 respectivamente sistemas de peaje por hora, donde las tarifas en horas pico son significativamente mayores, generando una reducción del tráfico del 20-30% en períodos de mayor demanda. Milán implementó desde 2012 el Area C, una tarifa de ingreso a la zona central que varía según las emisiones del vehículo, combinando gestión de demanda con política ambiental.

Estos proyectos demuestran que la gestión de demanda no es una teoría: es una política de transporte madura con efectos verificables. Sin embargo, ninguno de estos modelos es directamente transferible a Colombia sin adaptación regulatoria. La Ley 1682 de 2013 y la regulación de la ANI establecen que la tarificación de peajes requiere aprobación de la autoridad concedente, y el modelo 5G del corredor Chía-Girardot no contempla peaje tradicional como fuente de ingresos.

### 6.3 Aplicabilidad al corredor Chía-Girardot

Para el corredor Chía-Girardot, la gestión de demanda no debe concebirse como un mecanismo de cobro directo, sino como una herramienta de optimización del nivel de servicio. El concesionario podría evaluar mecanismos de tarificación diferenciada por horario para servicios específicos —por ejemplo, carriles de alta velocidad, carriles exclusivos para vehículos eléctricos, o acceso prioritario a zonas de servicio— si el marco contractual y regulatorio lo permite. Estos mecanismos requerirían una modificación del contrato de concesión, negociada con la ICCU y la ANI, que defina los términos de la tarificación, los beneficios para los usuarios, y la distribución de ingresos.

Alternativamente, el concesionario podría implementar sistemas de información en tiempo real que incentiven el cambio de horario de viaje sin requerir tarificación. Paneles de mensaje variable (VMS) que informen sobre tiempos de viaje en horas pico vs. horas valle, aplicaciones móviles que sugieran horarios de salida optimizados, y programas de incentivos para usuarios frecuentes que viajen en horas valle, son herramientas de gestión de demanda que no requieren cobro directo y que pueden mejorar el nivel de servicio para todos los usuarios del corredor.

El concesionario también podría ofrecer "pases mensuales" a usuarios frecuentes del corredor —residentes de Chía, Cota, Girardot, y otros municipios del corredor— con tarifas planas que incentiven la fidelización y generen un flujo de ingresos predecible. Este modelo, ya probado en concesiones chilenas y españolas, convierte la gestión de demanda en un servicio de valor para el usuario, no en una restricción.

---

## 7. TECNOLOGÍAS DE ANALÍTICA DE DATOS Y GENERACIÓN DE INFORMACIÓN

### 7.1 Contexto de aplicabilidad: el dato como herramienta de gestión

La operación de una concesión vial genera, de manera inherente, grandes volúmenes de datos: velocidades, flujos, tipos de vehículos, patrones horarios, incidentes, condiciones climáticas, y tiempos de recorrido. En el modelo tradicional, estos datos se utilizan exclusivamente para la gestión operativa del corredor y para los reportes regulatorios que exige la autoridad. Sin embargo, la tecnología ITS permite que estos datos sean procesados, analizados y transformados en información de valor para múltiples actores: el propio concesionario, los usuarios del corredor, las autoridades de transporte, las empresas de logística, y las aseguradoras.

Es fundamental establecer que la soberanía del dato en Colombia es del Estado. El Decreto 2060 de 2015 establece que la información capturada por los dispositivos ITS es un activo de utilidad pública, y el concesionario es su custodio técnico, no su propietario. Cualquier uso comercial de los datos requiere un acuerdo con la autoridad concedente que defina los términos de anonimización, los beneficios económicos, y los mecanismos de auditoría. Este marco no es una restricción: es una condición de operación que el concesionario debe incorporar en su diseño de negocio desde el inicio.

### 7.2 Tecnologías de procesamiento y proyectos de referencia

El mercado de datos de movilidad opera desde hace más de una década con múltiples actores. INRIX, con sede en Estados Unidos, provee datos de tráfico en tiempo real para aplicaciones de navegación y fabricantes de vehículos. HERE Technologies, con sede en los Países Bajos, es uno de los principales proveedores globales de mapas y datos de tráfico. TomTom, también de los Países Bajos, provee mapas y telemática a empresas de tecnología y transporte. Waze, propiedad de Google, opera un modelo de crowdsourcing donde los usuarios reportan condiciones de tráfico en tiempo real, generando una base de datos que se comparte con gobiernos para planificación urbana. Estas empresas demuestran que existe un mercado comercial para datos de movilidad, pero operan bajo marcos regulatorios de sus países de origen que no son directamente transferibles a Colombia.

### 7.3 Aplicabilidad al corredor Chía-Girardot

Para el corredor Chía-Girardot, la analítica de datos puede ser una herramienta de mejora de la prestación del servicio en múltiples dimensiones. El concesionario puede utilizar datos de flujo y velocidad para optimizar la gestión del tráfico en tiempo real, anticipando congestión y ajustando señalización dinámica antes de que se formen cuellos de botella. Los datos de incidentes pueden alimentar algoritmos de predicción que identifiquen tramos de alta siniestralidad y sugieran intervenciones preventivas. Los datos de tiempos de recorrido pueden ser publicados a los usuarios mediante paneles de mensaje variable y aplicaciones móviles, mejorando la experiencia de viaje y la percepción del servicio.

La comercialización de datos agregados —siempre bajo acuerdo con la autoridad y cumpliendo la Ley 1581 de 2012— puede ser una fuente de ingresos adicional. Datos anonimizados de flujos, velocidades y tiempos de recorrido tienen valor para aplicaciones de navegación, plataformas de logística, y gobiernos municipales para planificación urbana. El concesionario podría estructurar un modelo de Data as a Service (DaaS) donde los datos agregados del corredor se comercializan bajo licencia, generando ingresos recurrentes sin comprometer la privacidad de los usuarios.

La aplicación propia del concesionario puede operar bajo un modelo de información básica gratuita —tiempos de viaje, incidentes, condiciones climáticas— e información premium por suscripción —rutas optimizadas, alertas de congestión, disponibilidad de electrolineras— generando ingresos directos del usuario y, simultáneamente, enriqueciendo la base de datos propia del concesionario para mejorar la gestión del corredor.

---

## 8. TECNOLOGÍAS DE SEGURIDAD VIAL Y ANALÍTICA AVANZADA

### 8.1 Contexto de aplicabilidad: la seguridad como eje de la concesión 5G

La protección de la vida es el eje central del modelo de concesión 5G en Colombia, y la tecnología ITS es una herramienta fundamental para materializar este compromiso. La analítica avanzada —inteligencia artificial aplicada a video, sensores, y datos de tráfico— permite detectar incidentes automáticamente, identificar comportamientos de riesgo, y predecir condiciones de congestión antes de que se materialicen. Esta tecnología no es experimental: está operando en múltiples corredores globales desde hace años, con efectos medibles en la reducción de tiempos de respuesta y la prevención de accidentes.

### 8.2 Proyectos de referencia y tecnologías disponibles

En Austria, la concesionaria ASFINAG opera un sistema de detección automática de incidentes con analítica de video en 2.200 kilómetros de autopistas, reduciendo los tiempos de respuesta de emergencia en un 30-40%. En Australia, el estado de Victoria ha desplegado cámaras con inteligencia artificial para detectar conductas de riesgo —uso de teléfono móvil, no uso de cinturón— generando datos para política pública. En Inglaterra, National Highways utiliza sistemas de IA para detección de incidentes y gestión de tráfico. En Colombia, los proyectos Autopista al Mar 1 y Vías del Nus han integrado plataformas de gestión de tráfico con capacidades de analítica de video, operando en túneles y corredores de alta siniestralidad. En Estados Unidos, múltiples corredores inteligentes operan sistemas de detección de peatones, animales, y objetos en la vía mediante IA.

Estos proyectos demuestran que la analítica avanzada de seguridad es una tecnología madura (TRL 9) con múltiples aplicaciones: detección automática de incidentes (accidentes, vehículos detenidos, objetos en calzada), clasificación automática de vehículos (tipo, ejes, dimensiones), detección de intrusos (peatones, animales, vehículos en contravía), análisis predictivo de congestión (algoritmos que anticipan cuellos de botella 15-30 minutos antes), y mantenimiento predictivo (análisis de datos de sensores para anticipar fallas electromecánicas).

### 8.3 Aplicabilidad al corredor Chía-Girardot

El corredor Chía-Girardot, con sus 306 kilómetros y múltiples túneles, presenta condiciones donde la analítica avanzada de seguridad tiene un impacto directo en la siniestralidad y en los costos operativos. Los túneles requieren monitoreo constante de incendios, detenciones, y objetos; la vía arterial de 158 km presenta zonas de niebla, curvas peligrosas, y cruces de fauna; las vías colectoras de 148 km tienen alta interacción con tráfico local, peatones, y ciclistas. En este contexto, la analítica de video no es un lujo tecnológico: es una herramienta de reducción de riesgo contractual que puede mejorar la disponibilidad de la vía y reducir los costos de atención de incidentes.

El concesionario podría evaluar la instalación de sistemas de detección automática de incidentes en túneles y zonas críticas del corredor, no como una obligación, sino como una inversión que reduce los costos operativos y mejora el nivel de servicio. La detección automática permite que el centro de control reciba alertas sin depender de la observación manual de operadores, reduciendo los tiempos de respuesta y los costos de personal. La clasificación automática de vehículos genera datos estadísticos precisos para planificación de mantenimiento, permitiendo al concesionario anticipar el deterioro del pavimento y programar intervenciones preventivas que eviten cierres de vía y multas por incumplimiento de disponibilidad.

El concesionario también podría ofrecer, como servicio opcional, monitoreo de seguridad en tiempo real para flotas comerciales que circulan por el corredor. Este servicio, ya probado en corredores europeos, consiste en proporcionar alertas automáticas sobre condiciones de riesgo —niebla, congestionamiento, incidentes— y generar informes de seguridad para la gestión de flotas. Las aseguradoras, a su vez, podrían adquirir datos anonimizados de incidentes y patrones de riesgo para modelado de primas, siempre bajo los límites de la Ley 1581 de 2012 y con el consentimiento de los usuarios.

---

## 9. TECNOLOGÍAS DE EFICIENCIA ENERGÉTICA Y GENERACIÓN RENOVABLE

### 9.1 Contexto de aplicabilidad: la energía como costo y como oportunidad

Las concesiones viales consumen energía significativa en alumbrado de túneles, operación de centros de control, ventilación, paneles de mensaje variable, y sistemas de telecomunicaciones. La transición hacia tecnologías de eficiencia energética y generación renovable no responde únicamente a una obligación ambiental: responde a una reducción de costos operativos y, en algunos casos, a una oportunidad de ingresos adicionales. En un contrato 5G donde los ingresos están atados a la disponibilidad de la vía y a la calidad del servicio, cualquier reducción de costos operativos mejora directamente el margen financiero del concesionario.

### 9.2 Tecnologías disponibles y proyectos de referencia

El alumbrado LED en túneles reduce el consumo entre un 40% y un 60% comparado con iluminación tradicional de sodio o halógena, y además ofrece una vida útil superior (50.000-100.000 horas vs. 15.000-20.000 horas), reduciendo costos de mantenimiento. Los paneles solares en techos de áreas de servicio y estaciones de peaje generan energía para autoconsumo, reduciendo la factura eléctrica y, en jurisdicciones con regulación adecuada, permitiendo la venta de excedentes a la red. La ventilación inteligente en túneles —mediante jet fans controlados por sensores de CO y visibilidad, en lugar de operar en horarios fijos— reduce el consumo energético en un 20-30%. Los sistemas de respaldo energético con baterías y paneles solares permiten la operación off-grid en zonas remotas o durante fallas de la red, aumentando la resiliencia operativa.

En Chile, la Ruta 68 ha instalado paneles solares en áreas de servicio y ha migrado su alumbrado de túneles a LED, reduciendo el consumo energético en un 40-60%. En Portugal, Brisa ha migrado a alumbrado LED en toda su red y ha instalado paneles solares en múltiples emplazamientos. En España, Abertis ha incorporado paneles solares en techos de áreas de servicio y estaciones de peaje. En Italia, Autostrade per l'Italia ha establecido un compromiso de carbon neutrality en sus operaciones, incluyendo eficiencia energética y generación renovable. En el Reino Unido, National Highways opera el programa Net Zero Highways, orientado a alcanzar neutralidad de carbono en la operación de la red de autopistas.

### 9.3 Aplicabilidad al corredor Chía-Girardot

El corredor Chía-Girardot tiene múltiples túneles y áreas de servicio donde la migración a alumbrado LED genera ahorros inmediatos y medibles. La instalación de paneles solares en techos de áreas de servicio, y potencialmente en taludes del corredor donde la geografía y la exposición solar lo permitan, genera energía para autoconsumo. La Resolución CREG 030 de 2018 permite el autoconsumo y la venta de excedentes a la red, lo que significa que el concesionario puede generar ingresos adicionales por la energía fotovoltaica que no consume, si decide invertir en generación propia.

El concesionario podría también evaluar la ventilación inteligente en túneles como una inversión de eficiencia. Los túneles del corredor requieren ventilación constante por seguridad, pero los sistemas tradicionales operan en horarios fijos, consumiendo energía incluso cuando no hay tráfico. Los sistemas de ventilación por demanda, que activan los jet fans solo cuando los sensores detectan niveles de CO o partículas que superan los umbrales de seguridad, reducen el consumo energético significativamente sin comprometer la seguridad. Esta tecnología, ya operativa en túneles europeos, es una opción que el concesionario podría considerar como parte de su estrategia de reducción de costos operativos.

Adicionalmente, el concesionario podría posicionarse comercialmente como "corredor sostenible" o "corredor verde", diferenciador que tiene valor para flotas corporativas con compromisos de reducción de carbono. Colombia tiene un mercado de carbono regulado (Resolución 1447 de 2017 del MinAmbiente), lo que permite que la concesión certifique sus reducciones de emisiones y, eventualmente, venda créditos de carbono si el mercado se desarrolla lo suficiente durante la vigencia de la concesión.

---

## 10. TECNOLOGÍAS DE SERVICIOS DIGITALES AL USUARIO

### 10.1 Contexto de aplicabilidad: la experiencia del usuario como indicador de calidad

El usuario de autopistas del siglo XXI espera información en tiempo real sobre su recorrido, alternativas de ruta ante incidentes, disponibilidad de servicios en el corredor, capacidad de pago digital, y asistencia inmediata en caso de emergencia. Esta expectativa no es una moda: es una demanda de mercado que las concesiones más avanzadas ya están atendiendo mediante aplicaciones móviles propias, plataformas de información, y servicios integrados que transforman la experiencia de viaje. Para una concesión 5G, donde la calidad del servicio es un indicador contractual medible, la satisfacción del usuario es un factor directo de cumplimiento y de reputación.

### 10.2 Tecnologías disponibles y proyectos de referencia

En Chile, múltiples concesionarias operan aplicaciones móviles propias que proporcionan información de tráfico en tiempo real, estado de electrolineras, condiciones de túneles, y alertas de incidentes. En España, concesionarias operan apps con funcionalidades de navegación específica del corredor, pago de peaje integrado, y reserva de servicios en áreas de servicio. En Portugal, Brisa opera una app con información de tráfico, pago de peaje, y servicios de asistencia. En Estados Unidos, Electrify America ofrece una app que muestra la disponibilidad de cargadores en tiempo real, permite la reserva, y gestiona el pago. Estas aplicaciones no son solo herramientas de información: son plataformas de generación de datos, fidelización de usuarios, y venta de servicios adicionales.

### 10.3 Aplicabilidad al corredor Chía-Girardot

El concesionario de Chía-Girardot podría evaluar el desarrollo de una aplicación móvil propia que opere como un canal de servicio al usuario y como una herramienta de gestión de la demanda. Las funcionalidades básicas —tiempos de viaje en tiempo real, alertas de incidentes, estado de electrolineras, condiciones climáticas del corredor, ubicación de áreas de servicio— pueden ofrecerse gratuitamente, generando tráfico de usuarios y datos de comportamiento que el concesionario utilice para optimizar la gestión del corredor. Las funcionalidades premium —rutas optimizadas que evitan congestión, reserva de electrolinera con garantía de disponibilidad, alertas de seguridad personalizadas, y acceso a información de origen-destino para planificación— pueden ofrecerse por suscripción mensual o pago por uso, generando ingresos directos.

La app también puede integrar un servicio de asistencia vial digital: un botón de SOS que, al ser activado, envía la geolocalización precisa del usuario al centro de control de la concesión, que coordina automáticamente la respuesta de grúas, ambulancias, o policía. Este servicio puede operarse gratuitamente para usuarios registrados —como herramienta de fidelización y diferenciación del servicio— o puede ser ofrecido a aseguradoras como un servicio de respuesta de emergencia integrado.

El concesionario podría también integrar su app con plataformas de movilidad existentes en Bogotá (TransMilenio, apps de transporte) y Girardot, posicionándose como un nodo de información dentro del ecosistema de movilidad regional. Esta integración no requiere que el concesionario desarrolle toda la plataforma: puede operar mediante APIs de datos que el concesionario suministra a terceros, generando ingresos por licencia de datos y aumentando la visibilidad del corredor en el ecosistema digital de movilidad.

---

## 11. TECNOLOGÍAS DE LOGÍSTICA INTELIGENTE Y CONTROL DE CARGA

### 11.1 Contexto de aplicabilidad: el corredor como plataforma de movilidad de carga

Las autopistas no transportan solo personas: transportan carga. En un corredor como Chía-Girardot, con un TPDA de 40.000 vehículos, una proporción significativa del tráfico corresponde a vehículos de carga: camiones, tractocamiones, vehículos de reparto, y flotas de transporte logístico. La gestión inteligente de esta carga —su peso, sus dimensiones, su ruta, y su impacto en la infraestructura— es una función ITS que puede mejorar la prestación del servicio para todos los usuarios del corredor, porque los vehículos pesados son el principal factor de deterioro del pavimento y una fuente significativa de congestión cuando circulan por vías no diseñadas para su capacidad.

### 11.2 Tecnologías disponibles y proyectos de referencia

El pesaje en movimiento (Weigh-in-Motion, WIM) permite pesar vehículos mientras circulan, sin detenerlos, clasificando automáticamente su número de ejes y comparando el peso contra límites regulatorios. Esta tecnología opera en la autopista Palmillas–Apaseo en México, en múltiples concesiones en Chile, y en corredores de Europa y Estados Unidos. En Colombia, el Sistema de Autocontrol de Vehículos (SACV) implementado por el MinTransporte ya opera en corredores nacionales con esta tecnología. El reconocimiento de placas (LPR) aplicado a vehículos de carga permite el control de acceso a zonas restringidas, el rastreo de flotas, y la generación de matrices de movimiento de carga. Las cámaras de inspección de carga permiten verificar visualmente la carga sin detener el vehículo, tecnología que se utiliza en corredores de Europa y Estados Unidos para la detección de mercancías peligrosas o sobredimensionadas.

### 11.3 Aplicabilidad al corredor Chía-Girardot

El concesionario de Chía-Girardot podría evaluar la instalación de estaciones de pesaje en movimiento en puntos estratégicos de la vía arterial y las colectoras, no solo para cumplir con funciones de fiscalización que pueden ser contratadas por el MinTransporte o la ANSV, sino para generar datos de carga que alimenten la planificación de mantenimiento. Conocer con precisión el volumen, el peso, y la distribución de la carga que circula por el corredor permite al concesionario anticipar el desgaste del pavimento, programar intervenciones preventivas, y negociar con la autoridad concedente una tarificación de disponibilidad que refleje el uso real de la infraestructura. Este dato también es un insumo valioso para la autoridad, porque permite una fiscalización basada en evidencia en lugar de estimaciones.

Las áreas de servicio del corredor pueden ser evaluadas como emplazamientos para mini-hubs logísticos de última milla, especialmente en municipios de tamaño medio donde la distribución de carga desde centros urbanos grandes es costosa. El concesionario podría arrendar espacio a operadores logísticos o, en un modelo más ambicioso, operar directamente un servicio de transbordo: camiones grandes dejan la carga en el área de servicio, y vehículos menores distribuyen en el municipio final. Este modelo, ya explorado en Europa, tiene potencial en el contexto colombiano donde la logística de última milla enfrenta costos crecientes y donde la proximidad del corredor a múltiples municipios (Chía, Cota, Siberia, Girardot, entre otros) crea una oportunidad de distribución eficiente.

El concesionario también podría ofrecer un servicio de monitoreo de flotas comerciales que circulan por el corredor: informes de tiempos de recorrido, eficiencia, cumplimiento de rutas, y alertas de desviación. Este servicio, bajo modelo de suscripción mensual por flota, genera ingresos recurrentes y fideliza a los operadores logísticos como usuarios regulares del corredor.

---

## 12. CONCLUSIONES: HACIA UN MODELO DE PRESTACIÓN DEL SERVICIO 5G CON TECNOLOGÍA ABIERTA

El proyecto APP Chía-Girardot no debe concebirse como una infraestructura de concreto y asfalto con tecnología adicional, sino como una plataforma de prestación del servicio público de movilidad donde la tecnología ITS es una herramienta —entre muchas— para cumplir con los resultados contractuales: protección de la vida, eficiencia operativa, disponibilidad de la vía, y satisfacción del usuario. Las tecnologías presentadas en este capítulo no son obligatorias, ni excluyentes, ni cerradas. Son opciones que el futuro concesionario podrá evaluar, combinar, o descartar, según su estrategia de negocio, su apetito de riesgo, y las condiciones que defina la autoridad concedente en el pliego de condiciones.

La neutralidad tecnológica debe ser el principio rector. La autoridad debe definir los resultados esperados —reducción de siniestralidad en porcentajes medibles, nivel de servicio en índices de congestión, disponibilidad de la vía en porcentajes de tiempo, información al usuario en formatos accesibles— sin prescribir los medios. El concesionario, a su vez, debe proponer las tecnologías que considere más eficientes, asumiendo el riesgo de su elección y garantizando la interoperabilidad, la soberanía del dato, y la reportabilidad a las autoridades de IVC.

La estrategia de implementación debe ser faseada. En una primera fase (años 1-5), el concesionario puede enfocarse en tecnologías de alta madurez y bajo riesgo tecnológico: alumbrado LED en túneles, paneles solares para autoconsumo, electrolineras en áreas de servicio (bajo modelo de arrendamiento o joint venture), y sistemas de detección automática de incidentes en zonas críticas. En una segunda fase (años 5-10), puede expandir hacia monetización de datos agregados, servicios de seguridad para flotas, y evaluación de tarificación diferenciada si el marco regulatorio lo permite. En una tercera fase (años 10-25), puede activar capacidades de reserva: movilidad conectada si el mercado automotriz lo justifica, integración multimodal si el ecosistema de movilidad se consolida, y generación de energía a gran escala si el mercado de carbono se desarrolla.

Es imperativo reconocer que la viabilidad de cada tecnología en el contexto específico del corredor Chía-Girardot depende de variables que no pueden ser asumidas: la demanda real de usuarios, la evolución del marco regulatorio colombiano, la competencia de otros corredores y servicios, y las condiciones macroeconómicas durante la vigencia de la concesión. La viabilidad de las electrolineras, por ejemplo, depende directamente de la tasa de penetración de vehículos eléctricos en Colombia. La movilidad conectada depende de la evolución del parque automotor y de la regulación. El mercado de carbono es aún incipiente. Por tanto, este capítulo no debe interpretarse como una proyección de ingresos, sino como un mapa de posibilidades que el concesionario explorará con rigor técnico en su fase de estructuración de la oferta.

Finalmente, la soberanía del dato es el eje transversal de todas las tecnologías. El Decreto 2060 de 2015 establece que la información generada por los ITS es un activo de utilidad pública. El concesionario es el custodio técnico, no el propietario. Cualquier uso comercial de los datos requiere un acuerdo contractual con la autoridad que defina la titularidad, la anonimización, los beneficios económicos, y la auditoría. Este marco no es una restricción: es una condición de operación que el concesionario debe incorporar en su diseño de negocio desde el inicio, garantizando que la tecnología no sea una isla de información, sino un nodo interoperable de la red nacional de movilidad inteligente.

---

**Documento de Orientación para la Estructuración de la Concesión APP Chía-Girardot**
**Fecha:** Junio 2026
**Estado:** Borrador para revisión
**Nota metodológica:** Toda la información proviene de fuentes públicas verificables. No se incluyen datos inventados ni proyecciones no confirmadas. Las tecnologías presentadas son opciones que el futuro concesionario podrá evaluar; no son obligatorias ni excluyentes.
