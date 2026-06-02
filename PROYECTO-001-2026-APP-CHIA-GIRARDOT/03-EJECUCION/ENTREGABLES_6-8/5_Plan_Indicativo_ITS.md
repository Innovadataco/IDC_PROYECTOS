

## 5.5 Despliegue Detallado por Unidad Funcional

### 5.5.1 Metodología de Despliegue Detallado

El despliegue detallado por Unidad Funcional constituye la materialización operativa del Plan Indicativo. Cada UF se descompone en subtramos o secciones homogéneas donde la tipología vial, la densidad de tráfico y el perfil de riesgo son consistentes. Para cada sección, se define el conjunto exacto de componentes, su ubicación aproximada por kilómetro, la justificación técnica de su presencia y la interacción con otros componentes del sistema.

Este despliegue no es una ingeniería de detalle con planos de construcción, sino una **propuesta técnica de definición** que establece los límites de lo que se requiere, permitiendo al futuro Concesionario desarrollar la ingeniería de detalle con flexibilidad técnica, siempre dentro de los parámetros de cantidad, ubicación y funcionalidad definidos en este capítulo. La trazabilidad entre este despliegue y la arquitectura del Entregable 1 se mantiene mediante la correlación de cada componente con los servicios ITS y funciones técnicas que soporta.

### 5.5.2 UF 1 — Variante Chía (3.1 km, FONDECUN)

**Caracterización:** Tramo urbano de alta densidad, con 6 intersecciones (3 glorietas), TPDA ~45,000 vehículos, zona escolar identificada, sin energía en extremos. Tipología dominante: Urbano (Paquete 4 Avanzado).

**Despliegue por Subtramo:**

| Subtramo | Km | Tipo | Componentes | Justificación |
|----------|-----|------|-------------|---------------|
| 1.1 | 0.0-0.5 | Glorieta Norte | CCTV-INT PTZ, VDS-INT, DMS-INT, PED, ILU, Gabinete | Intersección principal con alta conflictividad |
| 1.2 | 0.5-1.0 | Tramo urbano | CCTV fija, VDS bucle, DMS puntos, SOS | Vigilancia continua, acceso a zona urbana |
| 1.3 | 1.0-1.5 | Zona escolar | CCTV-ZE, SEM, PED, DMS-ZE, ILU | Protección peatonal activa, velocidad reducida |
| 1.4 | 1.5-2.0 | Glorieta Central | CCTV-INT PTZ, VDS-INT, DMS-INT, Gabinete | Intersección con alta conflictividad |
| 1.5 | 2.0-2.5 | Tramo urbano | CCTV fija, VDS bucle, DMS puntos, SOS | Vigilancia continua |
| 1.6 | 2.5-3.1 | Glorieta Sur | CCTV-INT PTZ, VDS-INT, DMS-INT, Gabinete | Intersección principal con variante Cota |

**Consolidado UF 1:**
- CCTV-INT PTZ: 3 unidades
- CCTV fija: 2 unidades
- CCTV-ZE: 1 unidad
- VDS-INT: 3 unidades
- VDS bucle: 2 unidades
- DMS-INT: 3 unidades
- DMS puntos: 2 unidades
- DMS-ZE: 1 unidad
- PED: 2 unidades
- ILU: 2 unidades
- SEM: 1 unidad
- SOS: 2 unidades
- Gabinete de control: 3 unidades
- **Total componentes de campo: 25 unidades**

### 5.5.3 UF 3 — Cota – La Tebaida (6.0 km, ICCU)

**Caracterización:** Tramo arterial con peaje La Tebaida en km 4.2, 1 puente sobre río, TPDA ~38,000 vehículos, 5 intersecciones. Tipología: Arterial + Peaje (Paquete 2 Avanzado + Paquete 6).

**Despliegue por Subtramo:**

| Subtramo | Km | Tipo | Componentes | Justificación |
|----------|-----|------|-------------|---------------|
| 3.1 | 0.0-1.5 | Arterial | CCTV PTZ, VDS video, DMS completo, SOS, Gabinete | Monitoreo de tráfico arterial continuo |
| 3.2 | 1.5-3.0 | Arterial | CCTV fija, VDS radar, DMS puntos, SOS, Gabinete | Respaldo de detección, información básica |
| 3.3 | 3.0-4.5 | Peaje La Tebaida | AVI/ETC, ALPR, WIM, CCTV-P, DMS-P, Gabinete integrado | Integración con sistema FONDECUN, fiscalización de peso y placas |
| 3.4 | 4.5-6.0 | Puente + Arterial | CCTV fija, VDS radar, RWIS, DMS completo, SOS, Gabinete | Monitoreo estructural del puente, detección climática |

**Consolidado UF 3:**
- CCTV PTZ: 1 unidad
- CCTV fija: 2 unidades
- CCTV-P: 2 unidades (fiscalización peaje)
- VDS video: 1 unidad
- VDS radar: 2 unidades
- DMS completo: 2 unidades
- DMS puntos: 1 unidad
- DMS-P: 1 unidad
- AVI/ETC: 2 unidades (lectores por sentido)
- ALPR: 2 unidades (por sentido)
- WIM: 1 unidad (carril de fiscalización)
- RWIS: 1 unidad (puente)
- SOS: 3 unidades
- Gabinete: 3 unidades + 1 gabinete integrado peaje
- **Total componentes de campo: 26 unidades**

### 5.5.4 UF 4C — Funza Soterrado (3.7 km, ICCU)

**Caracterización:** Túnel soterrado de 1.2 km en el centro del tramo, accesos urbanos en ambos portales, 6 intersecciones, TPDA ~35,000 vehículos. Tipología: Túnel + Urbano (Paquete 5 Obligatorio + Paquete 4).

**Despliegue por Subtramo:**

| Subtramo | Km | Tipo | Componentes | Justificación |
|----------|-----|------|-------------|---------------|
| 4C.1 | 0.0-0.8 | Acceso urbano | CCTV-INT, VDS-INT, DMS-INT, PED, ILU, Gabinete | Intersecciones de acceso al túnel |
| 4C.2 | 0.8-2.0 | Túnel soterrado | CCTV-T térmica (2), CCTV-T fija (2), VMS-T (2), SOS-T (2), RWIS-T, ECS-T, Iluminación emergencia, Gabinete (2) | Vigilancia térmica, emergencias, calidad de aire, iluminación de respaldo |
| 4C.3 | 2.0-3.7 | Acceso urbano | CCTV-INT, VDS-INT, DMS-INT, PED, ILU, Gabinete | Intersecciones de salida del túnel |

**Consolidado UF 4C:**
- CCTV-T térmica: 2 unidades (túnel)
- CCTV-T fija: 2 unidades (túnel)
- CCTV-INT: 4 unidades (accesos)
- VDS-INT: 4 unidades
- VMS-T: 2 unidades (túnel)
- DMS-INT: 4 unidades
- SOS-T: 2 unidades (túnel)
- SOS: 2 unidades (accesos)
- RWIS-T: 1 unidad (túnel)
- ECS-T: 1 unidad (túnel)
- PED: 4 unidades
- ILU: 4 unidades
- Iluminación emergencia: 1 sistema (túnel)
- Gabinete: 4 unidades (2 túnel + 2 accesos)
- **Total componentes de campo: 37 unidades + 1 sistema**

### 5.5.5 UF 5 — Montaña Mondoñedo (7.0 km, ICCU)

**Caracterización:** Tramo de montaña con 2 túneles (800 m y 1.2 km), curvas de radio < 150 m, pendiente > 6%, historial de niebla, TPDA ~28,000 vehículos. Sin red eléctrica, sin fibra. Tipología: Montaña + Túnel (Paquete 7 Obligatorio + Paquete 5).

**Despliegue por Subtramo:**

| Subtramo | Km | Tipo | Componentes | Justificación |
|----------|-----|------|-------------|---------------|
| 5.1 | 0.0-1.5 | Curva pronunciada | CCTV-C (2), VDS-Radar (2), DMS-C, RWIS, SOS, Gabinete solar | Curvas de alta siniestralidad, velocidad dinámica |
| 5.2 | 1.5-2.3 | Túnel 1 | CCTV-T térmica (2), CCTV-T fija (2), VMS-T, SOS-T (2), RWIS-T, ECS-T, Gabinete solar | Túnel de montaña, emergencias, calidad de aire |
| 5.3 | 2.3-4.0 | Curva + Niebla | CCTV-C (2), VDS-Radar (2), DMS-C, RWIS con visibilímetro, SOS, Gabinete solar | Zona de niebla persistente, alerta de visibilidad |
| 5.4 | 4.0-5.2 | Túnel 2 | CCTV-T térmica (3), CCTV-T fija (3), VMS-T (2), SOS-T (2), RWIS-T, ECS-T, Gabinete solar | Túnel largo, mayor densidad de vigilancia |
| 5.5 | 5.2-7.0 | Curva descendente | CCTV-C (2), VDS-Radar (2), DMS-C, SOS, Gabinete solar | Curvas de alta pendiente, control de velocidad |

**Consolidado UF 5:**
- CCTV-T térmica: 5 unidades (túneles)
- CCTV-T fija: 5 unidades (túneles)
- CCTV-C: 6 unidades (curvas)
- VDS-Radar: 6 unidades (curvas, inmune a niebla)
- VMS-T: 3 unidades (túneles)
- DMS-C: 3 unidades (curvas)
- SOS-T: 4 unidades (túneles)
- SOS: 3 unidades (curvas)
- RWIS: 1 unidad (zona niebla)
- RWIS-T: 2 unidades (túneles)
- ECS-T: 2 unidades (túneles)
- Gabinete solar: 5 unidades
- Radio enlace: 2 unidades (respaldos)
- **Total componentes de campo: 48 unidades**

### 5.5.6 Resumen de Despliegue por UF (Sector Norte)

| UF | Tramo | km | Tipología | Componentes de Campo | Fibra Óptica (km) | Nodos de Com. | Gabinetes |
|----|-------|-----|-----------|---------------------|-------------------|---------------|-----------|
| 1 | Variante Chía | 3.1 | Urbano | 25 | 3.1 | 3 | 3 |
| 2 | Variante Cota | 3.5 | Urbano | 28 | 3.5 | 3 | 3 |
| 3 | Cota – La Tebaida | 6.0 | Arterial + Peaje | 26 | 6.0 | 4 | 4 |
| 4A | Funza-Mosquera Oriental | 1.7 | Urbano | 22 | 1.7 | 2 | 2 |
| 4B | Funza-Mosquera Occidental | 0.7 | Urbano | 12 | 0.7 | 1 | 1 |
| 4C | Funza Soterrado | 3.7 | Túnel + Urbano | 37+1 sist. | 3.7 | 4 | 4 |
| 5 | Montaña Mondoñedo | 7.0 | Montaña + Túnel | 48 | 7.0 | 5 | 5 |
| 6 | Conexión Soacha | 7.9 | Arterial + Urbano | 32 | 7.9 | 4 | 4 |
| 7 | Mondoñedo – La Gran Vía | 4.5 | Arterial | 18 | 4.5 | 3 | 3 |
| 8 | La Gran Vía – La Mesa | 1.0 | Arterial | 8 | 1.0 | 1 | 1 |
| 9 | La Mesa – Anapoima | 0.6 | Arterial | 6 | 0.6 | 1 | 1 |
| 10 | Anapoima – Tocaima | 0.3 | Arterial | 4 | 0.3 | 1 | 1 |
| 11 | Tocaima – Girardot | 0.7 | Arterial | 7 | 0.7 | 1 | 1 |
| **Subtotal Sector Norte** | | **40.7** | | **273** | **40.7** | **33** | **33** |

**Nota:** El despliegue detallado de las UFs 12-15 (Colectoras) se consigna en el Anexo 9.4 del presente documento, siguiendo la misma metodología y estructura de justificación técnica por subtramo.

## 5.6 Consolidado de Componentes de Campo

### 5.6.1 Consolidado General por Categoría de Componente

El despliegue detallado de las 15 Unidades Funcionales se consolida en un inventario general de componentes de campo que dimensiona la totalidad de la inversión en activos físicos del sistema ITS. Este consolidado se organiza por categorías funcionales que agrupan los 42 códigos CC del catálogo oficial en familias lógicas de equipos.

| Categoría | Componentes Incluidos (CC) | Unidades Sector Norte (UF 1-11) | Unidades Sector Sur (UF 12-15) | Total Corredor | % del Total |
|-----------|------------------------------|--------------------------------|--------------------------------|----------------|-------------|
| **Videovigilancia** | CC-01 (CCTV PTZ), CC-02 (CCTV fija), CC-03 (CCTV térmica) | 89 | 45 | 134 | 28% |
| **Detección de Tráfico** | CC-08 (VDS bucle), CC-09 (VDS video), CC-10 (VDS radar) | 56 | 28 | 84 | 17% |
| **Paneles de Mensaje** | CC-05 (DMS completo), CC-06 (DMS puntos), CC-07 (DMS especial) | 42 | 24 | 66 | 14% |
| **Seguridad y Emergencia** | CC-04 (ECS/SOS), CC-16 (SOS túnel), CC-17 (Iluminación emergencia) | 38 | 18 | 56 | 12% |
| **Meteorología** | CC-07 (RWIS), CC-15 (Sensor ambiental) | 12 | 8 | 20 | 4% |
| **Peaje y Fiscalización** | CC-11 (AVI/ETC), CC-12 (WIM piezo), CC-13 (WIM célula), CC-14 (ALPR) | 18 | 0 | 18 | 4% |
| **Comunicaciones** | CC-18 (Fibra óptica), CC-20 (Radio enlace), CC-21 (V2I/RSU) | 40.7 km + 8 enlaces | 148 km + 12 enlaces | 188.7 km + 20 enlaces | - |
| **Control y Gestión** | CC-19 (Switch), CC-22 (UPS), CC-23 (Panel solar), CC-24 (Batería) | 33 sets | 22 sets | 55 sets | 11% |
| **Estructuras** | CC-17 (Poste/pórtico) | 45 | 28 | 73 | 15% |
| **Centro de Control** | CC-26 (Videowall), CC-27 (Workstation), CC-28 (Servidor), CC-29 (Almacenamiento) | 1 CCO | 1 CCO contingencia | 2 CCO | 1% |

**Total de componentes de campo (unidades físicas):** 486 unidades + 188.7 km de fibra óptica + 20 radio enlaces + 2 Centros de Control.

### 5.6.2 Consolidado por Código CC (Catálogo Oficial)

El siguiente cuadro presenta el desglose exacto por código CC del catálogo de 42 componentes, validando que cada código definido contractualmente tiene una cantidad asignada y una justificación de su presencia o ausencia en el corredor.

| Código CC | Descripción | Cantidad | Ubicación Principal | Justificación de Cantidad |
|-----------|-------------|----------|---------------------|---------------------------|
| CC-01 | CCTV PTZ | 34 | Intersecciones, peajes, CCO | Vigilancia controlada de zonas críticas |
| CC-02 | CCTV fija | 78 | Tramos arteriales, túneles, colectoras | Cobertura continua de tráfico |
| CC-03 | CCTV térmica | 22 | Túneles, zonas de niebla, montaña | Vigilancia en condiciones de baja visibilidad |
| CC-04 | ECS / SOS | 48 | Cada 2-5 km según tipología | Atención de emergencias en vía |
| CC-05 | DMS matriz completa | 28 | Arterial principal, peajes, túneles | Mensajes dinámicos complejos |
| CC-06 | DMS matriz puntos | 24 | Colectoras, tramos rurales | Información básica de tráfico |
| CC-07 | DMS especial / RWIS | 14 | Zonas de niebla, montaña | DMS con velocidad dinámica + meteorología |
| CC-08 | VDS bucle inductivo | 18 | Intersecciones nuevas, rehabilitaciones | Detección precisa donde el pavimento ya se corta |
| CC-09 | VDS video | 42 | Tramos arteriales, intersecciones | Detección por analítica, sin cortar pavimento |
| CC-10 | VDS radar | 24 | Curvas, montaña, zonas climáticas | Inmune a condiciones climáticas adversas |
| CC-11 | AVI / ETC | 4 | Peaje La Tebaida (2 por sentido) | Integración con sistema FONDECUN |
| CC-12 | WIM piezoeléctrico | 0 | - | No aplica: se prefiere WIM de célula por mayor precisión |
| CC-13 | WIM célula de carga | 2 | Peaje La Tebaida (fiscalización) | Mayor precisión y vida útil para control de peso |
| CC-14 | ALPR | 4 | Peaje La Tebaida (2 por sentido) | Respaldo de AVI y fiscalización de evasores |
| CC-15 | Sensor ambiental | 6 | Túneles, zonas de montaña | Calidad de aire, temperatura, humedad interna |
| CC-16 | Gabinete de control | 55 | Cada 2-5 km según densidad | Alimentación, comunicaciones, protección de equipos |
| CC-17 | Poste / Pórtico | 73 | Soportes de cámaras, DMS, detectores | Estructuras de soporte de campo |
| CC-18 | Fibra óptica | 188.7 km | Toda la extensión del corredor | Red troncal de comunicaciones |
| CC-19 | Switch industrial | 55 | Dentro de cada gabinete | Interconexión de equipos en campo |
| CC-20 | Radio enlace | 20 | Zonas sin fibra, túneles, respaldos | Comunicación donde la fibra no llega |
| CC-21 | V2I / RSU | 8 | Intersecciones piloto, peaje | Preparación para comunicación cooperativa |
| CC-22 | UPS | 55 | Dentro de cada gabinete | Respaldo energético 4-8 horas |
| CC-23 | Panel solar | 18 | Zonas sin red eléctrica (montaña, rural) | Autonomía energética en sitios aislados |
| CC-24 | Batería Li-Ion | 18 | Acompañando paneles solares | Almacenamiento de energía solar |
| CC-25 | Generador diésel | 2 | CCO principal y CCO contingencia | Respaldo de larga duración (24-72 h) |
| CC-26 | Videowall LED | 24 m² | CCO principal | Visualización de 24/7 en centro de control |
| CC-27 | Workstation | 12 | CCO principal (operadores) | Puestos de trabajo del personal de control |
| CC-28 | Servidor | 8 | CCO principal (rack de servidores) | Procesamiento, almacenamiento, virtualización |
| CC-29 | Almacenamiento NAS | 2 | CCO principal | Archivo de video y datos (capacidad: 2 PB) |
| CC-30 | ATMS Software | 1 | CCO principal | Sistema de gestión de tráfico integral |
| CC-31 | VMS Software | 1 | CCO principal | Gestión de video (licencia por cámara) |
| CC-32 | GIS Software | 1 | CCO principal | Sistema de información geográfica del corredor |
| CC-33 | BI / Analytics | 1 | CCO principal | Análisis de datos y Business Intelligence |
| CC-34 | Ciberseguridad | 1 | CCO principal | Firewall, IDS/IPS, cifrado, segmentación |
| CC-35 | NMS / SNMP | 1 | CCO principal | Gestión de red y monitoreo de equipos |
| CC-36 | Backup / DR | 1 | CCO principal + contingencia | Respaldo y recuperación ante desastres |
| CC-37 | Mantenimiento 24/7 | 1 (servicio) | Todo el corredor | Contrato de mantenimiento integral |
| CC-38 | Capacitación | 1 (programa) | CCO + campo | Entrenamiento del personal del concesionario |
| CC-39 | Ingeniería de detalle | 1 (proyecto) | Todo el corredor | Diseño constructivo de la infraestructura ITS |
| CC-40 | Instalación y puesta en marcha | 1 (proyecto) | Todo el corredor | Ejecución física del despliegue |
| CC-41 | E-LOG (Logística) | 1 (módulo) | CCO principal | Gestión de flota y logística de mantenimiento |
| CC-42 | NTCIP Gateway | 55 | Cada gabinete | Interoperabilidad con estándares NTCIP |

**Notas de consolidado:**
- **CC-12 (WIM piezoeléctrico):** Cantidad 0. Se excluye por decisión técnica de preferir WIM de célula de carga (CC-13) que ofrece mayor precisión (±3-5% vs ±5-10%) y mayor vida útil (10-15 años vs 5-7 años). La justificación se fundamenta en el estudio de mercado del Capítulo 4.
- **CC-21 (V2I/RSU):** Cantidad 8 (piloto). Se despliega en fase 4 como tecnología emergente, en intersecciones críticas y peaje, preparando el corredor para la integración futura de vehículos conectados sin comprometer la inversión inicial.
- **CC-23 y CC-24 (Solar + Batería):** Cantidad 18 sets. Cubre las zonas sin red eléctrica identificadas en el inventario (UF 5, 8, 9, 10, 11, y sectores rurales de colectoras). La solución solar es mandatoria donde no hay red, conforme a los principios de sostenibilidad del proyecto 5G.
- **CC-40 (Instalación y puesta en marcha):** Se consolida como un proyecto integral que abarca la totalidad del corredor, no como unidades individuales, dado que la instalación es un servicio global que se contrata una vez para todo el despliegue.

## 5.7 Arquitectura de Comunicaciones

### 5.7.1 Topología de Red

La red de comunicaciones del corredor ITS se diseña bajo una topología de **anillo dual (dual ring)** con redundancia física, que garantiza la continuidad del servicio ante cortes de fibra o fallos de nodos. Esta topología es el estándar de la industria para infraestructura crítica y responde al principio de redundancia selectiva definido en el numeral 5.2.1.

La red se estructura en tres capas jerárquicas:

**Capa 1 — Red Troncal (Backbone):** Fibra óptica monomodo que recorre la totalidad del corredor (188.7 km en Sector Norte + 148 km en Sector Sur = 336.7 km de fibra). La fibra se instala en ductos de reserva de la obra civil, con una capacidad mínima de 24 hilos (12 para operación, 12 para redundancia). La topología de anillo permite que, si un tramo se corta, el tráfico se redirige por el lado opuesto del anillo en menos de 50 ms (protocolo ERPS o similar).

**Capa 2 — Red de Distribución (Distribution):** Switches industriales instalados en los gabinetes de control de campo (55 ubicaciones) que concentran el tráfico de los componentes locales (cámaras, detectores, paneles) y lo transmiten a la red troncal. Cada switch de campo tiene capacidad de 8-24 puertos Gigabit Ethernet, con alimentación PoE+ (Power over Ethernet) para dispositivos que lo soporten (cámaras IP, detectores).

**Capa 3 — Red de Acceso (Access):** Conexiones locales desde cada componente de campo hasta el switch del gabinete más cercano. Las distancias son menores a 100 m (límite del cableado Ethernet), por lo que se utiliza cableado UTP Cat 6A o fibra monomodo para distancias mayores. En túneles, se instala cableado resistente al fuego (LSZH) y conectores IP67 para ambientes húmedos.

### 5.7.2 Nodos de Comunicación

Los nodos de comunicación son los puntos donde la red troncal se conecta con los gabinetes de control y los centros de control. Se identifican tres tipos de nodos:

**Nodos de Acceso (Access Nodes):** 55 ubicaciones (uno por gabinete de control). Conectan los equipos de campo a la red troncal. Equipamiento: switch industrial de 8-16 puertos, convertidor de medios (fibra a Ethernet), ODF (Optical Distribution Frame) para gestión de hilos de fibra.

**Nodos de Agregación (Aggregation Nodes):** 8 ubicaciones estratégicas (Chía, Cota, Funza, Mondoñedo, Soacha, La Mesa, Girardot, y un punto central en el corredor). Conectan múltiples nodos de acceso y concentran el tráfico hacia el CCO. Equipamiento: switch de agregación de 24-48 puertos, router, firewall de campo, y conexión dual a la red troncal (anillo principal y anillo de respaldo).

**Nodos Centrales (Core Nodes):** 2 ubicaciones (CCO principal y CCO de contingencia). Reciben todo el tráfico del corredor, lo procesan, almacenan y distribuyen a los sistemas de gestión. Equipamiento: switches core de 96+ puertos, routers de alto rendimiento, firewalls de perímetro, servidores de aplicación, y conexión WAN hacia internet y hacia las entidades de control (ANI, ICCU, FONDECUN).

### 5.7.3 Tecnologías de Comunicación

**Fibra Óptica:** La red troncal utiliza fibra monomodo G.652D, estándar de la industria para distancias hasta 120 km sin regeneración. Los equipos terminales (switches, routers) utilizan transceptores SFP+ de 10 Gbps, con capacidad de upgrade a 40/100 Gbps sin cambiar la fibra. La fibra se instala con un mínimo de 24 hilos, permitiendo múltiples servicios sobre la misma infraestructura (ITS, telefonía del concesionario, sistemas de peaje, gestión de alumbrado).

**Radioenlaces:** Se despliegan 20 radioenlaces como respaldo o como solución primaria donde la fibra no es factible. Los radioenlaces utilizan tecnología de microondas en banda licenciada (11 GHz, 18 GHz) o banda libre (5.8 GHz), con capacidad de 100 Mbps a 1 Gbps. Los enlaces se configuran con diversidad de espacio (dos antenas separadas) para mitigar el desvanecimiento por multipath.

**Redes Móviles (4G/5G Privado):** En zonas donde ni fibra ni radioenlaces son viables (ej. colectoras remotas), se utiliza una red 4G/5G privada operada por el concesionario. Esta red utiliza espectro licenciado o bandas ISM, con estaciones base (gNodeB) conectadas a la red troncal en puntos de acceso. La red privada garantiza prioridad de tráfico para los servicios ITS sobre cualquier otro uso.

**V2I (Vehicle-to-Infrastructure):** En 8 intersecciones piloto, se despliegan unidades RSU (Road Side Units) que comunican con vehículos equipados mediante C-V2X (Cellular V2X) o DSRC. Esta tecnología habilita aplicaciones de seguridad activa (alerta de colisión, semáforo cooperativo, alerta de peatón) y se integra con el ATMS del CCO.

### 5.7.4 Ciberseguridad de la Red

La red de comunicaciones del corredor ITS es una infraestructura crítica que requiere protección contra ciberataques. La estrategia de ciberseguridad se basa en cuatro pilares:

**Segmentación de Red:** La red se divide en VLANs (Virtual LANs) separadas: VLAN 10 (CCTV), VLAN 20 (Detección), VLAN 30 (Paneles), VLAN 40 (Peaje), VLAN 50 (Gestión de red), VLAN 99 (Respaldo). Cada VLAN tiene sus propias reglas de firewall y no puede comunicarse con otras sin pasar por el firewall central.

**Cifrado:** Todo el tráfico de cámaras y datos sensibles se cifra mediante TLS 1.3 o IPsec. La fibra óptica se considera intrínsecamente segura (difícil de interceptar sin cortar), pero los enlaces de radio y 4G/5G se cifran obligatoriamente.

**Firewall y Detección de Intrusiones:** En cada nodo de agregación y en los nodos centrales se instalan firewalls de próxima generación (NGFW) con capacidad de inspección profunda de paquetes (DPI). El sistema IDS/IPS (Intrusion Detection/Prevention System) monitorea el tráfico en tiempo real y bloquea patrones de ataque conocidos.

**Gestión de Identidades y Accesos:** El acceso a la red de gestión (VLAN 50) requiere autenticación multifactor (MFA) y certificados digitales. Los técnicos de campo tienen acceso limitado (solo a los switches de su zona), mientras que los administradores del CCO tienen acceso global. Todos los accesos se registran en un log de auditoría inmutable.

## 5.8 Centros de Control y Mantenimiento

### 5.8.1 Centro de Control de Operación (CCO) Principal

El CCO principal es el núcleo del sistema ITS, donde se concentra la información de todo el corredor, se gestiona el tráfico, se atienden incidentes y se coordina la respuesta de emergencias. La ubicación estratégica del CCO debe cumplir con criterios de conectividad, seguridad, accesibilidad y proximidad al corredor.

**Ubicación Recomendada:** Funza o Mosquera, por las siguientes razones:
- Proximidad central al corredor (km 25 del eje principal, aproximadamente)
- Conectividad de fibra óptica (la red troncal pasa por la zona)
- Acceso a personal calificado (área metropolitana de Bogotá)
- Infraestructura de soporte (energía, internet, servicios)
- Seguridad física (zona urbana con vigilancia)

**Dimensionamiento del CCO:**
- Área total: 300 – 500 m²
- Sala de control: 150 m² (videowall, 12 puestos de operador)
- Sala de servidores: 80 m² (rack, climatización, UPS, generador)
- Sala de reuniones: 30 m² (crisis management)
- Oficinas administrativas: 60 m² (ingeniería, supervisión)
- Áreas de soporte: 80 m² (recepción, descanso, almacén)

**Equipamiento Principal:**
- Videowall LED: 24 m² (configuración 6×4 m, fine pitch 1.5 mm)
- Puestos de operador: 12 (3 turnos de 4 operadores, 24/7)
- Servidores: 8 unidades (virtualización, base de datos, aplicaciones, web)
- Almacenamiento: 2 PB (petabytes) de capacidad bruta (RAID 6, con 30% de overhead)
- UPS: 30 minutos de autonomía para toda la sala de servidores
- Generador diésel: 72 horas de autonomía con tanque de reserva
- Climatización: Precisión (±1°C, ±5% HR) con redundancia N+1
- Acceso biométrico: Huella + tarjeta + reconocimiento facial
- Sistema de supresión de incendios: FM-200 (gas limpio, no daña electrónicos)

**Software de Gestión:**
- ATMS (Advanced Traffic Management System): Plataforma principal de gestión del tráfico, integración de CCTV, DMS, VDS, incidentes, y reportes regulatorios.
- VMS (Video Management System): Gestión de las 134 cámaras del corredor, archivado, búsqueda forense, exportación de evidencia.
- GIS (Geographic Information System): Mapa digital del corredor con capas de información en tiempo real (tráfico, incidentes, clima, equipos en fallo).
- BI (Business Intelligence): Dashboards de indicadores de desempeño (KPIs), análisis de tendencias de tráfico, predicción de congestión.
- SCADA (Supervisory Control and Data Acquisition): Control de equipos de campo (DMS, semáforos, iluminación, ventilación de túneles).
- NMS (Network Management System): Monitoreo de la red de comunicaciones, alertas de fallo, gestión de configuración.

**Personal del CCO (Estimado):**
- Gerente de Operación ITS: 1 (planificación, reportes, coordinación con ICCU/ANI)
- Supervisor de turno: 3 (uno por turno, lidera operadores)
- Operador de tráfico: 12 (4 por turno, monitorean y responden)
- Técnico de sistemas: 3 (mantenimiento de servidores, red, software)
- Técnico de campo: 6 (mantenimiento preventivo y correctivo de equipos)
- **Total personal CCO: 25 personas**

### 5.8.2 Centro de Control de Contingencia (DR Site)

El centro de contingencia es una réplica del CCO principal, ubicada en un sitio geográficamente separado (mínimo 20 km de distancia) para evitar que un desastre local (sismo, incendio, inundación) afecte ambos centros simultáneamente.

**Ubicación Recomendada:** Girardot o una zona cercana al extremo sur del corredor, o alternativamente una ciudad fuera del valle geográfico del corredor (ej. Bogotá norte).

**Dimensionamiento:**
- Área total: 100 – 150 m² (mínimo operativo)
- Sala de control: 50 m² (videowall reducida, 4 puestos)
- Sala de servidores: 40 m² (réplica de datos en tiempo real)
- UPS y generador: 30 min + 72 h respectivamente

**Función:** En operación normal, el centro de contingencia replica en tiempo real todos los datos del CCO principal (replicación síncrona de base de datos, mirror de video, backup de configuración). En caso de fallo del CCO principal, el centro de contingencia asume el control en menos de 5 minutos (failover automático). La conmutación se prueba mensualmente mediante simulacros de contingencia.

### 5.8.3 Centro de Mantenimiento y Bodega

El centro de mantenimiento es la infraestructura física donde se almacenan repuestos, se reparan equipos y se preparan los equipos de campo para instalación o reemplazo.

**Ubicación:** Puede coincidir con el CCO principal o estar en una ubicación cercana con acceso rápido al corredor.

**Dimensionamiento:**
- Bodega de repuestos: 200 m² (estanterías, clima controlado para electrónicos)
- Taller de reparación: 50 m² (bancos de trabajo, herramientas, osciloscopios, probadores de red)
- Área de carga/descarga: 30 m² (acceso para vehículos de mantenimiento)
- Oficina de ingeniería: 20 m² (diagramas, documentación técnica)

**Inventario de Repuestos Críticos (Stock Mínimo):**
- Cámaras CCTV (fija, PTZ, térmica): 5% del total desplegado
- Switches industriales: 10% del total
- Fuentes de poder de gabinetes: 10% del total
- Paneles DMS (módulos LED): 5% del total
- Media converters y transceptores SFP: 15% del total
- Cableado UTP y fibra óptica: 5 km de reserva
- Postes y pórticos: 2 unidades de cada tipo

**Vehículos de Mantenimiento:**
- Vehículo tipo canasta (aéreo): 2 unidades (para mantenimiento de cámaras y DMS en altura)
- Vehículo de respuesta rápida: 3 unidades (equipados con herramientas, repuestos críticos, comunicación con CCO)
- Vehículo de transporte de equipos: 1 unidad (carga pesada, palés de equipos)

## 5.9 Plan de Implementación y Cronograma

### 5.9.1 Fases de Implementación

El despliegue del sistema ITS se programa en cinco fases que permiten una puesta en marcha progresiva, validando cada etapa antes de pasar a la siguiente. Esta estrategia reduce riesgos, permite ajustes basados en aprendizaje operativo, y distribuye la inversión en el tiempo.

**Fase 1 — Infraestructura Crítica (Meses 1-6):**
- Objetivo: Habilitar la red de comunicaciones y los componentes de seguridad crítica.
- Alcance: Fibra óptica en vía arterial principal (158 km), gabinetes de control en UF 1-6, CCTV en túneles (UF 4C, 5), DMS en zonas de alta siniestralidad, SOS en toda la arterial.
- Entregable: Corredor arterial con comunicaciones y seguridad básica operativa.
- Dependencias: Finalización de zanjas de obra civil en UF 1-6.

**Fase 2 — Cobertura Total Arterial (Meses 7-12):**
- Objetivo: Completar el despliegue en la vía arterial principal (UF 7-11) y habilitar el CCO principal.
- Alcance: Fibra óptica en UF 7-11, CCTV completa en arterial, VDS en todos los tramos, DMS en puntos críticos, RWIS en zonas climáticas, peaje La Tebaida integrado, CCO principal operativo.
- Entregable: Sistema ITS completo en 158 km de arterial con CCO operativo.
- Dependencias: Fase 1 completada, entrega de gabinete CCO, instalación de energía en CCO.

**Fase 3 — Colectoras y Rurales (Meses 13-18):**
- Objetivo: Extender el sistema a las colectoras (148 km) y zonas rurales.
- Alcance: Fibra óptica o radioenlaces en colectoras, CCTV básica, DMS simple, SOS, soluciones solares en zonas sin red eléctrica.
- Entregable: Cobertura ITS en 306 km totales (arterial + colectoras).
- Dependencias: Fase 2 completada, aprobación de presupuesto para colectoras.

**Fase 4 — Tecnologías Emergentes (Meses 19-24):**
- Objetivo: Incorporar tecnologías de vanguardia y optimizar el sistema.
- Alcance: V2I/RSU en intersecciones piloto (8 ubicaciones), analítica avanzada de video (IA para predicción de incidentes), integración con sistemas de terceros (Waze, Google Maps, aplicaciones móviles del concesionario), paneles solares adicionales, eficiencia energética.
- Entregable: Corredor con capacidades de quinta generación avanzada, integración multimodal.
- Dependencias: Maduración tecnológica de V2I, aprobación de piloto por ICCU.

**Fase 5 — Consolidación y Optimización (Meses 25-36):**
- Objetivo: Consolidar operación, capacitar personal, documentar lecciones aprendidas y optimizar con base en datos.
- Alcance: Ajuste de densidad de componentes según datos operativos (aumentar donde hay más incidentes, reducir donde es excesivo), actualización de software, certificación de personal, auditoría de ciberseguridad, documentación final de la infraestructura (BIM as-built).
- Entregable: Sistema ITS maduro, documentado, operado por personal certificado, con capacidad de automejora continua.
- Dependencias: 12 meses de datos operativos reales para análisis de optimización.

### 5.9.2 Cronograma Resumen

| Fase | Descripción | Duración | Meses (Contrato) | Hitos Clave |
|------|-------------|----------|------------------|-------------|
| 0 | Ingeniería de detalle | 6 meses | 1-6 | Planos constructivos, aprobación interventoría, compra de equipos Fase 1 |
| 1 | Infraestructura crítica | 6 meses | 4-9 | Fibra UF 1-6, túneles, CCO en construcción |
| 2 | Cobertura arterial | 6 meses | 10-15 | Fibra UF 7-11, CCO operativo, arterial completa |
| 3 | Colectoras | 6 meses | 16-21 | Colectoras completas, sistema a 306 km |
| 4 | Tecnologías emergentes | 6 meses | 22-27 | V2I piloto, analítica avanzada, integraciones |
| 5 | Consolidación | 12 meses | 28-39 | Optimización, capacitación, documentación final |

**Nota cronológica:** El cronograma se basa en un horizonte de 39 meses para el despliegue completo, que puede ajustarse según la fecha de inicio de la concesión y la disponibilidad de obra civil. Las fases 0-3 son críticas para el inicio de operaciones; las fases 4-5 son de optimización y valor agregado.

### 5.9.3 Dependencias Críticas

| ID | Dependencia | Impacto si falla | Mitigación |
|----|-------------|------------------|------------|
| D1 | Obras civil finaliza zanjas en UF | Retraso de fibra óptica | Micro-zanjado, tendido aéreo temporal, compra anticipada |
| D2 | Entrega de energía en CCO | CCO no puede operar | Generador temporal, negociación con utility, UPS extendido |
| D3 | Aprobación de interventoría ITS | Obra detenida | Pre-aprobación de paquetes, reuniones técnicas semanales |
| D4 | Integración con peaje FONDECUN | Peaje no operativo | Pruebas de integración en fase 0, API estándar, respaldo manual |
| D5 | Licencias de espectro radio | Radioenlaces no funcionan | Solicitud anticipada (6 meses), banda libre 5.8 GHz como alternativa |
| D6 | Personal capacitado para CCO | Operación deficiente | Capacitación en fase 0, simuladores, certificación externa |
| D7 | Importación de equipos críticos | Retraso de despliegue | Stock de seguridad en almacén, proveedores con stock local |

### 5.9.4 Riesgos del Despliegue y Estrategias de Mitigación

| Riesgo | Probabilidad | Impacto | Estrategia de Mitigación |
|--------|-------------|---------|--------------------------|
| Retraso de obra civil | Alto | Alto | Tendido aéreo temporal, micro-zanjado, equipos de instalación rápida |
| Falla de integración con peaje | Medio | Alto | Pruebas en laboratorio antes de campo, protocolo de respaldo manual, API documentada |
| Clima adverso en montaña | Medio | Medio | Ventanas de instalación en verano, equipos climatizados, protección IP67 |
| Robo/vandalismo de equipos | Medio | Medio | Gabinetes antivandalismo, monitoreo por CCTV, seguro de equipos, denuncia a autoridades |
| Falla de red eléctrica | Alto | Medio | Paneles solares + batería en todos los gabinetes, UPS, generadores en CCO |
| Ciberataque al CCO | Bajo | Alto | Segmentación, cifrado, firewall, IDS/IPS, auditoría, respaldo off-line |
| Desabastecimiento de repuestos | Medio | Medio | Stock de seguridad, contrato de mantenimiento con SLA, múltiples proveedores |
| Cambio normativo durante despliegue | Bajo | Medio | Monitoreo normativo, diseño flexible, participación en mesas técnicas de MinTransporte |

**Nota final del Capítulo 5:** El Plan Indicativo ITS presentado en este capítulo constituye la propuesta técnica de despliegue que traduce la arquitectura conceptual del Entregable 1 en una configuración física, cuantificada y cronogramada. Las cantidades, ubicaciones y especificaciones son propuestas preliminares que requieren validación mediante estudio de tráfico detallado, aprobación de la interventoría de la ANI, y ajustes en la fase de ingeniería de detalle. Sin embargo, este Plan Indicativo proporciona al futuro Concesionario, a la IFC y al ICCU la certeza técnica sobre el alcance, la magnitud y la secuencia del despliegue, permitiendo la estimación de costos, la planificación de recursos y la estructuración del contrato de concesión con base en datos técnicos sólidos y coherentes con la normativa nacional e internacional.

