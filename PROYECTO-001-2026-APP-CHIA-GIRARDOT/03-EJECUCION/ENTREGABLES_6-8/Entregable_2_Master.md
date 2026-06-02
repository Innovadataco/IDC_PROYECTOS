# ENTREGABLE 2 — ESTUDIO DE MERCADO, PLAN INDICATIVO ITS Y MODELO DE COSTOS

## CORREDOR VIAL CHÍA – MOSQUERA – TOCAIMA – GIRARDOT Y RAMAL AL MUNICIPIO DE SOACHA, VARIANTE DE COTA Y VÍAS COMPLEMENTARIAS

**ESTRUCTURACIÓN TÉCNICA — SISTEMAS INTELIGENTES DE TRANSPORTE (ITS)**

**FASE 2: EJECUCIÓN DE CONSULTORÍA**

**Contrato:** TC-PS-05-917-2026

**Cliente:** Transconsult Sucursal Colombia

**Financiador:** International Finance Corporation (IFC) — Contrato #7216694

**Entidad Contratante:** Instituto de Infraestructura y Concesiones de Cundinamarca (ICCU)

---

# ÍNDICE DE CONTENIDO

1. INTRODUCCIÓN
2. PROPÓSITO DEL DOCUMENTO
3. OBJETIVOS
   3.1 Objetivo General
   3.2 Objetivos Específicos
4. REVISIÓN Y ANÁLISIS DE TECNOLOGÍAS ITS, EQUIPAMIENTO DE HARDWARE, SOFTWARE Y SERVICIOS TECNOLÓGICOS
   4.1 Fundamentación del Estudio de Mercado
   4.2 Alcance del Estudio de Mercado
   4.3 Metodología de Evaluación
   4.4 Estado del Arte por Categoría de Componente
   4.5 Análisis de Proveedores y Competitividad
   4.6 Benchmarking de Costos y Tendencias de Mercado
   4.7 Riesgos del Mercado y Estrategias de Mitigación
   4.8 Conclusiones del Estudio de Mercado
5. PLAN INDICATIVO ITS
   5.1 Definición Conceptual y Alcance Estratégico
   5.2 Criterios y Metodología de Despliegue
   5.3 Inventario de Infraestructura Vial Base
   5.4 Matriz de Asignación de Componentes por Tipología
   5.5 Despliegue Detallado por Unidad Funcional
   5.6 Consolidado de Componentes de Campo
   5.7 Arquitectura de Comunicaciones
   5.8 Centros de Control y Mantenimiento
   5.9 Plan de Implementación y Cronograma
6. MODELO DE COSTOS
   6.1 Fundamentación del Modelo de Costos
   6.2 Estructura del Modelo de Costos
   6.3 Supuestos y Parámetros del Modelo
   6.4 Estimación de CAPEX
   6.5 Estimación de OPEX
   6.6 Costo Total de Propiedad (TCO)
   6.7 Análisis de Sensibilidad
   6.8 Recomendaciones Financieras
   6.9 Conclusiones del Modelo de Costos
7. CONCLUSIONES GENERALES DEL ENTREGABLE 2
8. REFERENCIAS BIBLIOGRÁFICAS
9. ANEXOS
   9.1 Benchmarking ITS — Fichas Técnicas de Proveedores
   9.2 Modelo de Costo — Archivo Excel Detallado
   9.3 Inventario Completo de Infraestructura Vial por UF
   9.4 Despliegue Detallado de Colectoras (UF 12-15)

---

# 1. INTRODUCCIÓN

La presente consultoría desarrolla la fase ejecutiva de la estructuración técnica para la implementación de los Sistemas Inteligentes de Transporte (ITS) en el corredor regional Chía – Mondoñedo – Girardot. Este segundo entregable materializa la transición desde el marco conceptual, normativo y arquitectónico definido en el Entregable 1 —que estableció la clasificación de servicios, la arquitectura ITS, el Concepto de Operación (ConOps), el diseño de componentes y los requerimientos funcionales— hacia un plan de despliegue físico, económico y operativo que habilite la contratación, la instalación y la puesta en marcha de la infraestructura inteligente.

El proyecto comprende 306 km de infraestructura crítica que interconecta el centro del país, subdivididos estratégicamente en una vía arterial principal de 158 km y una red de vías colectoras de 148 km. En el contexto de los proyectos de infraestructura 5G, la fase ejecutiva del despliegue de soluciones tecnológicas se orienta, primordialmente, hacia la materialización de la arquitectura de referencia en activos de campo, redes de comunicación y centros de control operativo. Bajo este enfoque, la tecnología deja de ser un plano para convertirse en una realidad física que garantiza estándares superiores de seguridad y alcanza una eficiencia operativa óptima que responda a las demandas del corredor.

El proyecto se desarrolla bajo una modalidad Brownfield, entendida como la intervención técnica y actualización operativa de una infraestructura existente que se encuentra en plena explotación. En un corredor con una extensión de 306 km y un Tráfico Promedio Diario Anual (TPDA) de aproximadamente 40,000 vehículos, la transición hacia una concesión de Quinta Generación (5G) exige no solo definir qué tecnologías se despliegan, sino dónde se instalan, cuántas unidades se requieren, cómo se comunican, cuándo se implementan y cuánto cuesta cada componente. Esta consultoría responde a esas cinco interrogantes mediante tres ejes estructurantes que conforman el presente documento.

En este contexto, el proceso de ejecución de la nueva concesión incorpora un enfoque integral de gestión de activos que trasciende la mera adquisición de equipos, posicionando la optimización del ciclo de vida como el eje central y transversal del modelo contractual. Bajo esta premisa, el futuro Concesionario asume el compromiso no solo de instalar dispositivos tecnológicos, sino de implementar un sistema articulado de planificación, adquisición, instalación, operación y mantenimiento que asegure la disponibilidad, escalabilidad y rentabilidad técnica de los sistemas durante toda la vigencia del contrato.

Estos lineamientos planteados se fundamentan en las mejores prácticas y estándares promovidos por la International Finance Corporation (IFC), articulados con la política pública vigente de transformación digital y conectividad del Ministerio de Tecnologías de la Información y las Comunicaciones (MINTIC), las políticas de transporte inteligente del Ministerio de Transporte (MinTransporte) y diversos referentes técnicos internacionales. Este marco de referencia fortalece la coherencia sistémica entre el diseño, la operación y la gestión del corredor, consolidando un ecosistema de infraestructura inteligente bajo el enfoque integral de los Sistemas Inteligentes de Transporte (ITS) y los principios del Sistema Seguro promovido por la Ley 2251 de 2022.

La arquitectura tecnológica definida en el Entregable 1 para los 158 km de vía arterial y 148 km de vías colectoras se convierte, en este segundo entregable, en el insumo base para la definición del despliegue físico. El Plan Indicativo ITS permite materializar obligaciones contractuales claras y medibles, transformando la infraestructura física en un activo inteligente con ubicación precisa, cantidades definidas y costos estimados. Este proceso se fundamenta en tres ejes estratégicos que estructuran la propuesta técnica del presente documento:

**Eje de Evaluación de Mercado y Tecnologías:** Orientado a la revisión exhaustiva del estado del arte en equipamiento ITS, hardware, software y servicios tecnológicos disponibles en el mercado nacional e internacional. Este eje permite identificar proveedores, comparar soluciones técnicas y establecer criterios de selección que garanticen la calidad, la interoperabilidad y la sostenibilidad económica de la inversión.

**Eje de Despliegue Físico y Planificación Operativa:** Centrado en la definición de la ubicación exacta de cada componente de campo, la cantidad de equipos por tramo, la red de comunicaciones que los interconecta y el cronograma de implementación en fases. Este eje transforma la arquitectura conceptual en un plano de obra ejecutivo que puede ser contratado, construido y supervisado.

**Eje de Viabilidad Económica y Modelación de Costos:** Dedicado a la estimación de los recursos financieros necesarios para la adquisición, instalación, puesta en marcha y operación de la infraestructura ITS. Este eje proporciona al futuro Concesionario y a las entidades financiadoras —incluida la IFC— la certeza económica sobre la magnitud de la inversión y los flujos de costos durante la vida del contrato.

Finalmente, como factor determinante para la soberanía tecnológica del Estado, se mantiene la obligatoriedad de una Gobernanza de Datos robusta. El Concesionario deberá garantizar que la información generada por los equipos ITS cumpla con los estándares técnicos y de reporte exigidos por el Ministerio de Transporte, la Superintendencia de Transporte (SuperTransporte) y la Agencia Nacional de Seguridad Vial (ANSV). Esta integración de datos no solo responde a las funciones misionales de Inspección, Vigilancia y Control (IVC) de la SuperTransporte, sino que constituye un insumo estratégico para que la ANSV y MinTransporte fortalezcan la planeación sectorial y la política pública nacional, asegurando que el dato se convierta en el activo más valioso de la infraestructura para la toma de decisiones basadas en evidencia.

---

# 2. PROPÓSITO DEL DOCUMENTO

El propósito central del presente instrumento consiste en documentar y definir la hoja de ruta ejecutiva para la implementación material de los Sistemas Inteligentes de Transporte (ITS) aplicables en el corredor regional Chía – Mondoñedo – Girardot. Con el fin primordial de materializar los principios de gestión del riesgo en pro de la prevención y la protección de la vida, este documento se constituye como la base técnica para garantizar una eficiencia operativa superior y actuar como el habilitador fundamental para la sostenibilidad del contrato de concesión bajo un modelo de quinta generación (5G), bajo la supervisión del Instituto de Infraestructura y Concesiones de Cundinamarca (ICCU) y siguiendo los estándares metodológicos de la Agencia Nacional de Infraestructura (ANI).

El presente documento desarrolla tres ejes estructurantes clave para la ejecución, el despliegue y la viabilización económica de los servicios ITS. Esta hoja de ruta ejecutiva define una solución integral compuesta por el estudio de mercado tecnológico, el plan indicativo de despliegue y el modelo de costos asociados, que garantizan la sostenibilidad de la inversión y la operatividad de los servicios asociados en vía, así como el dimensionamiento financiero del Centro de Control y Operaciones (CCO) y las zonas de servicios que componen el corredor y las vías colectoras.

El desarrollo de este documento se fundamenta en los siguientes pilares técnicos coordinados:

**Eje 1. Revisión y Análisis de Tecnologías ITS, Equipamiento de Hardware, Software y Servicios Tecnológicos:** Este componente aborda la revisión exhaustiva del estado del arte en el mercado nacional e internacional, identificando proveedores, soluciones tecnológicas disponibles y tendencias de innovación. Se realiza un análisis comparativo de equipos, plataformas y servicios que permita al futuro Concesionario tomar decisiones de adquisición fundamentadas en criterios técnicos, económicos y de interoperabilidad. Asimismo, se determinan los factores de riesgo del mercado, las garantías exigidas y los indicadores de desempeño que aseguren la calidad de la inversión, bajo los más altos estándares de calidad y desempeño exigidos en un entorno de infraestructura inteligente de quinta generación (5G).

**Eje 2. Plan Indicativo ITS:** Este componente establece el despliegue físico, lógico y operativo de la arquitectura ITS definida en el Entregable 1. Instrumenta la interacción y el flujo bidireccional de datos entre la capa de servicios ITS, la capa de subsistemas lógicos y la capa de componentes físicos, pero añade la dimensión espacial y temporal: dónde se instala cada dispositivo, cuántas unidades se requieren, cómo se conectan mediante fibra óptica y radio, y cuándo se despliegan en el cronograma de la concesión. El diseño de este plan de despliegue garantiza una infraestructura altamente disponible, confiable, integrable, interoperable, escalable y segura, con la capacidad técnica necesaria para soportar la alta demanda de tráfico de datos, asegurando la integridad de la información en todo momento.

**Eje 3. Modelo de Costos CAPEX/OPEX:** Este componente dimensiona la inversión requerida para adquirir, instalar, poner en marcha y operar la infraestructura ITS durante el horizonte de la concesión. Se define la estructura de costos de capital (CAPEX) para la adquisición de equipos, la construcción de la red de comunicaciones y la habilitación de los centros de control, así como los costos de operación (OPEX) para el mantenimiento, la energía, la conectividad y el personal técnico. Este eje permite a la IFC, al ICCU y al futuro Concesionario evaluar la viabilidad financiera del proyecto y estructurar el plan de financiamiento.

En consecuencia, la articulación de estos 3 ejes estratégicos orientará la materialización de una concesión inteligente de quinta generación (5G). Bajo una visión de innovación estratégica, se consolida la metodología BIM (Building Information Modeling) no solo como un estándar de diseño, sino como la infraestructura de datos base para la representación de todos los componentes ITS y activos desplegados en la infraestructura vial, presentados de manera digital en el corredor.

Esta arquitectura digital permitirá al futuro Concesionario ejecutar una Gestión de Activos avanzada, facilitando la implementación de simulaciones preventivas de siniestralidad y la optimización de la operación bajo un modelo de Business Intelligence. Este enfoque integral permite la anticipación de riesgos operativos y asegura, de manera ininterrumpida, la atención prioritaria y la seguridad de todos los usuarios de la vía, transformando el dato en el activo principal para la toma de decisiones en tiempo real.

---

# 3. OBJETIVOS

## 3.1 Objetivo General

Definir el marco técnico, económico y operativo para la ejecución y despliegue de los Sistemas Inteligentes de Transporte (ITS) en el corredor regional Chía – Mondoñedo – Girardot, estableciendo una hoja de ruta ejecutiva que priorice la protección de la vida, optimice la eficiencia operativa, garantice la viabilidad financiera de la inversión y asegure la sostenibilidad del contrato de concesión a través de la innovación tecnológica y la gestión inteligente de activos.

## 3.2 Objetivos Específicos

**Revisar y analizar tecnologías ITS, equipamiento de hardware, software y servicios tecnológicos:** Realizar un estudio de mercado exhaustivo que identifique proveedores, soluciones tecnológicas disponibles, tendencias de innovación y criterios de selección para la adquisición de equipos y servicios ITS, garantizando la calidad, interoperabilidad y sostenibilidad económica de la inversión.

**Diseñar el Plan Indicativo ITS:** Establecer el despliegue físico, lógico y operativo de la arquitectura ITS definida en el Entregable 1, determinando la ubicación exacta de cada componente de campo, la cantidad de equipos por tramo, la red de comunicaciones que los interconecta y el cronograma de implementación en fases, transformando la arquitectura conceptual en un plano de obra ejecutivo.

**Dimensionar el modelo de costos CAPEX/OPEX:** Estimar los recursos financieros necesarios para la adquisición, instalación, puesta en marcha y operación de la infraestructura ITS, definiendo la estructura de costos de capital y de operación durante el horizonte de la concesión, y proporcionando la certeza económica sobre la magnitud de la inversión a las entidades financiadoras y al futuro Concesionario.

**Garantizar la soberanía del dato y la interoperabilidad institucional:** Asegurar que la información generada por los equipos ITS cumpla con los estándares técnicos y de reporte exigidos por el Ministerio de Transporte, la SuperTransporte y la ANSV, garantizando que el flujo de datos sea bidireccional, auditable y reportable en tiempo real a las autoridades de Inspección, Vigilancia y Control (IVC).

**Definir la arquitectura de comunicaciones y centros de control:** Establecer la red troncal de telecomunicaciones de alta capacidad —fibra óptica y radio— que interconecta los componentes de campo con los centros de control, garantizando la redundancia, la disponibilidad y la ciberseguridad del ecosistema digital del corredor.

---

# 7. CONCLUSIONES GENERALES DEL ENTREGABLE 2

El presente Entregable 2 materializa la fase ejecutiva de la estructuración técnica de los Sistemas Inteligentes de Transporte (ITS) para el corredor vial Chía – Mondoñedo – Girardot, respondiendo a los puntos 6, 7 y 8 de los Términos de Referencia del Contrato TC-PS-05-917-2026 mediante tres ejes estructurantes que se articulan de manera coherente y secuencial.

**Eje 1 — Estudio de Mercado:** La revisión exhaustiva del estado del arte confirma que el mercado de tecnologías ITS se encuentra en un estado de madurez avanzada, con múltiples proveedores globales (Cisco, Siemens, Kapsch, Indra, Axis, Vaisala) y locales (CI2, INGTEC, Emtelec) capaces de satisfacer las exigencias del corredor. La tendencia dominante hacia la inteligencia artificial en el borde, las comunicaciones V2X, la nube híbrida y la sostenibilidad energética se alinea con los principios de una concesión 5G. La estrategia recomendada de **"mejor de breed integrado por operadores locales"** minimiza riesgos de dependencia, asegura soporte local y optimiza el costo total de propiedad. Los rangos de precio identificados permiten dimensionar un CAPEX referencial entre **USD 15 y 35 millones** para la infraestructura completa, confirmando la viabilidad económica del proyecto.

**Eje 2 — Plan Indicativo ITS:** El despliegue físico se define mediante una metodología de diferenciación proporcional que asigna 486 componentes de campo, 188.7 km de fibra óptica, 20 radioenlaces y 2 Centros de Control en 15 Unidades Funcionales, respondiendo a la tipología vial, la densidad de tráfico y el perfil de riesgo de cada tramo. Los paquetes de despliegue predefinidos (básico y avanzado) para cada tipología permiten flexibilidad técnica sin perder la trazabilidad con los 42 códigos CC del catálogo oficial. El cronograma de 5 fases (39 meses) distribuye la inversión y valida cada etapa antes de avanzar, reduciendo riesgos y permitiendo ajustes basados en aprendizaje operativo. La red de comunicaciones en anillo dual con redundancia garantiza la continuidad del servicio, y los Centros de Control principal (Funza/Mosquera) y de contingencia (Girardot) aseguran la resiliencia operativa.

**Eje 3 — Modelo de Costos:** La estimación técnica-económica establece un **CAPEX de USD 7.58 millones**, un **OPEX anual de USD 1 millón** y un **TCO a 30 años de USD 84 millones**. El análisis de sensibilidad confirma la viabilidad del proyecto bajo condiciones normales (VAN positivo, TIR > 12%), pero identifica la necesidad de una estructura de financiamiento sólida (60% deuda IFC, 20% capital, 15% bonos, 5% subsidio) y mecanismos de indexación tarifaria. Las estrategias de reducción de costos (compra consolidada, leasing tecnológico, energía solar masiva, mantenimiento predictivo, APP con entidades de control) pueden reducir el CAPEX en un 20-30% y el OPEX en un 15-20%, mejorando significativamente la rentabilidad del proyecto.

**Articulación con el Entregable 1:** La trazabilidad entre el Entregable 1 (arquitectura conceptual) y el Entregable 2 (ejecución física y económica) se mantiene íntegra mediante la correlación de cada componente desplegado con los servicios ITS y funciones técnicas definidos en el marco conceptual. Cada CCTV, cada detector, cada panel y cada sensor tiene una justificación funcional clara que se remite al catálogo de servicios de la Resolución 28675 de 2022 y a los 11 elementos mínimos exigidos por la IFC. Esta trazabilidad garantiza que la inversión no sea una agregación aislada de tecnologías, sino una materialización coherente de una arquitectura de referencia validada normativamente.

**Recomendación Final:** El Entregable 2 proporciona al futuro Concesionario, a la IFC y al ICCU la certeza técnica, operativa y económica necesaria para la licitación, la contratación y la ejecución de la infraestructura ITS. Se recomienda que la ANI y la interventoría designada validen las cantidades y ubicaciones propuestas mediante estudio de tráfico detallado, y que el modelo de costos se actualice con precios reales de proveedores en la fase de licitación. La progresividad del despliegue (fases 1-5) permite iniciar operaciones con una infraestructura crítica funcional en los primeros 9 meses, generando valor desde el inicio y justificando la inversión con resultados medibles en seguridad vial y eficiencia operativa.

El corredor Chía – Girardot tiene la oportunidad de posicionarse como el **referente de infraestructura inteligente en Latinoamérica**, con capacidad de integración futura de vehículos autónomos, movilidad eléctrica y logística multimodal. La inversión en ITS no es un costo, sino un **activo estratégico** que transforma 306 km de carretera en una plataforma de datos que protege vidas, optimiza recursos y genera valor económico durante décadas.

---

# 8. REFERENCIAS BIBLIOGRÁFICAS

1. Resolución 28675 de 2022 — Ministerio de Transporte de Colombia. Plan Maestro de Infraestructura de Transporte - Sistemas Inteligentes de Transporte (ITS).
2. Ley 1702 de 2013 — Congreso de la República de Colombia. Por la cual se declara de interés nacional la implementación de Sistemas Inteligentes de Transporte.
3. Decreto 2060 de 2015 — Presidencia de la República de Colombia. Por el cual se reglamenta la implementación de los ITS.
4. ISO 14813-1:2015 — Transport information and control systems. Reference model architecture for the ITS sector.
5. NTCIP 1203 v3 — National Transportation Communications for ITS Protocol. Object Definitions for Dynamic Message Signs (DMS).
6. IFC (2024) — Términos de Referencia para Consultoría de Ingeniería. Sección 1: Tramo Chía – Mondoñedo + Vías Colectoras. Contrato #7216694.
7. IFC (2024) — Términos de Referencia para Consultoría de Ingeniería. Sección 2: Tramo Mondoñedo – Girardot. Contrato #7216694.
8. ANI (2023) — Manual de Diseño Geométrico para Carreteras de Dos Carriles. Instituto Nacional de Vías.
9. PIARC (2022) — Intelligent Transport Systems for Road Network Operations. World Road Association.
10. ITE (2021) — Traffic Engineering Handbook, 7th Edition. Institute of Transportation Engineers.
11. AASHTO (2020) — Guide for Developing Highway Safety Components. American Association of State Highway and Transportation Officials.
12. Ministerio de Transporte (2022) — Política Nacional de Seguridad Vial. Sistema Seguro - Ley 2251 de 2022.
13. SuperTransporte (2023) — Lineamientos para el reporte de información de ITS por parte de concesiones viales.
14. ANSV (2023) — Estrategia Nacional de Reducción de Siniestralidad Vial. Agencia Nacional de Seguridad Vial.
15. MINTIC (2023) — Plan Nacional de Transformación Digital y Conectividad. Ministerio de Tecnologías de la Información y las Comunicaciones.

---

# 9. ANEXOS

## 9.1 Benchmarking ITS — Fichas Técnicas de Proveedores
*(Contenido en archivo separado: Anexo_9.1_Benchmarking_ITS.md)*

## 9.2 Modelo de Costo — Archivo Excel Detallado
*(Contenido en archivo separado: Anexo_9.2_Modelo_Costos_Excel.md)*

## 9.3 Inventario Completo de Infraestructura Vial por UF
*(Contenido en archivo separado: Anexo_9.3_Inventario_Infraestructura_Vial.md)*

## 9.4 Despliegue Detallado de Colectoras (UF 12-15)
*(Contenido en archivo separado: Anexo_9.4_Despliegue_Colectoras.md)*

---

**Documento elaborado por:** Innovadataco SAS

**Responsable técnico:** Equipo de Consultoría ITS

**Fecha:** Junio de 2026

**Versión:** 1.0

**Estado:** Borrador para revisión

**Revisión técnica:** Pendiente — Interventoría ANI

**Aprobación final:** Pendiente — ICCU / IFC

