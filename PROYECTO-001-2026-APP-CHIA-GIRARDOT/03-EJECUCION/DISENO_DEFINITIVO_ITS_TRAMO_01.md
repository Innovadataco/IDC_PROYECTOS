# DISEÑO DEFINITIVO DE LA CAPA ITS
## Tramo 1 — Variante Chía – Glorieta Norte Variante Cota

**Proyecto:** Estructuración Sistema ITS — Corredor Chía-Girardot  
**Código:** PROYECTO-001-2026-APP-CHIA-GIRARDOT  
**Entregable:** E5-Diseños-ITS / Tramo-01 — Diseño Definitivo  
**Fecha:** 2026-06-02  
**Versión:** 1.0 — Diseño Definitivo

---

## RESUMEN EJECUTIVO

El presente documento establece el **diseño definitivo de la capa de equipos de Sistemas Inteligentes de Transporte (ITS)** para el Tramo 1 del Corredor Vial Chía-Girardot: la Variante Chía – Glorieta Norte Variante Cota. Este tramo, con una longitud total de 7.134 kilómetros distribuidos en dos subtramos, constituye la puerta de entrada norte del corredor y una variante rápida periurbana que evita el tránsito por el casco urbano de Chía.

El diseño se fundamenta en la información de la base de diseño definida en el modelo financiero del proyecto, la cual identifica el Sector I (Chía – Mondoñedo), la unidad funcional de tramos 1, 2 y 3, y asigna la responsabilidad de construcción, operación y mantenimiento a FONDECUN. La tipología de infraestructura del tramo — vía variante plana, sin túneles, sin peajes, sin puentes mayores, con dos glorietas como únicos puntos de intersección — condiciona la selección de quince componentes de campo que conforman la red mínima de operación para este segmento.

La solución ITS propuesta abarca: monitoreo visual mediante cámaras de videovigilancia (CC-01), detección automática de incidentes (CC-02), paneles de mensajería variable (CC-03), columnas de emergencia (CC-04), sensores de tráfico (CC-05), radares de velocidad (CC-13), señales de límite variable (CC-14), semáforos y señalización luminosa para glorietas (CC-33), postes de soporte (CC-34), sistemas de respaldo energético (CC-35), fibra óptica de comunicaciones (CC-23), radio enlace de respaldo (CC-24), sistema de logística de emergencias (CC-41), iluminación de seguridad en equipos (CC-20) y, condicionalmente, una estación meteorológica (CC-06) sujeta a validación climática del sector.

La red de comunicaciones se estructura en dos nodos — ubicados en las glorietas de Av. Chilacos y Norte de Cota — interconectados mediante fibra óptica con redundancia radial. El Centro de Control Regional, compartido con los tramos adyacentes, opera la logística de emergencias y la gestión del corredor en tiempo real.

---

## 1. BASE DE DISEÑO

### 1.1 Información del Modelo Financiero del Proyecto

La siguiente tabla resume la información de la base de diseño definida en el modelo financiero para el Tramo 1:

| Parámetro | Valor |
|-----------|-------|
| **Sector** | I. Sector 1 (Chía – Mondoñedo) |
| **Unidad Funcional (UF)** | Tramos 1, 2 y 3 — Conexión Chía – Funza (Av. Pradilla – Peaje La Tebaida) |
| **Tramo No.** | 1. |
| **Descripción del Tramo** | Variante Chía – Glorieta Norte Variante Cota (Av. Pradilla – Glorieta Norte Variante Cota) |
| **Longitud total** | 7.134 km |
| **Etapa del proyecto** | Construcción, Operación y Mantenimiento |
| **Entidad a cargo** | FONDECUN |
| **Alcance definido** | Construcción de Segunda Calzada (dos carriles); Puesta a punto, O&M |
| **Calzada Chía – Mondoñedo – Girardot** | 3.086 km (Subtramo 1.1); 4.048 km (Subtramo 1.2) |
| **Estado actual calzada** | Un carril existente; calzada existente (bidireccional) |
| **Calzada Girardot – Mondoñedo – Chía** | 3.086 km (Subtramo 1.1); 4.048 km (Subtramo 1.2) |
| **Observaciones** | FONDECUN adelanta estudios y diseños. No incluye costos de la intersección con la Troncal de los Andes, ejecutada por ANI (Accesos Norte 1). Subtramo 1.2 incluye construcción de segunda calzada y cicloruta. |

### 1.2 Ficha Técnica del Tramo

| Parámetro | Valor |
|-----------|-------|
| **Código** | T-01 |
| **Nombre** | Variante Chía – Glorieta Norte Variante Cota |
| **Tipo de vía** | Variante rápida periurbana |
| **Carriles estimados** | 2 por sentido (segunda calzada en construcción) |
| **Velocidad de diseño** | 80 km/h |
| **Topografía** | Plana (Altiplano Cundiboyacense) |
| **Zona climática** | Templada; Chía: 2,564 msnm, clima fresco seco |
| **Riesgo sísmico** | Bajo |
| **Riesgo geotécnico** | Bajo |
| **Riesgo hidrológico** | Bajo |
| **Acceso a red eléctrica** | Sí, zona periurbana |
| **Cobertura celular** | Sí, operadores móviles presentes |
| **Entorno** | Zona periurbana en expansión, desarrollos residenciales de estrato medio-alto, centros comerciales (Centro Chía), zonas de reserva para expansión urbana |

### 1.3 Descripción Geográfica y Operativa

El Tramo 1 se localiza en el extremo norte del corredor, en el área de influencia del municipio de Chía, uno de los centros poblados de mayor crecimiento en la Sabana de Bogotá en las últimas dos décadas. La variante tiene como propósito evitar que el tráfico de paso entre la Autopista Norte y el corredor sur entre al casco urbano de Chía, reduciendo congestión y tiempos de viaje.

**Punto de inicio:** Intersección con Av. Pradilla, principal vía de acceso a Chía desde la Autopista Norte.  
**Punto de fin:** Glorieta Norte de Cota, que marca la transición hacia el Tramo 2 (Variante Cota).  
**Entorno:** Zona periurbana en transición, con desarrollos residenciales, centros comerciales y zonas de reserva para expansión urbana. No se trata de una zona rural aislada, ni de un centro urbano denso. Es un territorio de borde que crece hacia la vía.

---

## 2. SUBTRAMOS

### 2.1 Subtramo 1.1 — Variante Chía (Av. Pradilla – Glorieta Av. Chilacos)

| Parámetro | Valor |
|-----------|-------|
| **Código** | T-01-S01 |
| **Longitud** | 3.086 km |
| **Inicio** | Intersección con Av. Pradilla, Chía |
| **Fin** | Glorieta de Av. Chilacos |
| **Porcentaje del tramo** | 43% |
| **Entidad a cargo** | FONDECUN |
| **Etapa** | Construcción, Operación y Mantenimiento |
| **Estado actual calzada** | Un carril existente; calzada existente (bidireccional) |
| **Alcance** | Construcción de Segunda Calzada (dos carriles); Puesta a punto, O&M |
| **Infraestructura principal** | Vía variante de dos carriles por sentido, una glorieta al final del subtramo |

**Características operativas:**

Este subtramo es la **puerta de entrada** al corredor desde el norte. Todo vehículo que venga de Bogotá, Zipaquirá o Chía hacia el sur (Cota, Funza, Mosquera, Girardot) pasará por aquí. La conexión con Av. Pradilla es crítica: es una vía con alta demanda vehicular, especialmente en horas pico y fines de semana (Chía es destino de compras y restaurantes para bogotanos). La glorieta de Av. Chilacos es un punto de conflicto potencial: vehículos que vienen de la variante, de Chía y de Cota convergen en este nudo. Sin una gestión inteligente del flujo, puede convertirse en cuello de botella. El terreno es completamente plano, sin restricciones geométricas que afecten la visibilidad o la velocidad. No hay curvas cerradas, ni túneles, ni puentes.

**Riesgos operativos identificados:** congestión en la glorieta por convergencia de flujos; accidentes por exceso de velocidad en tramos rectos; necesidad de comunicación rápida con servicios de emergencia en caso de siniestro.

### 2.2 Subtramo 1.2 — Conexión Chía-Cota (Glorieta Av. Chilacos – Glorieta Norte Cota)

| Parámetro | Valor |
|-----------|-------|
| **Código** | T-01-S02 |
| **Longitud** | 4.048 km |
| **Inicio** | Glorieta de Av. Chilacos |
| **Fin** | Glorieta Norte de Cota |
| **Porcentaje del tramo** | 57% |
| **Entidad a cargo** | FONDECUN |
| **Etapa** | Construcción, Operación y Mantenimiento |
| **Estado actual calzada** | Un carril existente; un carril existente |
| **Alcance** | Construcción de Segunda Calzada (dos carriles); Puesta a punto, O&M. Construcción de cicloruta. Operación y mantenimiento de la calzada nueva y antigua. |
| **Infraestructura principal** | Vía variante continua, una glorieta al final del subtramo |

**Características operativas:**

Este subtramo es la **transición** entre Chía y Cota. No tiene conexiones intermedias con otras vías importantes, lo que lo convierte en un tramo de paso puro. La glorieta Norte de Cota conecta con la variante de Cota (Tramo 2), que tiene un perfil más complejo al incluir paso urbano. El terreno es plano y sin restricciones; la vía es recta, con visibilidad despejada. La zona es menos densa que Chía, pero igualmente periurbana, con zonas de loteo y desarrollo residencial en expansión.

**Riesgos operativos identificados:** velocidad descontrolada por tramo recto sin puntos de referencia; falta de servicios de emergencia inmediatos en la vía; necesidad de gestión activa del límite de velocidad.

---

## 3. TIPOLOGÍA DE INFRAESTRUCTURA

### 3.1 Inventario de Elementos

| Elemento | Cantidad | Ubicación Precisa | Relevancia para ITS |
|----------|----------|-------------------|---------------------|
| **Glorietas (intersecciones)** | 2 | T-01-S01 km 3.086 (Av. Chilacos); T-01-S02 km 4.048 (Norte Cota) | Alta — son los únicos puntos de conflicto del tramo |
| **Vía variante** | 7.134 km | Todo el tramo | Media — requiere monitoreo continuo pero no tiene complejidad estructural |
| **Túneles** | 0 | N/A | No aplica |
| **Puentes mayores** | 0 | N/A | No aplica |
| **Peajes** | 0 | N/A | No aplica |
| **Paso urbano** | 0 | N/A | No aplica |
| **Zonas de fauna silvestre** | 0 | N/A | No aplica |
| **Taludes inestables / Riesgo geotécnico** | 0 | N/A | No aplica |
| **Riesgo hidrológico crítico** | 0 | N/A | No aplica |
| **Zonas de alta contaminación** | 0 | N/A | No aplica |

**Conclusión:** El Tramo 1 es una vía simple en su morfología: recta, plana, sin elementos estructurales complejos. Su única complejidad operativa radica en las dos glorietas, que son puntos de intersección donde múltiples flujos vehiculares convergen. El diseño ITS es por tanto limpio y enfocado: monitoreo, conteo, emergencias, gestión de velocidad y control de intersecciones.

---

## 4. COMPONENTES DE CAMPO DEFINIDOS

El diseño definitivo del Tramo 1 incorpora los siguientes componentes de campo del catálogo oficial, con las cantidades, ubicaciones y especificaciones técnicas establecidas:

### 4.1 CC-01 — CCTV: Cámaras de Videovigilancia

**Cantidad:** 6 unidades  
**Función:** Permitir al Centro de Control la observación visual del estado de la vía, detección de incidentes, verificación de alarmas y apoyo a la gestión de emergencias.  
**Justificación técnica:** El tramo es una vía variante de 7.1 km sin presencia de personal de operación en campo. El CCTV constituye el único medio de visión que tiene el centro de control para conocer en tiempo real qué ocurre en la calzada: accidentes, vehículos detenidos, congestión, condiciones climáticas, estado de la infraestructura. Sin cámaras, el corredor opera a ciegas.

**Distribución definitiva:**

| Unidad | Tipo | Ubicación | Coordenada aproximada (km) | Función específica |
|--------|------|-----------|---------------------------|-------------------|
| CCTV-01 | PTZ | Entrada Av. Pradilla | 0.0 | Control del flujo de ingreso desde la Autopista Norte; detección de vehículos en contravía |
| CCTV-02 | Fija | Subtramo 1.1, punto intermedio | 1.5 | Monitoreo de tráfico en tramo recto; respaldo de AID-01 |
| CCTV-03 | PTZ | Glorieta Av. Chilacos | 3.086 | Gestión visual del nudo vial; cobertura de 360° de la glorieta |
| CCTV-04 | Fija | Inicio Subtramo 1.2 | 3.2 | Monitoreo de transición entre subtramos |
| CCTV-05 | PTZ | Subtramo 1.2, punto intermedio | 5.5 | Monitoreo de tráfico en tramo de paso puro |
| CCTV-06 | PTZ | Glorieta Norte Cota | 7.134 | Gestión visual del nudo vial; transición hacia Tramo 2 |

**Especificación técnica:** Cámaras IP PTZ (domo motorizado) para glorietas y entradas, con zoom óptico 30x, visión nocturna IR 100 m, protección IP66, resolución mínima 2 MP Full HD, compresión H.265. Cámaras fijas para puntos intermedios, lente varifocal 2.8–12 mm, resolución 2 MP, protección IP66. Integración ONVIF Profile S/G con el VMS del Centro de Control.

### 4.2 CC-02 — AID: Detección Automática de Incidentes

**Cantidad:** 2 sistemas  
**Función:** Detectar automáticamente eventos anómalos en la vía mediante análisis de video, sin intervención del operador.  
**Justificación técnica:** El operador de CCTV no puede monitorear seis cámaras de forma continua las 24 horas. El AID procesa las imágenes de las cámaras y detecta eventos: vehículo detenido, sentido contrario, peatón en calzada, humo, congestión, objeto en vía. Reduce el tiempo de detección de minutos a segundos.

**Distribución definitiva:**

| Sistema | Ubicación | Cámaras asociadas | Eventos detectados |
|---------|-----------|-------------------|-------------------|
| AID-01 | Subtramo 1.1, km 1.5 | CCTV-01, CCTV-02, CCTV-03 | Vehículo detenido, sentido contrario, conglomeración, peatón en vía, objeto anómalo |
| AID-02 | Subtramo 1.2, km 5.5 | CCTV-04, CCTV-05, CCTV-06 | Vehículo detenido, velocidad anómala, congestión, pérdida de visibilidad |

**Especificación técnica:** Software de análisis de video basado en inteligencia artificial, desplegado en servidor edge o en el Centro de Control. Debe soportar las categorías de evento: vehículo detenido, velocidad anómala, sentido contrario, conglomeración, peatón/animal en vía, pérdida de visibilidad (humo/niebla). Tiempo de detección menor a 10 segundos. Integración con el VMS y el sistema de gestión de eventos.

### 4.3 CC-03 — DMS/VMS: Paneles de Mensajería Variable

**Cantidad:** 1 panel  
**Función:** Informar al conductor en tiempo real sobre condiciones de la vía, incidentes, tiempos de recorrido, restricciones y mensajes de seguridad.  
**Justificación técnica:** La entrada a la variante desde Av. Pradilla es un punto crítico donde los conductores deciden su ruta. Un panel informativo antes de la bifurcación permite comunicar el estado del corredor (tramos libres, congestión, cierres), optimizando la demanda y mejorando la seguridad. Dentro de la variante, un único panel es suficiente dado que no hay bifurcaciones intermedias.

**Distribución definitiva:**

| Unidad | Ubicación | Tipo | Mensajes prioritarios |
|--------|-----------|------|----------------------|
| DMS-01 | Av. Pradilla, antes de la entrada a la variante (km 0.0, sentido sur) | Full matrix LED, 3 líneas x 12 caracteres | Estado del corredor, tiempos de recorrido, alertas de incidentes, restricciones de velocidad |

**Especificación técnica:** Panel de matriz LED full-matrix, visibilidad mínima 200 m, ángulo de visión 30°, protección IP65, control remoto vía protocolo NTCIP o vendor-specific, integración con el sistema central de gestión de contenido. Alimentación 110–240 V AC con respaldo UPS.

### 4.4 CC-04 — ECS/SOS: Columnas de Emergencia

**Cantidad:** 4 columnas  
**Función:** Permitir al usuario de la vía comunicarse directamente con el Centro de Control en caso de emergencia, avería o situación de riesgo.  
**Justificación técnica:** En un tramo de 7.1 km sin presencia de personal ni servicios de emergencia inmediatos, las columnas SOS son el único canal de comunicación directo usuario-operador. Un usuario accidentado, con vehículo averiado o testigo de un siniestro necesita un medio rápido de contacto.

**Distribución definitiva:**

| Unidad | Ubicación (km) | Sentido | Cobertura aproximada |
|--------|---------------|---------|---------------------|
| ECS-01 | 0.8 | Chía → Cota | Primer kilómetro del subtramo 1.1 |
| ECS-02 | 2.5 | Cota → Chía | Segundo kilómetro del subtramo 1.1 |
| ECS-03 | 4.0 | Chía → Cota | Primer kilómetro del subtramo 1.2 |
| ECS-04 | 6.5 | Cota → Chía | Segundo kilómetro del subtramo 1.2 |

**Especificación técnica:** Columna de emergencia con botón de pánico, interfono bidireccional de alta fidelidad, indicador LED de estado, altavoz de respuesta, cámara integrada (opcional, para verificar la situación antes de despachar ayuda), alimentación solar + batería con respaldo 72 h, protección IP65, conexión vía fibra óptica o radio. Altura 1.2 m, acabado anticorrosivo.

### 4.5 CC-05 — VDS/TDS: Sensores de Tráfico

**Cantidad:** 4 sensores  
**Función:** Medir en tiempo real el volumen vehicular, la ocupación, la velocidad y la clasificación de vehículos por categoría.  
**Justificación técnica:** Los datos de tráfico son la base de la operación inteligente: sin saber cuántos vehículos pasan, a qué velocidad y en qué proporción (livianos, buses, camiones), no es posible dimensionar la infraestructura, programar semáforos, informar a los usuarios ni planificar mantenimiento.

**Distribución definitiva:**

| Unidad | Ubicación (km) | Sentido | Parámetros medidos |
|--------|---------------|---------|-------------------|
| VDS-01 | 0.5 | Chía → Cota | Volumen, velocidad, ocupación, clasificación |
| VDS-02 | 3.0 | Cota → Chía | Volumen, velocidad, ocupación, clasificación |
| VDS-03 | 3.5 | Chía → Cota | Volumen, velocidad, ocupación, clasificación |
| VDS-04 | 7.0 | Cota → Chía | Volumen, velocidad, ocupación, clasificación |

**Especificación técnica:** Sensor de detección por radar doppler o LiDAR, alcance mínimo 50 m, precisión de velocidad ±3%, clasificación en 5 categorías (liviano, bus, camión ligero, camión pesado, motocicleta), comunicación vía RS-485/Ethernet, alimentación 12/24 V DC, protección IP65. Integración con el sistema central de gestión de tráfico.

### 4.6 CC-06 — ESS/RWIS: Estación Meteorológica

**Cantidad:** 1 estación (condicional)  
**Función:** Medir temperatura, humedad, velocidad y dirección del viento, precipitación, visibilidad y estado de la calzada (húmeda/seca/hielo).  
**Justificación técnica:** Chía se ubica a 2,564 msnm con clima fresco seco. La zona no presenta niebla recurrente ni riesgo de hielo significativo. Sin embargo, dado que es el tramo más alto del corredor, una estación meteorológica proporciona datos de referencia para la predicción de condiciones en los tramos de montaña posteriores. Su instalación queda **condicionada** a la validación del patrón climático del sector durante la fase de ingeniería de detalle.

**Distribución definitiva:**

| Unidad | Ubicación (km) | Estado |
|--------|---------------|--------|
| ESS-01 | 3.5 (punto medio del tramo) | **Condicional** — confirmar en ingeniería de detalle |

**Especificación técnica:** Estación meteorológica integrada con sensores de temperatura (-40 a +60 °C, ±0.3 °C), humedad relativa (0–100%, ±3%), viento (0–60 m/s, ±0.5 m/s), precipitación (tipping bucket 0.2 mm/resolución), visibilidad (0–10 km, ±10%), sensor de estado de calzada (húmedo/seco/hielo/helada). Comunicación vía Ethernet/celular, alimentación solar + batería. Integración con el sistema central de información meteorológica.

### 4.7 CC-13 — SPD: Radar de Velocidad

**Cantidad:** 1 radar  
**Función:** Medir la velocidad de los vehículos y mostrar al conductor su velocidad actual para inducir una reducción conductual.  
**Justificación técnica:** La variante Chía es una vía rápida recta sin puntos de referencia visuales. Los conductores tienden a exceder el límite de 80 km/h. Un radar de velocidad con display informativo en la entrada induce la autoregulación sin necesidad de sanción inmediata.

**Distribución definitiva:**

| Unidad | Ubicación (km) | Tipo |
|--------|---------------|------|
| SPD-01 | 0.5 (entrada a la variante desde Av. Pradilla) | Radar doppler + display LED |

**Especificación técnica:** Radar doppler de onda continua, rango 10–250 km/h, precisión ±1 km/h, display LED de 2 dígitos visibles a 100 m, protección IP65, alimentación 110–240 V AC con respaldo UPS. Integración con el sistema de gestión de velocidad.

### 4.8 CC-14 — VSL: Señal de Límite de Velocidad Variable

**Cantidad:** 2 señales  
**Función:** Cambiar dinámicamente el límite de velocidad según condiciones de tráfico, clima, incidentes u obras en la vía.  
**Justificación técnica:** Permite adaptar el límite de velocidad a las condiciones reales: reducir a 60 km/h en caso de congestión, niebla o incidente; restablecer a 80 km/h cuando las condiciones son normales. Proactivo, no reactivo.

**Distribución definitiva:**

| Unidad | Ubicación (km) | Sentido |
|--------|---------------|---------|
| VSL-01 | 0.3 | Chía → Cota |
| VSL-02 | 3.3 | Chía → Cota (inicio subtramo 1.2) |

**Especificación técnica:** Señal LED circular de límite de velocidad, diámetro 300 mm o 400 mm según norma de señalización colombiana, visibilidad mínima 200 m, protección IP65, control remoto vía NTCIP o protocolo propietario, alimentación 110–240 V AC con respaldo UPS. Integración con el sistema central de gestión de velocidad.

### 4.9 CC-20 — VIS/LGS: Iluminación de Seguridad

**Cantidad:** Variable (según existencia de alumbrado público)  
**Función:** Garantizar la visibilidad de los equipos ITS y de la calzada durante condiciones de baja luminosidad.  
**Justificación técnica:** Los equipos CCTV, DMS, VSL, ECS y PSS requieren un nivel mínimo de iluminación para operar efectivamente durante la noche. Si la vía no cuenta con alumbrado público existente, se debe instalar iluminación de seguridad en los puntos donde están ubicados los equipos.

**Distribución definitiva:**

| Tipo | Ubicaciones | Cantidad estimada |
|------|------------|-------------------|
| Luminarias en postes PSS | En cada poste que sostiene CCTV, DMS, VSL, ECS | ~18 luminarias |
| Iluminación de glorieta | Glorieta Av. Chilacos, Glorieta Norte Cota | 2 sistemas |

**Nota:** La necesidad y cantidad definitiva de luminarias se confirmará durante la ingeniería de detalle, verificando la existencia o no de alumbrado público municipal en cada punto de equipo.

**Especificación técnica:** Luminaria LED de 100–150 W, flujo luminoso 12,000–18,000 lm, temperatura de color 4000 K, índice de reproducción cromática >70, protección IP66, vida útil >50,000 h, controlador con protección sobretensión. Opcional: control remoto de encendido/apagado y atenuación.

### 4.10 CC-23 — FOC: Fibra Óptica de Comunicaciones

**Cantidad:** 7.2 km de tendido  
**Función:** Transportar datos, video y voz entre los equipos de campo y el Centro de Control.  
**Justificación técnica:** La fibra óptica es el medio de comunicación principal del corredor. Todos los equipos ITS (CCTV, VDS, ECS, DMS, VSL, AID) generan datos que deben llegar al Centro de Control en tiempo real. La fibra garantiza ancho de banda, latencia baja e inmunidad a interferencias electromagnéticas.

**Distribución definitiva:**

| Tramo de tendido | Longitud | Tipo de fibra | Capacidad |
|-------------------|----------|---------------|-----------|
| Nodo S-01 (Av. Pradilla) → Nodo S-02 (Glorieta Av. Chilacos) | 3.1 km | Monomodo G.652.D, 12 fibras | 10 Gbps por fibra |
| Nodo S-02 (Glorieta Av. Chilacos) → Nodo S-03 (Glorieta Norte Cota) | 4.1 km | Monomodo G.652.D, 12 fibras | 10 Gbps por fibra |
| **Total** | **7.2 km** | — | — |

**Especificación técnica:** Cable de fibra óptica monomodo ITU-T G.652.D, 12 fibras (mínimo), con elementos de resistencia a tracción y armadura de acero galvanizado para instalación subterránea o aérea según diseño vial. Conectores LC/UPC en patch panels. Pendiente definir: tendido aéreo (postes existentes) o subterráneo (ducto en corredor vial).

### 4.11 CC-24 — RCS: Radio Enlace de Comunicaciones

**Cantidad:** 2 radios  
**Función:** Proveer un canal de comunicación alternativo si se produce un corte en la fibra óptica.  
**Justificación técnica:** La redundancia de comunicaciones es crítica. Un corte de fibra por obra civil, accidente o vandalismo deja al tramo sin comunicación. El radio enlace mantiene la conectividad mínima (alarmas, ECS, VDS) mientras se restaura la fibra.

**Distribución definitiva:**

| Unidad | Ubicación | Cobertura |
|--------|-----------|-----------|
| RCS-01 | Nodo S-02 (Glorieta Av. Chilacos) | Toda la variante Chía y conexión con Tramo 2 |
| RCS-02 | Nodo S-03 (Glorieta Norte Cota) | Toda la conexión Chía-Cota y conexión con Tramo 2 |

**Especificación técnica:** Radio enlace punto-multipunto o punto-a-punto en banda licenciada (ej. 5.8 GHz o banda sub-6 GHz según disponibilidad del espectro en Colombia), throughput mínimo 100 Mbps, alcance visual >5 km, antena direccional de alto ganancia (18 dBi), protección IP65, alimentación con respaldo UPS. Integración con la red de comunicaciones del corredor.

### 4.12 CC-33 — LCS/SIG: Señalización Luminosa de Control de Tráfico

**Cantidad:** 8 señales (4 por glorieta)  
**Función:** Gestionar el flujo vehicular en las glorietas mediante semáforos o señales luminosas de carril, priorizando flujos principales y coordinando la entrada de vehículos.  
**Justificación técnica:** Las dos glorietas del tramo son los únicos puntos de conflicto. Sin una gestión activa del flujo, la convergencia de vehículos de la variante, de Chía y de Cota genera cuello de botella en horas pico. La señalización luminosa permite asignar turnos, priorizar la variante y coordinar con el Tramo 2.

**Distribución definitiva:**

| Glorieta | Unidad | Tipo | Función |
|----------|--------|------|---------|
| **Glorieta Av. Chilacos** | LCS-01 | Semáforo vehicular 3 fases | Control del flujo de la variante (prioridad) |
| | LCS-02 | Semáforo vehicular 3 fases | Control del flujo de Chía (secundario) |
| | LCS-03 | Semáforo vehicular 3 fases | Control del flujo de Cota (secundario) |
| | LCS-04 | Señal de carril/giro | Indicación de giro permitido/prohibido |
| **Glorieta Norte Cota** | LCS-05 | Semáforo vehicular 3 fases | Control del flujo de la variante (prioridad) |
| | LCS-06 | Semáforo vehicular 3 fases | Control del flujo de Cota (secundario) |
| | LCS-07 | Semáforo vehicular 3 fases | Control del flujo hacia Tramo 2 (secundario) |
| | LCS-08 | Señal de carril/giro | Indicación de giro permitido/prohibido |

**Especificación técnica:** Semáforo vehicular LED de 200 mm o 300 mm según norma colombiana, visibilidad mínima 150 m, protección IP65, controlador con capacidad de coordinación centralizada (plan de tiempos descargable desde el Centro de Control), detección de conflicto, respaldo de reloj interno. Alimentación 110–240 V AC con respaldo UPS. Integración con el sistema central de gestión de tráfico urbano.

### 4.13 CC-34 — PSS: Postes de Soporte de Equipos

**Cantidad:** ~50 postes  
**Función:** Sostener físicamente cámaras, paneles DMS, radares, señales VSL, antenas de radio y luminarias.  
**Justificación técnica:** Todos los equipos ITS que requieren altura y visibilidad necesitan un poste estructuralmente diseñado para soportar cargas de viento, peso del equipo y vibraciones.

**Distribución definitiva:**

| Tipo de poste | Cantidad estimada | Equipos soportados |
|---------------|-------------------|-------------------|
| Poste tubular metálico 6 m | 30 | Cámaras CCTV fijas, VDS, ECS, SPD |
| Poste tubular metálico 10 m | 12 | Cámaras PTZ, DMS, VSL, antenas RCS |
| Poste de iluminación 8 m | 8 | Luminarias VIS/LGS |

**Especificación técnica:** Poste tubular de acero galvanizado en caliente, altura según función (6 m, 8 m, 10 m), carga de diseño para viento de 120 km/h, base de anclaje con pernos de fundición, puerta de inspección para conexiones eléctricas y de fibra, protección anticorrosiva (zincado + pintura epóxica), vida útil >25 años. Cimentación según estudio geotécnico del punto.

### 4.14 CC-35 — UPS/EPS: Sistema de Respaldo Energético

**Cantidad:** 2 gabinetes  
**Función:** Garantizar la continuidad de operación de los equipos ITS durante cortes de energía eléctrica.  
**Justificación técnica:** Los equipos críticos (CCTV, VDS, ECS, comunicaciones) no pueden detenerse cuando se va la energía. Un usuario que presione SOS, una cámara que grabe un incidente o un sensor que cuente tráfico deben funcionar siempre.

**Distribución definitiva:**

| Unidad | Ubicación | Equipos respaldados |
|--------|-----------|---------------------|
| UPS-01 | Nodo S-02 (Glorieta Av. Chilacos) | CCTV-03, VDS-02, ECS-02, LCS-01 a LCS-04, AID-01, RCS-01 |
| UPS-02 | Nodo S-03 (Glorieta Norte Cota) | CCTV-06, VDS-04, ECS-04, LCS-05 a LCS-08, AID-02, RCS-02 |

**Especificación técnica:** Gabinete UPS de doble conversión online, capacidad 10–15 kVA según carga calculada, autonomía mínima 4 horas (baterías selladas de plomo-ácido o litio según vida útil deseada), protección IP55, ventilación forzada con filtro, monitorización remota vía SNMP/Modbus, bypass de mantenimiento. Incluye distribución eléctrica secundaria para cada equipo.

### 4.15 CC-41 — E-LOG: Sistema de Logística de Emergencias

**Cantidad:** 1 sistema (compartido con otros tramos del Sector I)  
**Función:** Coordinar la respuesta a emergencias vinculando al Centro de Control con grúas, ambulancias, bomberos, policía y equipos de mantenimiento del corredor.  
**Justificación técnica:** Detectar un incidente no es suficiente; hay que resolverlo. El sistema E-LOG gestiona la asignación de recursos de emergencia: qué grúa está más cerca, qué ruta debe tomar la ambulancia, cuánto tiempo tardará en llegar, quién tiene la orden de trabajo de mantenimiento.

**Distribución definitiva:**

| Componente | Ubicación | Función |
|------------|-----------|---------|
| Módulo E-LOG Central | Centro de Control Regional Sector I (compartido Tramos 1–3) | Gestión de recursos de emergencia para todo el sector |
| Terminales móviles | Grúas, ambulancias, patrullas, cuadrillas de mantenimiento | Recepción de órdenes y reporte de estado |

**Especificación técnica:** Plataforma software de gestión de flotas y emergencias, integración con GIS del corredor, algoritmo de asignación de recursos por proximidad y disponibilidad, comunicación vía radio/celular/tablet, registro histórico de tiempos de respuesta. Módulo de reportes de cumplimiento ANSV.

---

## 5. RED DE COMUNICACIONES Y NODOS

### 5.1 Arquitectura de Comunicaciones

El Tramo 1 se estructura en una red de dos nodos de comunicación, interconectados mediante fibra óptica con radio enlace de respaldo.

| Nodo | Ubicación | Equipos conectados | Función |
|------|-----------|-------------------|---------|
| **S-01** | Entrada Av. Pradilla (km 0.0) | CCTV-01, VDS-01, SPD-01, DMS-01, ECS-01, VSL-01 | Punto de acceso norte al corredor; inicio del tendido de fibra |
| **S-02** | Glorieta Av. Chilacos (km 3.086) | CCTV-02, CCTV-03, VDS-02, ECS-02, LCS-01–04, AID-01, UPS-01, RCS-01 | Nodo intermedio y de redundancia; conexión con Subtramo 1.2 |
| **S-03** | Glorieta Norte Cota (km 7.134) | CCTV-04, CCTV-05, CCTV-06, VDS-04, ECS-04, LCS-05–08, AID-02, UPS-02, RCS-02 | Nodo de frontera; transición hacia Tramo 2 (Variante Cota) |

### 5.2 Medios de Comunicación

| Medio | Tendido | Función |
|-------|---------|---------|
| **FOC — Fibra Óptica** | 7.2 km, monomodo 12 fibras, S-01 → S-02 → S-03 | Transporte principal de datos, video y voz |
| **RCS — Radio Enlace** | 2 radios, S-02 ↔ S-03 + conexión con Tramo 2 | Respaldo ante corte de fibra |
| **Ethernet/Cobre** | Dentro de cada nodo (hasta 100 m) | Conexión de equipos al switch local |

**Pendiente de definición en ingeniería de detalle:** modalidad de tendido de fibra (aéreo en postes existentes vs. subterráneo en ducto vial); certificación de postes existentes para carga adicional de fibra y equipos; permisos de paso con FONDECUN y municipios.

---

## 6. CONSOLIDADO DE CANTIDADES

### 6.1 Resumen por Componente

| CC | Nombre del Componente | Cantidad | Unidad |
|----|----------------------|----------|--------|
| CC-01 | CCTV: Cámaras de Videovigilancia | 6 | Unidades |
| CC-02 | AID: Detección Automática de Incidentes | 2 | Sistemas |
| CC-03 | DMS/VMS: Paneles de Mensajería Variable | 1 | Panel |
| CC-04 | ECS/SOS: Columnas de Emergencia | 4 | Columnas |
| CC-05 | VDS/TDS: Sensores de Tráfico | 4 | Sensores |
| CC-06 | ESS/RWIS: Estación Meteorológica | 1 (condicional) | Estación |
| CC-13 | SPD: Radar de Velocidad | 1 | Radar |
| CC-14 | VSL: Señal de Límite de Velocidad Variable | 2 | Señales |
| CC-20 | VIS/LGS: Iluminación de Seguridad | ~18 + 2 | Luminarias |
| CC-23 | FOC: Fibra Óptica de Comunicaciones | 7.2 | km |
| CC-24 | RCS: Radio Enlace de Comunicaciones | 2 | Radios |
| CC-33 | LCS/SIG: Señalización Luminosa de Control | 8 | Señales |
| CC-34 | PSS: Postes de Soporte | ~50 | Postes |
| CC-35 | UPS/EPS: Sistema de Respaldo Energético | 2 | Gabinetes |
| CC-41 | E-LOG: Sistema de Logística de Emergencias | 1 (compartido) | Sistema |

### 6.2 Resumen por Subtramo

| Equipo | T-01-S01 (3.086 km) | T-01-S02 (4.048 km) | Total |
|--------|---------------------|---------------------|-------|
| CCTV | 3 | 3 | 6 |
| AID | 1 | 1 | 2 |
| DMS/VMS | 1 | 0 | 1 |
| ECS/SOS | 2 | 2 | 4 |
| VDS/TDS | 2 | 2 | 4 |
| SPD | 1 | 0 | 1 |
| VSL | 1 | 1 | 2 |
| LCS/SIG | 4 | 4 | 8 |
| UPS/EPS | 1 | 1 | 2 |
| RCS | 1 | 1 | 2 |
| FOC | 3.1 km | 4.1 km | 7.2 km |
| PSS | ~22 | ~28 | ~50 |
| ESS/RWIS | 0 (o 1 condicional) | 0 | 0–1 |
| VIS/LGS | ~8 + 1 | ~10 + 1 | ~18 + 2 |
| E-LOG | 1 (compartido) | 1 (compartido) | 1 |

---

## 7. DEFINICIONES PENDIENTES PARA INGENIERÍA DE DETALLE

Las siguientes definiciones quedan pendientes para la fase de ingeniería de detalle, una vez se cuente con los planos constructivos actualizados y la confirmación de FONDECUN:

| # | Definición pendiente | Información requerida | Impacto en el diseño |
|---|---------------------|----------------------|---------------------|
| 1 | Existencia de alumbrado público en la variante | Confirmación del diseño vial / FONDECUN | Si existe: no se instala VIS/LGS en esos tramos. Si no existe: se instalan ~18 luminarias. |
| 2 | Justificación de estación meteorológica en Chía | Datos climáticos históricos del sector (IDEAM) | Si no se justifica: se elimina CC-06. Si se justifica: se confirma en km 3.5. |
| 3 | Densidad de cámaras según estándar de diseño | Norma ANSV o estándar del proyecto (ej. cada 500 m, 1 km o 2 km) | Si el estándar pide más cámaras: se incrementa CC-01. Si pide menos: se ajusta. |
| 4 | Modalidad de tendido de fibra óptica | Definición del diseño vial (aéreo vs. subterráneo) | Afecta costo de instalación, permisos y tiempo de ejecución. |
| 5 | Tipo de glorietas (circulares tradicionales vs. semaforizadas) | Plano geométrico de intersecciones | Si son circulares sin semáforos: LCS/SIG puede ajustarse a señales de yield/giro únicamente. |
| 6 | Configuración de calzada en segunda carril | Confirmación de número de carriles por sentido en segunda calzada | Afecta el número de detectores VDS y la cobertura de cámaras. |

---

## 8. REFERENCIAS

| Documento | Código | Fecha | Descripción |
|-----------|--------|-------|-------------|
| Modelo Financiero V1 | MF-APP-CHIA-2026 | 2026 | Base de diseño con sectores, tramos, subtramos, entidades y longitudes |
| Catálogo Oficial de Componentes de Campo | CC-TRANSCONSULT-2026 | 2026-04-30 | 42 CCs definidos para el corredor (CC-01 al CC-42) |
| Informe Técnico Tramo 1 (borrador) | IT-01-ITS-2026 | 2026-06-02 | Análisis preliminar de tipología y mapeo de 42 CCs |
| Diseños del Corredor | Carpeta Drive 1uMBVthOp42mbVp2Exbat3QGR2a98wuFv | 2026 | Planos CAD/KMZ de las 40 secciones del corredor |

---

*Documento de diseño definitivo de la capa ITS para el Tramo 1 del Corredor Chía-Girardot. Elaborado conforme a la base de diseño definida en el modelo financiero del proyecto, el catálogo oficial de componentes de campo y los planos del corredor.*

**PROYECTO-001-2026-APP-CHIA-GIRARDOT / E5-Diseños-ITS / Tramo-01**  
**Versión 1.0 — Diseño Definitivo**  
**2026-06-02**
