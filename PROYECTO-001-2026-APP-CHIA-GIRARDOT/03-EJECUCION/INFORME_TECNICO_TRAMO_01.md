# INFORME TÉCNICO N° 1 — TRAMO 1
## Diseño de la Capa de Equipos ITS — Corredor Chía-Girardot

**Proyecto:** APP-CHIA-GIRARDOT — Estructuración ITS  
**Código:** PROYECTO-001-2026-APP-CHIA-GIRARDOT  
**Entregable:** E5-Diseños-ITS / Tramo-01  
**Fecha:** 2026-06-02  
**Elaborado por:** ZEUS — InnovaDataCo  
**Revisión:** V1.0 — Borrador para validación del CEO

---

## RESUMEN EJECUTIVO

El presente informe detalla el diseño de la capa de equipos de Sistemas Inteligentes de Transporte (ITS) para el **Tramo 1: Variante Chía — Glorieta Norte** del Corredor Vial Chía-Girardot. Este tramo, con una longitud de 7.134 kilómetros distribuidos en dos subtramos, constituye una variante rápida periurbana que evita el tráfico urbano del municipio de Chía y establece la conexión inicial hacia el norte del corredor.

**Hallazgo principal:** De los 42 Componentes de Campo (CCs) definidos en el catálogo oficial de TransConsult, únicamente **15 componentes resultan aplicables** para este tramo, dado su perfil de infraestructura: vía variante plana, sin túneles, sin peajes, sin puentes mayores y con dos glorietas como únicos elementos de intersección. Los 27 componentes restantes quedan descartados por no corresponder a la tipología real del tramo, evitando así sobredimensionamiento innecesario del sistema ITS.

**Componentes críticos identificados:** CCTV para monitoreo visual, VDS para caracterización del flujo, ECS para atención de emergencias, AID para detección automática de incidentes, y LCS para gestión de flujo en las dos glorietas. La red de comunicaciones se sustenta en fibra óptica (FOC) con respaldo radial (RCS), garantizando redundancia en la transmisión de datos.

**Dudas técnicas pendientes:** Se identifican seis puntos de verificación que requieren confirmación por parte del equipo de diseño vial, relacionados con la existencia de alumbrado público, la necesidad de estación meteorológica, la bidireccionalidad de la vía, la densidad de cámaras, el tipo de glorietas y la modalidad de tendido de fibra óptica.

---

## 1. CONTEXTO DEL PROYECTO

### 1.1 Alcance del Corredor Chía-Girardot

El Corredor Vial Chía-Girardot es una infraestructura estratégica para la Región Central de Colombia, diseñada para mejorar la conectividad entre el norte del departamento de Cundinamarca (Chía, Cota, Cajicá) y el sur (Soacha, Sibaté, La Mesa, Anapoima, Tocaima, Girardot), descongestionando la Autopista Norte y ofreciendo una alternativa viable al cuello de botella actual que representa el paso por Bogotá.

El corredor se estructura en **15 tramos** con una longitud total aproximada de 333.6 kilómetros, distribuidos entre vías principales (variantes), tramos de montaña, conexiones urbanas y vías colectoras. La capa de ITS tiene como objetivo dotar al corredor de inteligencia operativa, seguridad vial, gestión de tráfico en tiempo real y atención de emergencias, transformando una vía tradicional en un corredor inteligente.

### 1.2 Metodología de Diseño ITS

El diseño de la capa de equipos ITS no sigue un criterio genérico de "instalar todo en todos los tramos". Por el contrario, se aplica una **metodología de tipología real**: cada tramo es analizado según su infraestructura específica — túneles, puentes, peajes, pasos urbanos, glorietas, tramos de montaña, zonas de fauna — y únicamente se asignan los componentes que esa infraestructura realmente requiere.

Esta metodología evita:
- **Sobredimensionamiento:** Instalar peajes electrónicos donde no hay peajes, o controles de túneles donde no hay túneles.
- **Costos innecesarios:** Cada componente de campo tiene un costo de adquisición, instalación, operación y mantenimiento. Instalar lo que no se necesita es un desperdicio de recursos.
- **Complejidad operativa:** Más equipos generan más alarmas, más mantenimiento y más personal de operación. La simplicidad operativa es un valor.

La base de diseño parte del **catálogo oficial de 42 Componentes de Campo (CCs)** definido por TransConsult, que abarca desde CCTV hasta respaldo satelital, pasando por peajes electrónicos, control de túneles, detección de fauna y gestión de iluminación.

---

## 2. CARACTERIZACIÓN DEL TRAMO 1

### 2.1 Ficha Técnica General

| Parámetro | Valor | Observación |
|-----------|-------|-------------|
| **Código del tramo** | T-01 | Nomenclatura oficial del proyecto |
| **Nombre** | Variante Chía — Glorieta Norte | Denominación funcional |
| **Longitud total** | 7.134 km | Incluye ambos subtramos |
| **Número de subtramos** | 2 | Segmentación por puntos de interés |
| **Tipo de vía** | Variante rápida | No es vía urbana ni carretera de montaña |
| **Carriles estimados** | 2 por sentido | Verificar en planos constructivos |
| **Velocidad de diseño** | 80 km/h | Estimada para variante periurbana |
| **Topografía** | Plana | Altiplano Cundiboyacense, pendiente mínima |
| **Zona climática** | Templada | Chía: 2,564 msnm, clima fresco seco |
| **Riesgo sísmico** | Bajo | No en zona de falla activa |
| **Riesgo geotécnico** | Bajo | Terreno plano, sin taludes inestables |
| **Riesgo hidrológico** | Bajo | Drenaje natural eficiente, zona plana |
| **Acceso a red eléctrica** | Sí | Periurbano, red de Cundinamarca disponible |
| **Cobertura celular** | Sí | Zona poblada, operadores móviles presentes |

### 2.2 Descripción Geográfica

El Tramo 1 se localiza en el extremo norte del corredor, en el área de influencia del municipio de Chía, uno de los centros poblados de mayor crecimiento en la Sabana de Bogotá en las últimas dos décadas. La variante tiene como propósito evitar que el tráfico de paso entre la Autopista Norte y el corredor sur entre al casco urbano de Chía, reduciendo congestión y tiempos de viaje.

**Punto de inicio:** Av. Pradilla, principal vía de acceso a Chía desde la Autopista Norte.  
**Punto de fin:** Glorieta Norte de Cota, que marca la transición hacia el Tramo 2 (Variante Cota).  
**Entorno:** Zona periurbana en transición, con desarrollos residenciales de estrato medio-alto, centros comerciales (como el Centro Chía), y zonas de reserva para expansión urbana. No se trata de una zona rural aislada, ni de un centro urbano denso. Es un territorio de "borde" que crece hacia la vía.

### 2.3 Subtramo 1.1 — Variante Chía (3.086 km)

**Código:** T-01-S01  
**Longitud:** 3.086 kilómetros (43% del tramo total)  
**Inicio:** Intersección con Av. Pradilla, Chía  
**Fin:** Glorieta de Av. Chilacos  
**Infraestructura principal:** Vía variante de dos carriles por sentido, una glorieta al final del subtramo.

**Características operativas:**
- Este subtramo es la **puerta de entrada** al corredor desde el norte. Todo vehículo que venga de Bogotá, Zipaquirá o Chía hacia el sur (Cota, Funza, Mosquera, Girardot) pasará por aquí.
- La conexión con Av. Pradilla es crítica: es una vía con alta demanda vehicular, especialmente en horas pico y fines de semana (Chía es destino de compras y restaurantes para bogotanos).
- La glorieta de Av. Chilacos es un punto de conflicto potencial: vehículos que vienen de la variante, de Chía y de Cota convergen en este nudo. Sin una gestión inteligente del flujo, puede convertirse en cuello de botella.
- El terreno es completamente plano, sin restricciones geométricas que afecten la visibilidad o la velocidad. No hay curvas cerradas, ni túneles, ni puentes.

**Riesgos identificados:**
- **Congestión en la glorieta:** Sin semáforos inteligentes o gestión de carril, la glorieta puede colapsar en horas pico.
- **Accidentes por velocidad:** Vía rápida con posible exceso de velocidad, especialmente en tramos rectos.
- **Atención de emergencias:** En caso de accidente, los usuarios necesitan un canal de comunicación rápido con servicios de emergencia.

### 2.4 Subtramo 1.2 — Conexión Chía-Cota (4.048 km)

**Código:** T-01-S02  
**Longitud:** 4.048 kilómetros (57% del tramo total)  
**Inicio:** Glorieta de Av. Chilacos  
**Fin:** Glorieta Norte de Cota  
**Infraestructura principal:** Vía variante continua, una glorieta al final del subtramo.

**Características operativas:**
- Este subtramo es la **transición** entre Chía y Cota. No tiene conexiones intermedias con otras vías importantes, lo que lo convierte en un tramo de "paso" puro.
- La glorieta Norte de Cota conecta con la variante de Cota (Tramo 2), que tiene un perfil más complejo al incluir paso urbano.
- Al igual que el subtramo anterior, el terreno es plano y sin restricciones. La vía es recta, con visibilidad despejada.
- La zona es menos densa que Chía, pero igualmente periurbana. Se observan zonas de loteo y desarrollo residencial en expansión.

**Riesgos identificados:**
- **Velocidad descontrolada:** Al ser un tramo de paso recto, los conductores tienden a acelerar. El límite de velocidad debe ser gestionado activamente.
- **Falta de puntos de referencia:** Al no haber intersecciones ni cambios de paisaje, los conductores pueden perder la noción de velocidad.
- **Emergencias en zona aislada:** Aunque es periurbano, no hay servicios de emergencia inmediatos en la vía. Un usuario accidentado necesita comunicarse con el centro de control.

---

## 3. ANÁLISIS DE TIPOLOGÍA DE INFRAESTRUCTURA

### 3.1 Inventario de Elementos

Tras analizar la ficha técnica del tramo y la descripción de sus subtramos, se identifica el siguiente inventario de elementos de infraestructura que condicionan el diseño ITS:

| Elemento | Cantidad | Ubicación Precisa | Relevancia para ITS | Impacto en Selección de CCs |
|----------|----------|-------------------|---------------------|---------------------------|
| **Glorietas (intersecciones)** | 2 | T-01-S01 km 3.086 (Av. Chilacos) y T-01-S02 km 4.048 (Norte Cota) | **Alta** — son los únicos puntos de conflicto del tramo | Obliga a incluir CC-33 (LCS) para gestión de flujo |
| **Vía variante** | 7.134 km | Todo el tramo | **Media** — requiere monitoreo continuo pero no tiene complejidad | Base para CC-01, CC-05, CC-23 |
| **Túneles** | 0 | N/A | N/A | Elimina CC-15, CC-17, CC-30 |
| **Puentes (mayores)** | 0 | N/A | N/A | Elimina CC-09 |
| **Peajes** | 0 | N/A | N/A | Elimina CC-07, CC-11, CC-12 |
| **Paso urbano** | 0 | N/A | N/A | Elimina CC-16, CC-18, CC-22, CC-31 |
| **Zonas de fauna silvestre** | 0 | N/A | N/A | Elimina CC-37 |
| **Taludes inestables / Riesgo geotécnico** | 0 | N/A | N/A | Elimina CC-08 |
| **Riesgo hidrológico crítico** | 0 | N/A | N/A | Elimina CC-10 |
| **Zonas de alta contaminación** | 0 | N/A | N/A | Elimina CC-31 |

**Conclusión del análisis:** El Tramo 1 es una vía **simple en su morfología**: recta, plana, sin elementos estructurales complejos. Su única complejidad operativa radica en las dos glorietas, que son puntos de intersección donde múltiples flujos vehiculares convergen. Esto hace que el diseño ITS sea **limpio y enfocado**: monitoreo, conteo, emergencias, gestión de velocidad y control de intersecciones.

---

## 4. MAPEO DE LOS 42 COMPONENTES DE CAMPO (CCs)

### 4.1 Criterio de Selección

Para cada uno de los 42 CCs del catálogo oficial, se aplicó el siguiente criterio de decisión:

1. **¿La infraestructura del tramo lo requiere?** Si el tramo tiene un elemento que justifica el componente (ej. túnel → control de túneles), se marca como aplicable.
2. **¿El entorno operativo lo justifica?** Si el contexto del tramo (urbano, rural, montaña, periurbano) genera una necesidad funcional que el componente resuelve, se marca como aplicable.
3. **¿Es un componente base del corredor?** Algunos componentes son transversales a todos los tramos porque forman la red mínima de operación (comunicaciones, respaldo energético, estructura física).

Si la respuesta a las tres preguntas es "no", el componente queda **descartado** para este tramo, con la justificación correspondiente.

### 4.2 Componentes Aplicables — Ficha Detallada

#### CC-01 — CCTV: Cámaras de Vigilancia por Video

**Justificación técnica:** El Tramo 1 es una vía variante de 7.1 km sin presencia de personal de operación en campo. El CCTV es el único medio de "visión" que tiene el Centro de Control para saber qué está pasando en la vía: accidentes, vehículos detenidos, congestionamiento, condiciones climáticas, estado de la calzada. Sin cámaras, el corredor opera a ciegas.

**Densidad recomendada:** 1 cámara cada 1.2 km en promedio, con refuerzo en puntos críticos (glorietas, entradas). Para 7.1 km, esto resulta en **6 cámaras**: 3 por subtramo.

**Distribución propuesta:**
- **Subtramo 1.1:** CCTV-01 (PTZ, entrada Av. Pradilla), CCTV-02 (fija, km 1.5), CCTV-03 (PTZ, glorieta Av. Chilacos).
- **Subtramo 1.2:** CCTV-04 (fija, inicio), CCTV-05 (PTZ, km 5.5), CCTV-06 (PTZ, glorieta Norte Cota).

**Especificación técnica:** Cámaras IP PTZ (domo motorizado) para glorietas y entradas, con capacidad de zoom óptico 30x, visión nocturna IR 100m, protección IP66. Cámaras fijas para puntos intermedios, resolución 2MP Full HD, lente varifocal.

**Duda técnica:** ¿La densidad de 1 cámara cada 1.2 km es suficiente o se requiere una cobertura más densa (ej. cada 500m)? Esto depende del estándar de diseño que aplique el proyecto.

---

#### CC-02 — AID: Detección Automática de Incidentes

**Justificación técnica:** El ojo humano del operador de CCTV no puede estar pendiente de 6 cámaras 24/7. El AID es un sistema de videoanálisis que procesa las imágenes de las cámaras y detecta automáticamente eventos: vehículo detenido, sentido contrario, peatón en calzada, humo, congestión, objeto en vía. Reduce el tiempo de detección de incidentes de minutos a segundos.

**Aplicación en el tramo:** El AID se instala en las cámaras ubicadas en zonas de mayor riesgo: entrada a la variante (donde los vehículos pueden entrar a velocidad inadecuada) y glorietas (donde pueden ocurrir colisiones). No es necesario en todo el tramo, sino en puntos estratégicos.

**Distribución propuesta:** 2 sistemas AID, uno por subtramo, integrados con las cámaras PTZ de la glorieta y la entrada.

**Especificación técnica:** Software de análisis de video basado en inteligencia artificial, integrado con las cámaras CCTV existentes. Debe soportar las categorías de evento: vehículo detenido, velocidad anómala, sentido contrario, conglomeración, peatón/animal en vía, pérdida de visibilidad (humo/niebla).

---

#### CC-03 — DMS/VMS: Paneles de Mensajería Variable

**Justificación técnica:** El Tramo 1 es una variante rápida que conecta con la Autopista Norte. Los conductores que entran desde Av. Pradilla necesitan información clara: ¿el corredor está abierto? ¿hay congestión más adelante? ¿hay un accidente en el tramo 7? ¿cuál es la velocidad máxima permitida? Un panel de mensaje variable en la entrada reduce la incertidumbre y mejora la toma de decisiones del conductor.

**Duda técnica:** ¿La variante es bidireccional con entradas separadas, o es unidireccional? Si es bidireccional con dos entradas, se necesitan 2 paneles (uno por sentido). Si es unidireccional con una sola entrada, basta con 1 panel.

**Distribución propuesta:** 1 panel en la entrada desde Av. Pradilla (verificar si se necesita uno adicional para el sentido contrario). Panel adicional opcional en la glorieta de Av. Chilacos para informar sobre condiciones del Tramo 2.

**Especificación técnica:** Panel LED full matrix, visible a 200m, protección IP65, control remoto desde el CCO. Capacidad de mensajes preprogramados: "Velocidad Máxima 80 km/h", "Congestión 5 km adelante", "Accidente — Carril Cerrado", "Niebla — Reduzca Velocidad".

---

#### CC-04 — ECS/SOS: Puntos de Emergencia

**Justificación técnica:** En una variante de 7.1 km sin presencia de peajes ni servicios de emergencia, un usuario que sufre un accidente o una falla mecánica necesita un medio de comunicación directo con el centro de control. El teléfono de emergencia (ECS) es un punto fijo de contacto, visible, accesible y siempre operativo. No depende de que el usuario tenga batería en el celular ni señal de red.

**Densidad recomendada:** 1 punto cada 2 km en promedio, ubicados de forma alternada por sentido para que un usuario siempre tenga un punto a menos de 1 km de distancia. Para 7.1 km, esto resulta en **4 puntos de emergencia**.

**Distribución propuesta:**
- **Subtramo 1.1:** ECS-01 (km 1.0, sentido sur), ECS-02 (km 2.5, sentido norte).
- **Subtramo 1.2:** ECS-03 (km 4.0, sentido sur), ECS-04 (km 6.5, sentido norte).

**Especificación técnica:** Columna de emergencia con interfón VoIP, botón de pánico, altavoz, identificación luminosa (LED azul), alimentación por red eléctrica con batería de respaldo 72h. Comunicación sobre fibra óptica (no depende de red celular).

---

#### CC-05 — VDS/TDS: Contadores de Tráfico

**Justificación técnica:** El corredor necesita "saber" cuántos vehículos pasan, a qué velocidad, en qué horarios, y qué tipo de vehículos son (automóviles, buses, camiones). Esta información es la base de toda la gestión operativa: programación de mantenimiento, ajuste de horarios de peajes, planificación de cierres por obra, validación de modelos de tráfico. Sin contadores, el corredor opera sin datos.

**Distribución propuesta:** 2 puntos de conteo por subtramo, uno por sentido. Total: **4 sensores VDS**.
- **Subtramo 1.1:** VDS-01 (km 0.5, sentido norte-sur), VDS-02 (km 2.8, sentido sur-norte).
- **Subtramo 1.2:** VDS-03 (km 3.5, sentido norte-sur), VDS-04 (km 7.0, sentido sur-norte).

**Especificación técnica:** Sensores inductivos de lazo empotrados en calzada o sensores de radar montados en lateral. Deben contar, clasificar (por longitud/ejes) y medir velocidad. Precisión >95%. Comunicación por fibra óptica al nodo más cercano.

---

#### CC-13 — SPD: Radar Pedagógico

**Justificación técnica:** La variante Chía es una vía rápida recta y plana, donde los conductores tienden a exceder la velocidad. El radar pedagógico no es un radar de sanción (como los de policía), sino un dispositivo que muestra al conductor la velocidad a la que va, induciendo comportamiento más seguro por autoconsciencia. Es especialmente efectivo en zonas de cambio de velocidad (entrada a la variante desde Av. Pradilla, donde el límite puede bajar de 100 a 80 km/h).

**Distribución propuesta:** 1 radar pedagógico en la zona de entrada a la variante desde Av. Pradilla, donde ocurre el cambio de entorno urbano a variante rápida. Opcionalmente 1 adicional en la glorieta de Av. Chilacos si hay cambio de velocidad.

**Especificación técnica:** Radar Doppler montado en poste, display LED de 30cm de alto visible a 150m, alimentación solar + batería, conectividad inalámbrica al nodo ITS. Sin función de sanción (no es fotodetección).

---

#### CC-14 — VSL: Señal de Velocidad Variable

**Justificación técnica:** La velocidad máxima en una variante no debe ser fija todo el tiempo. Si hay niebla, lluvia, un accidente, o una obra, la velocidad debe reducirse dinámicamente. La señal de velocidad variable (VSL) permite al Centro de Control ajustar el límite de velocidad en tiempo real desde la sala, sin necesidad de enviar personal a campo.

**Duda técnica:** ¿Es necesaria en todo el tramo o solo en puntos específicos? Para un tramo de 7.1 km sin túneles ni zonas de riesgo climático extremo, la VSL puede ser más útil en las entradas y en las glorietas que en el tramo central. Se propone 1 por subtramo, ubicada en la entrada.

**Distribución propuesta:** 1 señal VSL en la entrada desde Av. Pradilla (T-01-S01) y 1 señal VSL en la entrada desde la glorieta de Av. Chilacos (T-01-S02). Total: **2 señales**.

**Especificación técnica:** Señal LED de velocidad límite, 60cm de diámetro, visibilidad 300m, control remoto desde CCO, conectividad por fibra óptica. Capacidad de mostrar valores de 40 a 100 km/h.

---

#### CC-23 — FOC: Fibra Óptica (Backbone de Comunicaciones)

**Justificación técnica:** Todos los equipos ITS generan datos que deben llegar al Centro de Control: video de cámaras, conteos de tráfico, alarmas de emergencia, estados de paneles. La fibra óptica es el medio de transporte de datos de mayor capacidad, menor latencia y mayor confiabilidad. Es la "espina dorsal" del sistema ITS. Sin fibra, no hay ITS.

**Diseño propuesto:** Tendido de fibra óptica monomodo de 12 fibras (6 en uso, 6 de reserva) a lo largo de los 7.1 km del tramo, con dos nodos de acceso: uno en la glorieta de Av. Chilacos (Nodo S-01) y otro en la glorieta Norte de Cota (Nodo S-02). Cada nodo tiene un gabinete con switch, protección eléctrica y UPS.

**Duda técnica:** ¿El tendido es aéreo (sobre postes existentes) o subterráneo (ducto)? Esto depende de la normativa del IDU y los derechos de vía. Lo más común en Colombia es aéreo en zonas rurales/periurbanas y subterráneo en zonas urbanas.

**Especificación técnica:** Fibra monomodo G.652D, cable de 12 fibras, tendido aéreo o en ducto subterráneo, conectores SC/APC, OTDR para certificación. Cada nodo: switch administrable L2, protección eléctrica, gabinete IP55.

---

#### CC-24 — RCS: Comunicación Radial (Respaldo)

**Justificación técnica:** La fibra óptica puede fallar: corte por obra, robo de cable, daño por terceros. La comunicación radial (radio VHF/UHF) es el respaldo que mantiene al centro de control conectado con los equipos de campo cuando la fibra no funciona. Es un sistema de redundancia crítica para la seguridad operativa.

**Aplicación en el tramo:** No se instalan radios en cada equipo, sino que se configura una red de radio que cubre todo el tramo desde los dos nodos de comunicación. Los equipos críticos (ECS, VSL) tienen capacidad de comunicarse por radio como respaldo.

**Especificación técnica:** Radio base en cada nodo de comunicación, antenas direccionales, cobertura de 5-10 km por radio. Frecuencia autorizada por ANE. Integración con el sistema de radio del Centro de Control regional.

---

#### CC-33 — LCS/SIG: Control de Carril en Glorietas

**Justificación técnica:** Las dos glorietas del Tramo 1 son los únicos puntos de conflicto real. En horas pico, múltiples flujos de vehículos convergen desde diferentes direcciones. Sin un sistema de gestión, la glorieta puede colapsar. El LCS (Lane Control System) utiliza semáforos dinámicos o señales de carril para regular el flujo: abrir o cerrar carriles, dar prioridad a una dirección, alternar flujos en caso de congestión.

**Duda técnica:** ¿Las glorietas son circulares tradicionales (sin semáforos) o son intersecciones semaforizadas? Si son circulares tradicionales, el LCS puede no aplicar (las glorietas se gestionan por normas de prioridad). Si son intersecciones con semáforos, el LCS es fundamental. Se requiere verificar el diseño vial de las glorietas.

**Distribución propuesta:** 4 señales de carril por glorieta (una por cada entrada), total **8 señales**. Las señales indican: carril abierto, carril cerrado, ceda el paso, dirección prioritaria.

**Especificación técnica:** Señales LED de carril, flechas direccionales y "X" de cierre, montadas en poste de 5m, control desde CCO, conectividad por fibra óptica.

---

#### CC-34 — PSS: Postes y Estructuras de Soporte

**Justificación técnica:** Ningún equipo ITS flota en el aire. Cada cámara, panel, sensor, antena y señal necesita un poste, una torreta, una estructura metálica o una fundación de concreto. El PSS es el componente "invisible" que sostiene todo lo visible. Aunque no es tecnológico, es indispensable.

**Distribución propuesta:** Un poste cada 100-200 metros aproximadamente, dependiendo de la ubicación de los equipos. Para 7.1 km, esto implica **35-70 postes/estructuras** en todo el tramo, incluyendo postes de CCTV, soportes de DMS, columnas de ECS, torres de radio, etc.

**Especificación técnica:** Postes metálicos galvanizados de 6-10m de altura, fundaciones de concreto según carga eólica, certificación estructural. Para gabinetes: bases de concreto con nivelación.

---

#### CC-35 — UPS/EPS: Respaldo Energético

**Justificación técnica:** Los equipos ITS no pueden apagarse cuando se va la luz. Un corte eléctrico en el momento de un accidente dejaría al corredor sin cámaras, sin comunicación y sin emergencia. El UPS (Uninterruptible Power Supply) garantiza que los equipos críticos sigan operando durante un corte eléctrico, mientras llega la planta de emergencia o se restablece el servicio.

**Distribución propuesta:** 1 gabinete UPS por cada nodo de comunicación. Total: **2 gabinetes** (uno en glorieta Av. Chilacos, otro en glorieta Norte Cota). Cada gabinete alimenta los equipos de su subtramo.

**Especificación técnica:** UPS industrial de 3-5 kVA, autonomía mínima 2 horas, bypass manual, monitoreo remoto de estado de batería, conectividad SNMP al CCO. Incluye protección eléctrica (supresor de sobretensiones, breaker diferencial).

---

#### CC-41 — E-LOG: Gestión de Carga Crítica y Logística Operativa

**Justificación técnica:** Este componente no es un equipo de campo, sino una capacidad del Centro de Control: la gestión logística de la operación del corredor. Incluye el monitoreo de vehículos de mantenimiento, grúas, ambulancias, patrullas, camiones de señalización, y la optimización de sus rutas y tiempos de respuesta. Aunque es un sistema de software, se le asigna un CC porque es una capacidad operativa que el corredor debe tener.

**Aplicación en el tramo:** El Tramo 1 no tiene su propio centro de control, sino que se conecta a un **Centro de Control Regional** que gestiona múltiples tramos. E-LOG es la capacidad de ese centro para gestionar los recursos de logística que atienden el tramo.

**Especificación técnica:** Software de gestión de flota (AVL/OBU integrado), integración con GIS, algoritmos de ruteo óptimo, interfaz con sistemas de emergencia. No requiere equipos en campo, sino licenciamiento y configuración en el CCO.

---

### 4.3 Componentes Dudosos — Requieren Verificación

#### CC-06 — ESS/RWIS: Estación Meteorológica

**Descripción:** Sensores que miden temperatura, humedad, velocidad del viento, presión barométrica, precipitación, visibilidad y estado de la calzada (seco, húmedo, congelado).

**Duda:** ¿Chía requiere una estación meteorológica? El clima de Chía es templado y estable: temperatura promedio 13°C, sin nevadas, sin lluvias torrenciales extremas, sin vientos huracanados. No es una zona de riesgo climático que justifique monitoreo continuo. Sin embargo, el conocimiento de la temperatura y el estado de la calzada puede ser útil para ajustar la velocidad variable (VSL) y los mensajes de los paneles (DMS).

**Recomendación:** Instalar **1 estación meteorológica mínima** en el punto medio del tramo (km 3.5), como referencia para todo el corredor. No es crítica, pero aporta valor operativo.

---

#### CC-20 — VIS/LGS: Iluminación de la Vía

**Descripción:** Sistema de alumbrado público inteligente ajustado a la hora del día, condiciones climáticas y flujo vehicular.

**Duda:** ¿La variante Chía ya tiene alumbrado público o es una vía oscura? Si la variante está diseñada como vía urbana/periurbana, probablemente ya tenga alumbrado convencional del municipio. Si es una vía nueva de desvío, puede no tenerlo. La iluminación es crítica para la seguridad nocturna y para que el CCTV funcione correctamente en horas de oscuridad.

**Recomendación:** Verificar en los planos de diseño vial si la variante incluye alumbrado. Si no lo tiene, el sistema ITS debe incluir iluminación de bajo consumo (LED) en los tramos donde hay equipos de CCTV y ECS, para garantizar visibilidad nocturna.

---

### 4.4 Componentes Descartados — Con Justificación Técnica

Los siguientes 27 componentes fueron evaluados y descartados para el Tramo 1, porque su infraestructura, entorno o tipología no los requiere:

| CC | Componente | Razón de Descarte |
|----|-----------|-------------------|
| **CC-07** | WIM — Pesaje Dinámico | No hay peaje ni estación de pesaje en el tramo. El pesaje dinámico se instala donde hay control de carga vehicular (peajes, puestos de control). |
| **CC-08** | GMS-I — Inclinometría Geotécnica | El terreno es plano y estable, sin taludes, cortes ni zonas de deslizamiento. La inclinometría se usa en tramos de montaña con riesgo geotécnico. |
| **CC-09** | SMS/SBT — Monitoreo de Estructuras | No hay puentes mayores, viaductos ni obras de arte que requieran monitoreo estructural continuo. |
| **CC-10** | WLS — Monitoreo Hídrico | No hay ríos, quebradas, zonas de inundación o riesgo hidrológico crítico. Chía es zona plana de altiplano. |
| **CC-11** | AVI/ETC — Peaje Electrónico | No hay peaje en este tramo. Los peajes electrónicos se instalan exclusivamente en estaciones de peaje. |
| **CC-12** | ALPR/LPR — Reconocimiento de Placas | No hay control de acceso ni peaje que requiera identificación automática de vehículos. |
| **CC-15** | TCS — Control de Túneles | No hay túneles en el tramo. El control de túneles incluye ventilación, iluminación específica, supresión de incendio y monitoreo de gases. |
| **CC-16** | EVCS — Electrolineras | No es una zona de carga eléctrica. Las electrolineras se instalan en zonas urbanas, centros comerciales o estaciones de servicio. |
| **CC-17** | PAS — Megafonía Inteligente | No hay túneles ni zonas de alta concentración peatonal donde la megafonía masiva sea necesaria. |
| **CC-18** | BCS/VRU — Contador de Ciclistas/Peatones | La variante es una vía rápida de vehículos, sin ciclovía ni aceras. No hay usuarios vulnerables que contar. |
| **CC-19** | UAS/UAV — Drones de Inspección | No hay activos de difícil acceso (torres, puentes altos) que requieran inspección aérea. |
| **CC-21** | CSG/IoT — Ciberseguridad de IoT | Es un componente de red y software, no de campo físico. Se gestiona desde el centro de control, no en la vía. |
| **CC-22** | PSV — Seguridad Ciudadana | No es una zona de alta inseguridad ni de vigilancia policial especial. La variante no requiere enlace directo con cámaras de seguridad pública. |
| **CC-25** | SME — Gestión de Medios Sociales | Es un componente de centro de control (gestión de redes sociales), no un equipo de campo. |
| **CC-26** | RSU — Comunicación V2X | Es una tecnología futurista (vehículos conectados) que no está madura en el mercado colombiano. No es base para el diseño actual. |
| **CC-27** | AVL/OBU — Control de Flota | No hay flota de emergencia propia del corredor estacionada en este tramo. La gestión de flota se hace desde el centro de control (CC-41). |
| **CC-28** | PGS — Gestión de Parqueaderos | No hay parqueaderos, estacionamientos ni zonas de descanso en la variante. |
| **CC-29** | SLP — Iluminación Solar | Hay acceso a red eléctrica convencional (zona periurbana), por lo que la iluminación solar no es necesaria. |
| **CC-30** | LHD — Detección de Incendio Lineal | No hay túneles ni infraestructura confinada donde un incendio requiera detección térmica especializada. |
| **CC-31** | AQM — Calidad del Aire | No es una zona de alta contaminación industrial o urbana densa que justifique monitoreo continuo de calidad del aire. |
| **CC-32** | WAR — Sala de Crisis | No es un centro de control regional ni un punto de comando de alto impacto. Es un tramo de corredor, no una sala de crisis. |
| **CC-36** | V2X-H — Nodos de Enlace Híbrido V2X | Como el CC-26, es tecnología futurista de comunicación vehicular que no aplica al diseño base actual. |
| **CC-37** | WDA — Detección de Fauna | No hay fauna silvestre de riesgo en una zona periurbana densamente poblada como Chía-Cota. |
| **CC-38** | ADS — Estación de Drones | No hay necesidad de patrullaje aéreo autónomo en una variante periurbana plana. Los drones se usan en zonas de difícil acceso o montaña. |
| **CC-39** | MSG — Micro-Red Inteligente | Hay red eléctrica estable de Cundinamarca. No se requiere generación propia aislada. |
| **CC-40** | D-TWN — Nodos de Procesamiento BIM | Es un componente de software/infraestructura digital, no un equipo de campo en la vía. |
| **CC-42** | SAT-B — Respaldo Satelital | Hay cobertura de red celular y fibra óptica. El respaldo satelital es para zonas extremadamente remotas sin conectividad terrestre. |

---

## 5. DISEÑO DE LA RED DE COMUNICACIONES

### 5.1 Arquitectura de Red

El Tramo 1 opera con una arquitectura de red **híbrida**: fibra óptica como medio principal y radio como respaldo. Esta arquitectura garantiza que, incluso si ocurre un corte de fibra, el centro de control sigue teniendo comunicación con los equipos críticos.

```
┌────────────────────────────────────────────────────────────┐
│                    TRAMO 1 — RED ITS                        │
├────────────────────────────────────────────────────────────┤
│                                                            │
│   ┌─────────┐     ┌─────────┐     ┌─────────┐            │
│   │ CCTV-01 │─────│ CCTV-02 │─────│ CCTV-03 │            │
│   │ VDS-01  │     │ ECS-01  │     │ AID-01  │            │
│   └────┬────┘     └────┬────┘     └────┬────┘            │
│        │               │               │                 │
│        └───────────────┼───────────────┘                 │
│                        │                                  │
│                   ┌────┴────┐                            │
│                   │  NODO   │◄──── FOC (fibra óptica)    │
│                   │ S-01    │      RCS (radio respaldo)    │
│                   │(Gabinete)                             │
│                   │  · UPS  │                            │
│                   │  · SW   │                            │
│                   └────┬────┘                            │
│                        │                                  │
│                        │ FOC troncal 7.1 km               │
│                        ▼                                  │
│   ┌─────────┐     ┌─────────┐     ┌─────────┐            │
│   │ CCTV-04 │─────│ CCTV-05 │─────│ CCTV-06 │            │
│   │ VDS-02  │     │ ECS-02  │     │ AID-02  │            │
│   └────┬────┘     └────┬────┘     └────┬────┘            │
│        │               │               │                 │
│        └───────────────┼───────────────┘                 │
│                        │                                  │
│                   ┌────┴────┐                            │
│                   │  NODO   │◄──── FOC (fibra óptica)    │
│                   │ S-02    │      RCS (radio respaldo)    │
│                   │(Gabinete)                             │
│                   │  · UPS  │                            │
│                   │  · SW   │                            │
│                   └────┬────┘                            │
│                        │                                  │
│                        │ FOC troncal                        │
│                        ▼                                  │
│                   ┌──────────┐                           │
│                   │   CCO    │  Centro de Control         │
│                   │ Regional │  Operaciones (E-LOG)      │
│                   └──────────┘                           │
│                                                            │
│   Leyenda: ─── = FOC (fibra)  ─ ─ = RCS (radio)           │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

### 5.2 Descripción de Nodos

| Nodo | Ubicación | Equipos conectados | Función |
|------|-----------|-------------------|---------|
| **Nodo S-01** | Glorieta Av. Chilacos (km 3.086) | CCTV-01, CCTV-02, CCTV-03, VDS-01, ECS-01, ECS-02, AID-01, DMS-01, SPD-01, VSL-01, LCS-01 (4 señales) | Agregación de subtramo 1.1, conexión a fibra troncal |
| **Nodo S-02** | Glorieta Norte Cota (km 7.134) | CCTV-04, CCTV-05, CCTV-06, VDS-02, ECS-03, ECS-04, AID-02, VSL-02, LCS-02 (4 señales) | Agregación de subtramo 1.2, conexión a fibra troncal y salida hacia Tramo 2 |

---

## 6. RESUMEN DE CANTIDADES Y DISTRIBUCIÓN

### 6.1 Tabla Consolidada de Equipos

| CC | Componente | Cantidad | Unidad | Subtramo 1.1 (km 0-3.086) | Subtramo 1.2 (km 3.086-7.134) | Observación |
|----|-----------|----------|--------|---------------------------|--------------------------------|-------------|
| **CC-01** | CCTV | 6 | Cámaras | 3 (PTZ, fija, PTZ) | 3 (fija, PTZ, PTZ) | Cobertura visual completa |
| **CC-02** | AID | 2 | Sistemas | 1 (entrada) | 1 (intermedia) | Detección automática de incidentes |
| **CC-03** | DMS/VMS | 1 | Panel | 1 (entrada Av. Pradilla) | 0 | Mensaje variable en entrada. Verificar si se necesita 2 |
| **CC-04** | ECS/SOS | 4 | Columnas | 2 (km 1.0, km 2.5) | 2 (km 4.0, km 6.5) | 1 cada 2 km alternados por sentido |
| **CC-05** | VDS/TDS | 4 | Sensores | 2 (por sentido) | 2 (por sentido) | Conteo y clasificación vehicular |
| **CC-06** | ESS/RWIS | 1 | Estación | 1 (km 1.5, opcional) | 0 | Meteorológica. Verificar si aplica |
| **CC-13** | SPD | 1 | Radar | 1 (km 0.5) | 0 | Radar pedagógico en entrada |
| **CC-14** | VSL | 2 | Señales | 1 (entrada) | 1 (entrada S-02) | Velocidad variable en entradas |
| **CC-20** | VIS/LGS | Variable | Luminarias | Según diseño vial | Según diseño vial | Verificar si hay alumbrado existente |
| **CC-23** | FOC | 7.1 | km | 3.086 km | 4.048 km | Fibra óptica troncal + 2 nodos |
| **CC-24** | RCS | 2 | Radios | 1 (Nodo S-01) | 1 (Nodo S-02) | Respaldo radial en cada nodo |
| **CC-33** | LCS/SIG | 8 | Señales | 4 (glorieta Av. Chilacos) | 4 (glorieta Norte Cota) | Control de carril en glorietas |
| **CC-34** | PSS | ~50 | Postes | ~25 | ~25 | Estimación: 1 poste cada 140m promedio |
| **CC-35** | UPS/EPS | 2 | Gabinetes | 1 (Nodo S-01) | 1 (Nodo S-02) | Respaldo energético por nodo |
| **CC-41** | E-LOG | 1 | Sistema | Remoto (CCO) | Remoto (CCO) | Gestión logística en centro de control |

**Total de CCs aplicables: 15 de 42**  
**Total de equipos de campo estimados: ~80 unidades** (sin contar tendido de fibra ni postes)

---

## 7. DUDAS TÉCNICAS Y PUNTOS DE VERIFICACIÓN

El diseño presentado tiene seis puntos que requieren confirmación por parte del equipo de ingeniería vial o del CEO para finalizar:

| # | Duda Técnica | Impacto en el Diseño | Recomendación | Prioridad |
|---|-------------|---------------------|---------------|-----------|
| **1** | **¿CC-06 ESS/RWIS?** — ¿Chía requiere estación meteorológica? | Si se confirma, se agrega 1 estación meteorológica en km 1.5. Si no, se elimina. | Chía tiene clima templado estable. Sugerencia: instalar 1 estación mínima como referencia regional. | Media |
| **2** | **¿CC-20 VIS/LGS?** — ¿La variante tiene alumbrado público? | Si hay alumbrado, no se instala VIS. Si no hay, se debe agregar iluminación LED en todo el tramo o al menos en zonas de equipos. | Verificar en planos de diseño vial. Si la variante es nueva, probablemente no tenga alumbrado. | Alta |
| **3** | **¿CC-03 DMS/VMS?** — ¿La vía es bidireccional con entradas separadas? | Si es bidireccional con 2 entradas, se necesitan 2 paneles DMS (1 por sentido). Si es unidireccional, basta con 1. | Verificar la configuración geométrica de la variante en los planos. | Alta |
| **4** | **Cantidad de CCTV** — ¿6 cámaras son suficientes para 7.1 km? | Si el estándar es 1 cada 500m, se necesitan 14 cámaras. Si es 1 cada 1 km, se necesitan 7. | Verificar el estándar de diseño ITS del proyecto (norma IDU o ANSV). | Media |
| **5** | **Tipo de glorietas** — ¿Son circulares tradicionales o semaforizadas? | Si son circulares tradicionales, el CC-33 (LCS) puede no aplicar. Si son semaforizadas, el LCS es crítico. | Verificar los planos de intersección de las glorietas de Av. Chilacos y Norte Cota. | Alta |
| **6** | **Tendido de FOC** — ¿Aéreo o subterráneo? | Impacta en costo, permisos y tiempo de instalación. Aéreo es más económico pero más expuesto a daños. | Verificar normativa del IDU y acuerdos de derechos de vía. | Media |

---

## 8. CONCLUSIONES Y RECOMENDACIONES

### 8.1 Perfil del Tramo 1

El Tramo 1 — Variante Chía - Glorieta Norte es un tramo de **baja complejidad técnica pero alta importancia operativa**. Es la puerta de entrada al corredor desde el norte, lo que significa que es el primer contacto del usuario con el sistema ITS. Una mala experiencia aquí (falta de información, accidente sin atención, congestión no gestionada) afecta la percepción de todo el corredor.

Su perfil de infraestructura es simple: vía plana, recta, sin túneles ni puentes. La única complejidad son las dos glorietas, que deben ser gestionadas inteligentemente para evitar cuellos de botella. Esto hace que el diseño ITS sea enfocado y eficiente: 15 componentes de 42, lo que representa un **ahorro estimado del 64%** en equipos de campo comparado con un diseño genérico de "instalar todo en todos los tramos".

### 8.2 Fortalezas del Diseño Propuesto

1. **Cobertura visual completa:** 6 cámaras garantizan que el centro de control vea todo el tramo, especialmente los puntos críticos (entradas y glorietas).
2. **Atención de emergencias garantizada:** 4 puntos de emergencia aseguran que ningún usuario esté a más de 1 km de un teléfono de auxilio.
3. **Gestión de velocidad:** La combinación de radar pedagógico (SPD) y velocidad variable (VSL) induce comportamientos seguros sin necesidad de sanciones.
4. **Redundancia de comunicaciones:** Fibra óptica + radio garantizan que el tramo nunca quede desconectado del centro de control.
5. **Sin sobredimensionamiento:** Solo se instala lo que la infraestructura realmente necesita, optimizando la inversión.

### 8.3 Riesgos del Diseño

1. **Densidad de cámaras:** Si 6 cámaras son insuficientes (estándar 1 cada 500m), quedarán zonas ciegas en el tramo.
2. **Glorietas no gestionadas:** Si las glorietas son circulares tradicionales y no se instala LCS, la congestión en horas pico puede ser un problema crónico.
3. **Falta de iluminación:** Si la variante no tiene alumbrado y no se instala VIS, el CCTV no tendrá visibilidad nocturna y los usuarios circularán en oscuridad.
4. **Corte de fibra:** Si el tendido es aéreo y no hay protección, un accidente o una obra de terceros puede dejar al tramo sin comunicación (aunque el radio RCS mitiga esto).

### 8.4 Próximos Pasos

1. **Validar las 6 dudas técnicas** con el equipo de diseño vial y el CEO.
2. **Ajustar cantidades** según las respuestas (ej. agregar CCTV, eliminar ESS, confirmar DMS, etc.).
3. **Generar el informe del Tramo 2** con la misma metodología.
4. **Consolidar los 15 informes** en un modelo financiero y un plan de implementación.

---

## ANEXOS

### Anexo A: Glosario de Siglas

| Sigla | Significado |
|-------|-------------|
| CCTV | Closed Circuit Television — Cámaras de vigilancia |
| AID | Automatic Incident Detection — Detección automática de incidentes |
| DMS | Dynamic Message Sign — Panel de mensaje variable |
| VMS | Variable Message Sign — Sinónimo de DMS |
| ECS | Emergency Call System — Sistema de llamada de emergencia |
| SOS | Save Our Souls — Sinónimo de ECS |
| VDS | Vehicle Detection System — Sistema de detección de vehículos |
| TDS | Traffic Detection System — Sinónimo de VDS |
| FOC | Fiber Optic Cable — Fibra óptica |
| RCS | Radio Communication System — Sistema de comunicación radial |
| LCS | Lane Control System — Sistema de control de carril |
| SIG | Signal — Señal |
| SPD | Speed Pedagogical Device — Radar pedagógico |
| VSL | Variable Speed Limit — Límite de velocidad variable |
| ESS | Environmental Sensor Station — Estación de sensores ambientales |
| RWIS | Road Weather Information System — Sistema de información meteorológica vial |
| VIS | Visual — Visual/Iluminación |
| LGS | Lighting System — Sistema de iluminación |
| PSS | Pole and Structure System — Postes y estructuras |
| UPS | Uninterruptible Power Supply — Sistema de respaldo energético |
| EPS | Emergency Power Supply — Sinónimo de UPS |
| E-LOG | Electronic Logistics — Logística electrónica |
| CCO | Centro de Control de Operaciones |
| PTZ | Pan-Tilt-Zoom — Cámara domo motorizada |
| IR | Infrared — Infrarrojo |
| VoIP | Voice over IP — Voz sobre IP |
| GIS | Geographic Information System — Sistema de información geográfica |
| AVL | Automatic Vehicle Location — Localización automática de vehículos |
| OBU | On-Board Unit — Unidad a bordo |
| V2X | Vehicle-to-Everything — Comunicación vehicular con todo |
| BIM | Building Information Modeling — Modelado de información de construcción |
| IoT | Internet of Things — Internet de las cosas |

### Anexo B: Catálogo Oficial de 42 CCs (Referencia)

Consultar documento: `CATALOGO-CC-OFICIAL-TRANSCONSULT.md` — InnovaDataCo.

---

*Documento elaborado por ZEUS — InnovaDataCo*  
*Proyecto: APP-CHIA-GIRARDOT — Estructuración ITS*  
*Versión: 1.0 — Borrador para validación*  
*Fecha: 2026-06-02*  
*Próxima revisión: Tramo 2 — Variante Cota*
