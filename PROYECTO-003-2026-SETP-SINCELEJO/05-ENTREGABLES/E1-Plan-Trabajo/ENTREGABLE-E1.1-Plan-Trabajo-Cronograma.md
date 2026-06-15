# ENTREGABLE 1.1 — PLAN DE TRABAJO Y CRONOGRAMA

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E1.1  
**Versión:** 2.0 — Reescritura argumentada y fluida  
**Fecha:** 15 de junio de 2026  
**Elaborado por:** ZEUS — InnovaDataCo  
**Revisión:** V2.0 — Borrador para validación del CEO

---

## RESUMEN EJECUTIVO

El presente documento establece el plan de trabajo y el cronograma de ejecución para la consultoría de estructuración de los componentes tecnológicos del Sistema Estratégico de Transporte Público de Sincelejo (SETP), contratada por Metro Sabanas S.A.S. Esta consultoría no se origina en un vacío institucional: el SETP Sincelejo acumula una historia tecnológica de más de una década que es indispensable comprender para estructurar adecuadamente los requerimientos técnicos de su proceso de contratación actual.

**Hallazgo principal:** El SETP Sincelejo cuenta con cuatro sistemas tecnológicos definidos desde 2015 —SRC, SGCF, SIU y SST— que fueron diseñados en un estudio de prefactibilidad, actualizados en una consultoría posterior (2022) e incorporados en un proceso de contratación con el Ministerio de Transporte (2023) que no llegó a adjudicarse. Esta consultoría de 2026, por tanto, no inventa tecnología nueva: valida, actualiza y estructura los sistemas existentes para que Metro Sabanas S.A.S. pueda lanzar un proceso de licitación robusto, fundamentado en documentación técnica coherente y alineada con la normativa colombiana de Sistemas Inteligentes de Transporte (ITS).

**Metodología:** El proyecto se ejecuta en tres fases —Inicio y Diagnóstico, Diseño Conceptual, y Análisis Tecnológico— con una duración de cuatro semanas y un valor de $39.000.000 COP. El producto final no es un sistema implementado, sino un **Estudio Previo ITS** que alimenta el proceso de contratación del componente tecnológico del SETP Sincelejo.

---

## 1. CONTEXTO DEL PROYECTO

### 1.1 El SETP Sincelejo: una historia tecnológica fragmentada

El Sistema Estratégico de Transporte Público de Sincelejo constituye la apuesta de la ciudad para transformar la movilidad urbana mediante un servicio de transporte estructurado, regulado y tecnológicamente habilitado. Sin embargo, el componente tecnológico de este sistema no ha logrado materializarse en infraestructura operativa pese a haber sido definido teóricamente desde 2015. Esta fragmentación histórica exige una consultoría que, antes de proponer nuevas especificaciones, comprenda qué se ha definido, qué se ha intentado contratar y por qué esos intentos no han concluido en sistemas operativos.

La historia tecnológica del SETP Sincelejo se puede trazar en cinco momentos clave. En **2015**, la Unión Temporal conformada por Steer Davies Gleave (consultora internacional especializada en transporte) y GSD+ (consultora colombiana) ejecutó el estudio de prefactibilidad del sistema. En ese documento se definieron los tres sistemas tecnológicos originales: el **Sistema de Recaudo Centralizado (SRC)**, que habilitaría el pago electrónico en buses mediante validadores y tarjetas sin contacto; el **Sistema de Gestión y Control de Flota (SGCF)**, que permitiría el rastreo GPS, la programación de rutas y la supervisión de la operación; y el **Sistema de Información al Usuario (SIU)**, que dotaría a los pasajeros de canales de información (aplicación móvil, portal web, pantallas en paraderos y call center). Junto con estos sistemas, se delinearon tres escenarios institucionales que definían quién operaría la tecnología: un escenario "base" donde un concesionario externo operaría el recaudo mientras Metro Sabanas operaba la gestión de flota y la información al usuario; un escenario de "socio tecnológico" donde un único concesionario operaría los tres sistemas; y un escenario de "operador recaudador" donde el operador de transporte asumiría la operación de los tres sistemas. Estos tres escenarios, definidos en 2015, siguen vigentes como marco de referencia institucional para la contratación actual.

En **2022**, la empresa **A4 Asociados SAS** ejecutó una consultoría de actualización del modelo de transporte bajo el contrato **CM-001-2022**. Esta consultoría no modificó la arquitectura tecnológica de 2015, pero actualizó los parámetros de demanda, la red de rutas y los indicadores de operación, manteniendo vigentes los tres sistemas originales. La consultoría de A4 Asociados, en ese sentido, representó una continuidad técnica: validó que los sistemas definidos en 2015 seguían siendo pertinentes para el modelo de transporte actualizado.

El momento más cercano a la implementación ocurrió en **2023**, cuando el **Ministerio de Transporte de Colombia** lanzó un proceso de contratación para el componente tecnológico del SETP Sincelejo. Este proceso definió una flota de **46 vehículos**, un plazo de **nueve meses** para la implementación y un pago condicionado a la validación de entregables. Fue en este proceso donde se agregó un cuarto sistema: el **Sistema de Seguridad de Transacciones (SST)**, encargado del cifrado de datos, la seguridad de comunicaciones y la auditoría de transacciones. Sin embargo, este proceso no llegó a adjudicarse, quedando los cuatro sistemas —SRC, SGCF, SIU, SST— en estado de diseño documentado pero no implementado.

Finalmente, en **2025**, Metro Sabanas S.A.S. lanzó una **Solicitud de Información (RFI)** que integra tres contratos: provisión de flota (vehículos), tecnología (software e infraestructura) y operación (servicios). Esta estructura no es una adquisición por lotes tradicional, sino una contratación integrada que permite a la empresa operadora proponer modelos donde un mismo proveedor asuma uno, dos o los tres contratos, o se asocie con otros proveedores para una oferta conjunta. Es en este contexto donde se enmarca la presente consultoría de **2026**: estructurar los requerimientos técnicos para que el RFI y la posterior Solicitud de Cotización (RFQ) cuenten con documentación robusta, fundamentada y alineada con la normativa colombiana.

### 1.2 Naturaleza de esta consultoría

Es fundamental clarificar que esta consultoría no implica la implementación, instalación, operación ni puesta en marcha de los sistemas tecnológicos. Su objetivo es estrictamente la **estructuración técnica**: revisar la documentación existente, definir la arquitectura conceptual, especificar los componentes de hardware y software, estructurar los requerimientos funcionales y no funcionales, y apoyar en la elaboración de los documentos de licitación (RFI y RFQ). El producto tangible es un **Estudio Previo ITS** que alimentará el proceso de contratación del componente tecnológico del SETP Sincelejo.

Esta delimitación de alcance es importante porque evita confusiones tanto con el cliente como con los posibles oferentes del proceso de contratación. Metro Sabanas S.A.S. no está contratando, a través de Innovadataco, la implementación de un sistema ITS: está contratando la elaboración de los documentos técnicos que permitirán, en una etapa posterior, contratar a un proveedor que sí implemente el sistema. Esta consultoría, en ese sentido, es un puente entre la historia tecnológica definida (2015-2023) y el proceso de contratación futuro (RFI/RFQ 2025-2026).

### 1.3 Marco normativo aplicable

El diseño y la especificación de los sistemas ITS del SETP Sincelejo deben alinearse con la normativa colombiana vigente. La principal referencia es la **Resolución 20203040034065 del Ministerio de Transporte (2020)**, que establece los estándares técnicos para los Sistemas Inteligentes de Transporte en Colombia. Esta resolución define los subsistemas ITS, los componentes de campo, los centros de control, las arquitecturas de comunicación y los requerimientos de interoperabilidad que deben cumplir los sistemas desplegados en el país. Adicionalmente, la **Resolución 20223040028675** del Ministerio de Transporte (2022) actualiza el Plan Maestro de ITS (PMITS), estableciendo prioridades y lineamientos para el despliegue de estos sistemas en corredores viales y sistemas de transporte público.

Esta normativa no es un mero formalismo administrativo: es la base técnica sobre la cual se construyen las especificaciones, los requerimientos y los criterios de evaluación de la contratación. Un Estudio Previo ITS que no esté alineado con la Resolución 20203040034065 correría el riesgo de ser rechazado en la revisión del Ministerio de Transporte o de generar sistemas que no sean interoperables con la red nacional de ITS.

---

## 2. METODOLOGÍA DE TRABAJO

### 2.1 Enfoque general

El proyecto sigue una metodología de consultoría especializada en Sistemas Inteligentes de Transporte (ITS), adaptada a la naturaleza de una estructuración técnica previa a la licitación. La metodología se fundamenta en tres principios: (1) **fidelidad documental**, es decir, no inventar sistemas ni datos que no estén en la documentación histórica del proyecto; (2) **trazabilidad normativa**, asegurando que cada especificación y requerimiento tenga una base en la Resolución 20203040034065 u otra normativa aplicable; y (3) **argumentación técnica**, presentando las decisiones de diseño con justificaciones claras, no como listas arbitrarias.

La metodología se organiza en tres fases secuenciales, cada una con objetivos definidos, actividades específicas y productos entregables. La duración total es de cuatro semanas, lo que implica una intensidad de trabajo alta y una coordinación estrecha entre el equipo de Innovadataco y el equipo técnico de Metro Sabanas S.A.S.

### 2.2 Fase 1: Inicio y Diagnóstico (Semana 1)

La primera fase tiene como propósito sentar las bases del proyecto mediante la revisión exhaustiva de la documentación histórica y el establecimiento de los mecanismos de gobierno del proyecto. Esta fase no es una mera formalidad administrativa: es el momento en que el equipo de consultoría se familiariza con la historia tecnológica del SETP Sincelejo, identifica los documentos clave, detecta inconsistencias o vacíos en la información disponible, y establece los canales de comunicación con el cliente.

Las actividades de esta fase incluyen: (a) revisión documental de los entregables de la consultoría de A4 Asociados (2022), el Anexo Técnico ITS del proceso de contratación 2023, los Estudios Previos de 2023 y el RFI 2025 de Metro Sabanas; (b) identificación de los actores institucionales involucrados (Metro Sabanas, Ministerio de Transporte, potenciales proveedores tecnológicos, operadores de transporte); (c) definición de la estructura de gobierno del proyecto, incluyendo los roles, responsabilidades y mecanismos de toma de decisiones; y (d) elaboración del Plan de Trabajo y Cronograma detallado, que incluye no solo las fechas de entrega, sino los criterios de aceptación, las dependencias entre entregables y los riesgos identificados.

El producto de esta fase es el **Entregable 1.1 (Plan de Trabajo y Cronograma)**, que se formaliza en este mismo documento, y el **Entregable 2.1 (Revisión y Clasificación de Servicios ITS)**, que documenta el resultado de la revisión documental y el mapeo de los sistemas definidos históricamente (SRC, SGCF, SIU, SST) con los subsistemas ITS de la normativa colombiana.

### 2.3 Fase 2: Diseño Conceptual (Semanas 2-3)

La segunda fase constituye el núcleo técnico de la consultoría. Su objetivo es definir, a nivel conceptual, la arquitectura tecnológica del SETP Sincelejo y especificar los componentes de hardware, software e interfaces que la conforman. Esta fase no produce diseños de ingeniería de detalle (que corresponden al proveedor implementador), pero sí establece los parámetros técnicos, las especificaciones mínimas y las interfaces que ese proveedor deberá cumplir.

Las actividades de esta fase se organizan en cuatro entregables complementarios. El **Entregable 2.2 (Arquitectura Tecnológica Conceptual)** define la visión de componentes y subsistemas, presentando un diagrama de arquitectura en capas (presentación, aplicación, datos, comunicaciones, campo) y estableciendo los principios arquitectónicos (modularidad, escalabilidad, interoperabilidad, seguridad, disponibilidad, mantenibilidad). El **Entregable 3.1 (Concepto de Operación Tecnológica)** describe cómo se operarían los cuatro sistemas en la práctica: quién operaría qué, cuáles serían los flujos de información entre los sistemas, cuáles serían los roles y responsabilidades del personal operativo, y cuáles son los tres escenarios institucionales definidos en 2015 (base, socio tecnológico, operador recaudador) actualizados al contexto de 2026. El **Entregable 3.2 (Diseño y Especificaciones Conceptuales)** detalla las especificaciones de hardware onboard (CPU, RAM, almacenamiento, GPS, comunicaciones), las especificaciones de software (funcionalidades mínimas por sistema), las interfaces entre sistemas (protocolos, formatos de datos, frecuencias de sincronización) y la normativa aplicable. Finalmente, el **Entregable 3.3 (Requerimientos Funcionales y No Funcionales)** estructura los requerimientos en formato estándar (código, descripción, prioridad, trazabilidad a sistema), diferenciando entre requerimientos funcionales (qué debe hacer el sistema) y no funcionales (cómo debe hacerlo: rendimiento, seguridad, disponibilidad, usabilidad).

Un aspecto crítico de esta fase es la escala del sistema: **46 vehículos**. Este número no es arbitrario: proviene del proceso de contratación de 2023 y representa la flota proyectada para la operación inicial del SETP Sincelejo. Todas las especificaciones de hardware, las estimaciones de costos y los requerimientos de rendimiento deben dimensionarse para esta escala, con márgenes de crecimiento que permitan futuras expansiones sin rediseño completo del sistema.

### 2.4 Fase 3: Análisis Tecnológico (Semanas 3-4)

La tercera fase tiene como objetivo apoyar a Metro Sabanas S.A.S. en la preparación de los documentos de contratación tecnológica. Esta fase no diseña el proceso de contratación en su totalidad (que es responsabilidad del área jurídica y de compras de Metro Sabanas), pero sí estructura los requerimientos técnicos que esos documentos deben contener.

El **Entregable 3.4 (Apoyo en RFI y RFQ)** es el producto principal de esta fase. Este entregable debe reflejar la estructura real del RFI 2025 de Metro Sabanas: no una adquisición por lotes tradicionales (Lote 1, Lote 2, Lote 3), sino una **contratación integrada de tres contratos** (flota + tecnología + operación) donde la empresa operadora puede proponer modelos integrados. El entregable incluye: (a) una estructura propuesta para el RFI, incluyendo las secciones técnicas que los oferentes deben responder; (b) una lista de requerimientos para el RFQ, derivados de los Entregables 3.2 y 3.3; (c) un modelo de evaluación técnica con criterios de ponderación; y (d) una estructura de garantías, soporte post-contratación y condiciones de servicio.

Una distinción importante es que este entregable no redacta el RFI ni el RFQ en su totalidad (esos documentos son de responsabilidad jurídica de Metro Sabanas), pero sí proporciona el **contenido técnico** que debe insertarse en ellos: especificaciones, requerimientos, criterios de evaluación, matrices de cumplimiento y preguntas orientadoras para los oferentes.

---

## 3. CRONOGRAMA DE EJECUCIÓN

### 3.1 Estructura temporal

La consultoría se ejecuta en un período de **cuatro semanas**, contadas a partir de la firma del contrato y la entrega por parte de Metro Sabanas S.A.S. de la información técnica, operativa y documental requerida para el inicio de las actividades. Este plazo es ajustado pero viable, dado que el proyecto no implica desarrollo de software ni instalación de hardware, sino revisión documental, análisis técnico y redacción de especificaciones.

La distribución temporal de las fases es la siguiente: la **Fase 1 (Inicio y Diagnóstico)** ocupa la **Semana 1**, con las actividades de revisión documental, identificación de actores y gobierno del proyecto. La **Fase 2 (Diseño Conceptual)** se desarrolla durante las **Semanas 2 y 3**, con las actividades de definición de arquitectura, diseño de especificaciones y estructuración de requerimientos. La **Fase 3 (Análisis Tecnológico)** se ejecuta durante las **Semanas 3 y 4**, con las actividades de apoyo en RFI y RFQ. Es importante notar que hay una superposición entre la Fase 2 y la Fase 3 en la Semana 3: esto es deliberado, porque los requerimientos del RFQ (Fase 3) se derivan directamente de las especificaciones y requerimientos definidos en la Fase 2, y es conveniente que el equipo de consultoría comience a trabajar en el RFQ tan pronto como tenga borradores avanzados de los Entregables 3.2 y 3.3.

### 3.2 Hitos de pago

El contrato se estructura en tres hitos de pago, condicionados a la entrega y aceptación de los productos correspondientes. El primer hito corresponde al **40% del valor total ($15.600.000 COP)** y se paga contra la entrega de los productos de la Fase 1, es decir, el Plan de Trabajo y Cronograma (E1.1) y la Revisión y Clasificación de Servicios ITS (E2.1). El segundo hito corresponde al **30% del valor total ($11.700.000 COP)** y se paga contra la entrega de los productos de la Fase 2, es decir, la Arquitectura Tecnológica Conceptual (E2.2), el Concepto de Operación Tecnológica (E3.1), el Diseño y Especificaciones Conceptuales (E3.2) y los Requerimientos Funcionales y No Funcionales (E3.3). El tercer hito corresponde al **30% restante ($11.700.000 COP)** y se paga contra la entrega del producto de la Fase 3, es decir, el Apoyo en RFI y RFQ (E3.4).

Esta estructura de pagos refleja la lógica del esfuerzo: la Fase 1 requiere una intensidad alta de revisión documental y coordinación (40%), la Fase 2 constituye el núcleo técnico con mayor volumen de redacción (30%), y la Fase 3, aunque importante, se beneficia de los productos previos y tiene un volumen menor de redacción original (30%).

### 3.3 Proceso de aprobación de entregables

Una vez entregado cada producto, Metro Sabanas S.A.S. contará con un plazo máximo de **cinco (5) días hábiles** para realizar la revisión correspondiente y comunicar por escrito las observaciones, ajustes o correcciones que considere necesarias. Este plazo es razonable para documentos técnicos de esta naturaleza: no son documentos de divulgación que se lean en una sentada, sino documentos de especificación que requieren revisión técnica detallada por parte del equipo de Metro Sabanas.

En caso de que, transcurrido dicho término, no se reciban observaciones o solicitudes de ajuste por parte de Metro Sabanas S.A.S., el respectivo entregable se entenderá aprobado a satisfacción para todos los efectos contractuales y de facturación. Las observaciones presentadas deberán corresponder al alcance definido en la propuesta contractual: Innovadataco realizará los ajustes que resulten procedentes y entregará la versión ajustada para su validación final. Es importante aclarar que las observaciones que impliquen ampliación del alcance (por ejemplo, solicitar un nuevo entregable no contemplado en la propuesta) serán evaluadas por Innovadataco y, de ser procedentes, se formalizarán mediante un adendum contractual con los ajustes de cronograma y valor correspondientes.

### 3.4 Dependencias críticas

El cumplimiento del cronograma depende de tres factores externos al control directo de Innovadataco. El primero es la **entrega oportuna de información por parte de Metro Sabanas S.A.S.**: la consultoría requiere acceso a la documentación técnica, operativa y contractual del SETP Sincelejo (entregables de A4 Asociados, anexos técnicos del proceso 2023, RFI 2025, entre otros). Retrasos en la entrega de esta información generarán, inevitablemente, retrasos en la elaboración de los entregables. El segundo factor es la **disponibilidad del equipo técnico de Metro Sabanas para mesas técnicas**: varios entregables (especialmente el Concepto de Operación y el Apoyo en RFI/RFQ) requieren sesiones de validación con el equipo del cliente para confirmar supuestos, validar escenarios y definir prioridades. El tercer factor es la **agilidad en la revisión y aprobación de entregables**: si Metro Sabanas S.A.S. utiliza los cinco días hábiles de plazo para cada entregable, el cronograma se mantiene; si los plazos de revisión se extienden, el cronograma total se verá afectado.

---

## 4. GOBERNANZA DEL PROYECTO

### 4.1 Estructura de gobierno

Innovadataco designará un **Líder del Proyecto** encargado de gestionar, coordinar y participar en las reuniones que sean requeridas por Metro Sabanas S.A.S. y/o por el equipo de supervisión del SETP. Este líder actúa como interlocutor técnico principal para la validación de entregables, la articulación con actores institucionales, proveedores tecnológicos y grupos de interés del proyecto. Su rol no es solo administrativo: es técnico, en el sentido de que debe comprender la arquitectura de los sistemas ITS, la normativa colombiana y el contexto institucional del SETP Sincelejo para poder representar adecuadamente los intereses de Metro Sabanas en las interacciones con terceros.

Adicionalmente, el líder del proyecto brinda apoyo técnico y estratégico a Metro Sabanas S.A.S. de manera articulada y coordinada, para el cumplimiento del plan de trabajo, así como para el seguimiento y control del cronograma establecido. Esto incluye la identificación proactiva de riesgos, la propuesta de mitigaciones y la escalación oportuna de problemas que requieran decisión del nivel directivo de Metro Sabanas.

### 4.2 Mecanismos de comunicación

La comunicación entre Innovadataco y Metro Sabanas S.A.S. se estructura en tres niveles. El primero es la **comunicación operativa diaria**: correos electrónicos, mensajes instantáneos y llamadas telefónicas para resolver dudas puntuales, solicitar documentos o confirmar detalles. El segundo es la **mesa técnica semanal**: una reunión programada (presencial o virtual) de duración máxima dos horas, donde se revisa el avance del proyecto, se validan supuestos técnicos, se resuelven bloqueos y se definen las prioridades de la semana siguiente. El tercero es la **revisión de entregables**: sesiones formales donde Innovadataco presenta el borrador de un entregable, Metro Sabanas realiza observaciones y se acuerda el plan de ajustes.

Todos los acuerdos técnicos relevantes serán documentados en actas de reunión, que serán compartidas por Innovadataco dentro de las 24 horas siguientes a cada sesión. Estas actas constituyen la memoria formal del proyecto y son la base para resolver discrepancias sobre lo acordado.

### 4.3 Confidencialidad y propiedad intelectual

Las partes se comprometen a mantener la reserva y confidencialidad de la información técnica, operativa, comercial y estratégica intercambiada durante la ejecución del proyecto, salvo autorización expresa de la otra parte o requerimiento legal. Esto incluye no solo los documentos formales, sino también la información compartida en mesas técnicas, correos electrónicos y llamadas telefónicas.

Los documentos, análisis, diseños conceptuales y demás productos elaborados en ejecución de esta consultoría serán entregados a Metro Sabanas S.A.S. para su utilización dentro del proyecto SETP Sincelejo. Innovadataco conservará la titularidad sobre sus metodologías, modelos, herramientas, plantillas y conocimiento especializado utilizados para la elaboración de los productos. Esta distinción es relevante: Metro Sabanas adquiere el derecho de uso de los productos específicos del SETP Sincelejo, pero no adquiere la propiedad intelectual de las metodologías genéricas de Innovadataco, que pueden ser reutilizadas en otros proyectos.

---

## 5. RIESGOS Y MITIGACIONES

### 5.1 Riesgos identificados

El proyecto enfrenta cinco riesgos principales que deben ser gestionados proactivamente para garantizar el cumplimiento del cronograma y la calidad de los entregables.

El **riesgo 1** es la **disponibilidad de documentación histórica**. Si Metro Sabanas S.A.S. no cuenta con versiones completas de los entregables de A4 Asociados (2022), el Anexo Técnico ITS del proceso 2023 o los Estudios Previos, la consultoría deberá reconstruir información por inferencia, lo que aumenta el riesgo de error y el tiempo de elaboración. La mitigación es solicitar formalmente la documentación en la primera semana y, si no está disponible, documentar los vacíos como supuestos del proyecto.

El **riesgo 2** es la **rotación de personal en Metro Sabanas**. Si las personas que conocen la historia del proyecto (quienes participaron en el proceso 2023 o en la consultoría de A4 Asociados) ya no están en la empresa, la validación de entregables se dificulta. La mitigación es identificar desde el inicio quiénes son los referentes técnicos y, si no están disponibles, buscar contactos alternativos (por ejemplo, en el Ministerio de Transporte o en A4 Asociados).

El **riesgo 3** es la **cambios en el RFI 2025 de Metro Sabanas**. Si Metro Sabanas modifica la estructura del RFI (por ejemplo, cambia de tres contratos a una adquisición por lotes tradicional), los entregables de la Fase 3 quedarán desactualizados. La mitigación es mantener comunicación semanal con el área de compras de Metro Sabanas para detectar cambios estructurales con anticipación.

El **riesgo 4** es la **complejidad normativa**. La Resolución 20203040034065 es un documento extenso y técnico; si su interpretación es errónea, las especificaciones y requerimientos pueden quedar desalineados. La mitigación es validar la interpretación normativa con un experto externo en ITS colombiano o con el Ministerio de Transporte directamente.

El **riesgo 5** es el **plazo ajustado**. Cuatro semanas es un plazo corto para siete entregables técnicos. La mitigación es la superposición deliberada de fases (Fase 2 y Fase 3 comparten la Semana 3) y la priorización de los entregables críticos (E3.2 y E3.3, que son la base de E3.4).

---

## 6. ENTREGABLES Y CRONOGRAMA DETALLADO

### 6.1 Lista de entregables

El proyecto produce siete entregables técnicos, organizados en tres fases, que culminan en el **Estudio Previo ITS** para el proceso de licitación del componente tecnológico del SETP Sincelejo.

La **Fase 1: Inicio y Diagnóstico** produce dos entregables. El **Entregable 1.1** es el presente Plan de Trabajo y Cronograma, que establece la metodología, el cronograma, la gobernanza y los riesgos del proyecto. El **Entregable 2.1** es la Revisión y Clasificación de Servicios ITS, que documenta el resultado de la revisión documental y el mapeo de los cuatro sistemas reales del SETP (SRC, SGCF, SIU, SST) con los subsistemas ITS definidos en la Resolución 20203040034065.

La **Fase 2: Diseño Conceptual** produce cuatro entregables. El **Entregable 2.2** es la Arquitectura Tecnológica Conceptual, que define el diagrama de arquitectura en capas, los principios arquitectónicos y las interfaces entre sistemas. El **Entregable 3.1** es el Concepto de Operación Tecnológica, que describe los roles, flujos y escenarios institucionales de operación. El **Entregable 3.2** es el Diseño y Especificaciones Conceptuales, que detalla el hardware, software, interfaces y normativa aplicable. El **Entregable 3.3** es la Definición de Requerimientos Funcionales y No Funcionales, que estructura los requerimientos en formato estándar con trazabilidad a los sistemas.

La **Fase 3: Análisis Tecnológico** produce un entregable. El **Entregable 3.4** es el Apoyo en la Elaboración de RFI y RFQ, que estructura los requerimientos técnicos para los documentos de contratación de Metro Sabanas.

### 6.2 Cronograma de entregables

| Entregable | Fase | Semana | Producto | Hito de pago |
|------------|------|--------|----------|--------------|
| **E1.1** | Inicio y Diagnóstico | 1 | Plan de Trabajo y Cronograma | Hito 1 (40%) |
| **E2.1** | Inicio y Diagnóstico | 1 | Revisión y Clasificación de Servicios ITS | Hito 1 (40%) |
| **E2.2** | Diseño Conceptual | 2 | Arquitectura Tecnológica Conceptual | Hito 2 (30%) |
| **E3.1** | Diseño Conceptual | 2-3 | Concepto de Operación Tecnológica | Hito 2 (30%) |
| **E3.2** | Diseño Conceptual | 2-3 | Diseño y Especificaciones Conceptuales | Hito 2 (30%) |
| **E3.3** | Diseño Conceptual | 3 | Requerimientos Funcionales y No Funcionales | Hito 2 (30%) |
| **E3.4** | Análisis Tecnológico | 3-4 | Apoyo en RFI y RFQ | Hito 3 (30%) |

La ejecución de la Fase 2 y la Fase 3 con superposición en la Semana 3 es deliberada. Los requerimientos del RFQ (E3.4) se derivan directamente de las especificaciones (E3.2) y los requerimientos (E3.3), por lo que el equipo puede comenzar a estructurar el RFQ tan pronto como tenga borradores avanzados de estos entregables, sin esperar a que estén 100% aprobados.

---

*Documento elaborado por ZEUS — InnovaDataCo | 2026-06-15 | Versión 2.0*
