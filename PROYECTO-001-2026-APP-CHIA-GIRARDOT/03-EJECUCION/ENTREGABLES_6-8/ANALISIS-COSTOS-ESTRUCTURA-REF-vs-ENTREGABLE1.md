# ANÁLISIS COMPARATIVO — Estructura de Costos vs. Entregable #1 (APP Chía-Girardot)

**Fecha:** Junio 2026
**Proyecto:** APP Chía-Girardot — Componente Tecnológico ITS
**Referencia:** Modelo Financiero V1 (imagen recibida) vs. Entregable 1 — Estructura Técnica ITS
**Propósito:** Evaluar qué hace falta en la estructura de costos recibida y proponer la estructura completa para el modelo financiero

---

## 1. EVALUACIÓN DE LA ESTRUCTURA RECIBIDA (Formato de Referencia)

### 1.1 Lo que tiene la estructura de referencia

La imagen recibida presenta una estructura jerárquica limpia:

| Jerarquía | Ejemplo en imagen |
|-----------|-------------------|
| **TRAMO** | Tramo 1: Av. Pradilla — Glorieta Norte Cota (7,134 km) |
| **SUBTRAMO** | 1.1 Variante Chía (3,068 km) / 1.2 Conexión Chía-Cota (4,066 km) |
| **SISTEMA** | Red de Comunicaciones / Energía / ITS |
| **COMPONENTE** | Fibra óptica, Suministro eléctrico, Cámaras, PMV, Postes, Gabinetes, Otros |
| **DOBLE CALZADA** | Cantidad Ida + Cantidad Retorno = Cantidad Total |

### 1.2 Errores detectados en la estructura de referencia

**A. Error de longitud del Subtramo 1.1**
- Imagen dice: 3,068 km
- Entregable 1 / Modelo Financiero V1: **3,086 km** (UF 1 — Variante Chía)
- Diferencia: 18 metros. Posible error de transcripción o redondeo.

**B. Valores unitarios irrealmente uniformes ($250.000 para TODO)**
- Fibra óptica: $250.000/km → realidad: $15–50 millones/km instalada
- Cámaras: $250.000/unidad → realidad: $5–15 millones/unidad
- PMV: $250.000/unidad → realidad: $80–300 millones/unidad
- Postes de emergencia: $250.000/unidad → realidad: $8–20 millones/unidad

**C. Omisión masiva de componentes del Entregable 1**
La imagen incluye solo 5 componentes ITS (Cámaras, PMV, Postes, Gabinetes, Otros). El Entregable 1 define **42 Componentes de Campo (CC-01 a CC-42)**. Faltan 37 componentes.

**D. Energía cotizada por km (concepto incorrecto)**
El suministro eléctrico no se compra por kilómetro. Requiere: acometidas, transformadores, tableros, cables de baja tensión, UPS, baterías, puesta a tierra, paneles solares donde no hay red.

**E. Faltan sistemas enteros**
- No hay red de comunicaciones detallada (solo fibra óptica, no switches, radios, gateways)
- No hay sistemas de detección de tráfico (bucles, radar, video)
- No hay sistemas de control de peaje
- No hay sistemas de telegestión energética
- No hay centro de control (CCO)
- No hay sistemas V2X, ciberseguridad, respaldo satelital

---

## 2. CATÁLOGO OFICIAL DE COMPONENTES DE CAMPO — ENTREGABLE 1

Los 42 Componentes de Campo (CC) definidos en el Entregable 1 se agrupan en **8 Sistemas Funcionales**:

### Sistema 1: Detección y Vigilancia (CC-01 a CC-09)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-01 | CCTV PTZ (Pan-Tilt-Zoom) | Unidad | Videovigilancia 360° intersecciones críticas |
| CC-02 | CCTV fija (Fixed) | Unidad | Vigilancia continua de flujo |
| CC-03 | CCTV con AID (Autom. Incident Detection) | Unidad | Detección automática de incidentes por video |
| CC-04 | ECS / SOS (Emergency Call System) | Unidad | Punto de emergencia peatonal/vial |
| CC-05 | DMS matriz completa (Full Matrix) | Unidad | Panel mensaje variable gráfico/texto |
| CC-06 | DMS matriz puntos (Dot Matrix) | Unidad | Panel mensaje variable texto simple |
| CC-07 | VSL (Variable Speed Limit) | Unidad | Señalización de velocidad variable |
| CC-08 | VDS bucle inductivo | Unidad | Detección tráfico por bucle magnético |
| CC-09 | VDS radar / acústico | Unidad | Detección tráfico sin bucle (no invasivo) |

### Sistema 2: Control y Actuación (CC-10 a CC-15)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-10 | Semáforo inteligente / TCS | Unidad | Control semafórico adaptativo |
| CC-11 | Controlador de intersección (TSC) | Unidad | Controlador lógico de semáforos |
| CC-12 | Barrera peatonal automática | Unidad | Protección peatonal activa (zonas escolares) |
| CC-13 | Iluminación inteligente / LED túneles | Unidad | Iluminación adaptativa túneles/vías |
| CC-14 | Sistema de riego túneles | Unidad | Supresión de incendios en túneles |
| CC-15 | Sistema de ventilación túneles | Unidad | Control de calidad de aire en túneles |

### Sistema 3: Red de Comunicaciones (CC-16 a CC-21)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-16 | Gabinete de control de campo | Unidad | Alojamiento equipos, protección IP65 |
| CC-17 | Servidor de borde (Edge Server) | Unidad | Procesamiento local de datos |
| CC-18 | Fibra óptica (km de hilo) | km | Red troncal de transporte de datos |
| CC-19 | Switch industrial Ethernet | Unidad | Conmutación de red de campo |
| CC-20 | Radio enlace / microondas | Par | Respaldo de comunicaciones |
| CC-21 | Antena 4G/5G / V2X RSU | Unidad | Comunicación vehicular e inalámbrica |

### Sistema 4: Energía y Respaldo (CC-22 a CC-27)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-22 | UPS (Sistema de respaldo energético) | Unidad | Respaldo 4–8 horas |
| CC-23 | Panel solar fotovoltaico | Unidad | Generación autónoma (zonas sin red) |
| CC-24 | Batería de litio (almacenamiento) | Unidad | Almacenamiento energético nocturno |
| CC-25 | Transformador / acometida eléctrica | Unidad | Conexión a red eléctrica formal |
| CC-26 | Tablero de distribución eléctrica | Unidad | Distribución interna de energía |
| CC-27 | Sistema de puesta a tierra | Unidad | Protección eléctrica y equipos |

### Sistema 5: Recaudo y Peaje (CC-28 a CC-31)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-28 | Antena RFID / AVI (peaje electrónico) | Unidad | Lectura de tags vehiculares |
| CC-29 | Validador de categoría vehicular | Unidad | Clasificación automática de vehículos |
| CC-30 | Barrera de peaje | Unidad | Control físico de paso |
| CC-31 | Cabina de peaje / Toll Plaza | Unidad | Infraestructura de recaudo |

### Sistema 6: Control de Carga y Pesaje (CC-32 a CC-34)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-32 | WIM (Weigh In Motion) | Unidad | Pesaje en movimiento de vehículos pesados |
| CC-33 | Plataforma de pesaje estática | Unidad | Pesaje preciso (control legal) |
| CC-34 | Sistema de precinto electrónico | Unidad | Control de carga y sellos digitales |

### Sistema 7: Seguridad y Resiliencia (CC-35 a CC-39)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-35 | Sensor de humo / CO en túneles | Unidad | Detección de incendios / gases |
| CC-36 | Sistema de cierre de túneles (compuertas) | Unidad | Contención de incidentes en túneles |
| CC-37 | Sistema de alerta sísmica / estructural | Unidad | Monitoreo de integridad estructural |
| CC-38 | Sistema de respaldo satelital (SAT-B) | Unidad | Comunicación ante fallo total de red |
| CC-39 | Sistema de ciberseguridad de campo (Firewall) | Unidad | Protección de red perimetral |

### Sistema 8: Gestión y Soporte (CC-40 a CC-42)

| Código | Componente | Unidad | Función principal |
|--------|------------|--------|-------------------|
| CC-40 | Estación meteorológica | Unidad | Datos climáticos en tiempo real |
| CC-41 | Sistema de telegestión energética (MSG) | Unidad | Control remoto de consumo energético |
| CC-42 | Gateway NTCIP / Protocolo estándar | Unidad | Interoperabilidad entre fabricantes |

---

## 3. GAP ANALYSIS — ¿Qué hace falta en la estructura de referencia?

### 3.1 Faltan por completos: Sistemas enteros

| Sistema | Componentes faltantes | Impacto en costos |
|---------|----------------------|-------------------|
| **Control y Actuación** | CC-10 a CC-15 (semáforos, barreras, iluminación túneles, riego, ventilación) | **$8–15 mil millones** (túneles son caros) |
| **Recaudo y Peaje** | CC-28 a CC-31 (4 estaciones de peaje con TPDA 40.000) | **$15–25 mil millones** |
| **Control de Carga** | CC-32 a CC-34 (WIM, plataforma, precinto) | **$3–6 mil millones** |
| **Seguridad y Resiliencia** | CC-35 a CC-39 (túneles, sísmica, satélite, ciberseguridad) | **$5–10 mil millones** |
| **Gestión y Soporte** | CC-40 a CC-41 (meteorología, telegestión) | **$1–2 mil millones** |

### 3.2 Faltan detalles dentro de sistemas que SÍ aparecen

| Sistema en imagen | Lo que muestra | Lo que falta del Entregable 1 |
|---------------------|--------------|-------------------------------|
| **Red de Comunicaciones** | Solo "Fibra óptica" | CC-19 (switches), CC-20 (radio enlaces), CC-21 (antenas 4G/5G/V2X), CC-17 (edge servers), CC-42 (gateways) |
| **Energía** | Solo "Suministro eléctrico" | CC-22 (UPS), CC-23 (paneles solares), CC-24 (baterías), CC-25 (transformadores), CC-26 (tableros), CC-27 (puesta a tierra), CC-41 (telegestión) |
| **ITS** | Solo 5 componentes genéricos | CC-01 (CCTV PTZ), CC-02 (CCTV fija), CC-03 (CCTV AID), CC-04 (SOS), CC-07 (VSL), CC-08 (bucles), CC-09 (radar), CC-10 (semáforos), CC-12 (barreras peatonales), etc. |

### 3.3 Faltan elementos de costo no incluidos

| Elemento | ¿Está en imagen? | ¿Debe estar? | Observación |
|----------|------------------|--------------|-------------|
| **Instalación y puesta en marcha** | No | Sí | 15–25% del valor de equipos |
| **Ingeniería de detalle** | No | Sí | 8–12% del CAPEX |
| **Software y licencias** | No | Sí | Plataforma CCO, integración, video management |
| **OPEX años 1–5** | No | Sí | Mantenimiento, energía, conectividad, personal |
| **Contingencia técnica** | No | Sí | 10–15% del CAPEX total |
| **CCO (Centro de Control)** | No | Sí | Edificación, equipos CCO, videowall, servidores |
| **Pruebas y aceptación** | No | Sí | FAT, SAT, pruebas de interoperabilidad |

---

## 4. ESTRUCTURA DE COSTOS PROPUESTA — COMPLETA

Basada en el Entregable 1, la estructura de costos debe organizarse así:

### 4.1 Jerarquía de desglose (WBS)

```
PROYECTO APP CHÍA-GIRARDOT — COMPONENTE ITS
│
├── 1. INFRAESTRUCTURA DE COMUNICACIONES Y ENERGÍA
│   ├── 1.1 Red Troncal de Fibra Óptica (por km de vía)
│   ├── 1.2 Red de Distribución Local (switches, UTP, PoE)
│   ├── 1.3 Radio Enlaces de Respaldo (por puntos críticos)
│   ├── 1.4 Suministro Eléctrico y Acometidas
│   ├── 1.5 Sistemas de Respaldo Energético (UPS, solar, baterías)
│   └── 1.6 Telegestión y Eficiencia Energética
│
├── 2. SISTEMAS DE DETECCIÓN Y VIGILANCIA
│   ├── 2.1 CCTV (fijas, PTZ, AID) — por punto de monitoreo
│   ├── 2.2 Detección de Tráfico (bucles, radar, acústico)
│   ├── 2.3 Paneles de Mensaje Variable (DMS full matrix, dot matrix)
│   ├── 2.4 Señalización de Velocidad Variable (VSL)
│   └── 2.5 Puntos de Emergencia (SOS/ECS)
│
├── 3. SISTEMAS DE CONTROL Y ACTUACIÓN
│   ├── 3.1 Control Semafórico Inteligente (intersecciones urbanas)
│   ├── 3.2 Protección Peatonal Activa (barreras, zonas escolares)
│   ├── 3.3 Iluminación Inteligente (túneles, tramos críticos)
│   ├── 3.4 Sistemas de Seguridad en Túneles (riego, ventilación, humo)
│   └── 3.5 Cierre de Túneles y Alerta Sísmica
│
├── 4. SISTEMAS DE RECAUDO Y PEAJE
│   ├── 4.1 Peaje Electrónico (RFID/AVI) — 4 estaciones
│   ├── 4.2 Clasificación Vehicular Automática
│   ├── 4.3 Cabinas y Barreras de Peaje
│   └── 4.4 Sistema de Back-office de Recaudo
│
├── 5. SISTEMAS DE CONTROL DE CARGA
│   ├── 5.1 Pesaje en Movimiento (WIM)
│   ├── 5.2 Plataforma de Pesaje Estática
│   └── 5.3 Precinto Electrónico
│
├── 6. CENTRO DE CONTROL Y PLATAFORMA (CCO)
│   ├── 6.1 Edificación/Adaptación CCO
│   ├── 6.2 Videowall y Estaciones de Operador
│   ├── 6.3 Servidores y Almacenamiento (on-premise/cloud)
│   ├── 6.4 Software de Integración y Gestión (SCADA/ITS)
│   ├── 6.5 Ciberseguridad Perimetral y de Red
│   └── 6.6 Respaldo Satelital (SAT-B)
│
├── 7. INSTALACIÓN, PUESTA EN MARCHA Y PRUEBAS
│   ├── 7.1 Instalación de Campo (mano de obra, montaje)
│   ├── 7.2 Ingeniería de Detalle y Supervisión
│   ├── 7.3 Pruebas FAT, SAT, Interoperabilidad
│   └── 7.4 Capacitación y Transferencia de Conocimiento
│
└── 8. OPEX AÑOS 1–5 (Estimación)
    ├── 8.1 Mantenimiento preventivo y correctivo
    ├── 8.2 Energía eléctrica y conectividad
    ├── 8.3 Personal de operación y monitoreo
    └── 8.4 Renovación de equipos de corta vida (5 años)
```

### 4.2 Niveles de desglose por tramo

Cada uno de los **15 Tramos / UF** debe desglosarse en:

| Nivel | Descripción | Ejemplo |
|-------|-------------|---------|
| **UF** | Unidad Funcional (15 total) | UF 1 — Variante Chía (3,086 km) |
| **Sector** | Sector operativo (Norte, Centro, Sur) | Norte — Acceso Bogotá |
| **Tramo** | Tramo físico de diseño | Tramo 1.1: Variante Chía Principal |
| **Subtramo** | Sección homogénea | Subtramo 1.1.1: Glorieta Norte (0,5 km) |
| **Tipología** | Paquete ITS asignado | Paquete 4-A (Urbano Avanzado) + Mod. PE-01 |
| **Sistema** | Grupo funcional (8 sistemas) | Detección y Vigilancia |
| **Componente** | CC individual (CC-01 a CC-42) | CC-01 CCTV PTZ |
| **Unidad** | Item de costo | Cantidad × Valor unitario × Especificación |

---

## 5. VALORES UNITARIOS REFERENCIALES DE MERCADO (Colombia, 2026)

> **Nota:** Estos valores son referencias de mercado para proyectos de infraestructura vial en Colombia. No son cotizaciones finales. Deben validarse con RFI/RFQ a proveedores.

| Código | Componente | Unidad | Valor referencial COP | Fuente / Justificación |
|--------|------------|--------|----------------------|------------------------|
| CC-01 | CCTV PTZ 4K, 30×, IR 200m | Unidad | $12.000.000 – $18.000.000 | Proyectos ANI, peaje, túneles |
| CC-02 | CCTV fija 2MP, IR 50m | Unidad | $4.000.000 – $6.000.000 | Instalación estándar vial |
| CC-03 | CCTV con AID (software incluido) | Unidad | $18.000.000 – $28.000.000 | Requiere licencia de análisis |
| CC-04 | ECS / SOS columna IP, IK10 | Unidad | $15.000.000 – $22.000.000 | Resistente vandalismo, intemperie |
| CC-05 | DMS Full Matrix LED 16×80 | Unidad | $95.000.000 – $150.000.000 | Alta visibilidad, control NTCIP |
| CC-06 | DMS Dot Matrix 16×32 | Unidad | $35.000.000 – $55.000.000 | Mensaje simple, costo-efectivo |
| CC-07 | VSL (señal LED variable) | Unidad | $8.000.000 – $12.000.000 | Panel velocidad + control |
| CC-08 | VDS bucle inductivo (dual) | Unidad | $3.500.000 – $5.500.000 | Incluye detector rack |
| CC-09 | VDS radar Doppler | Unidad | $6.000.000 – $9.000.000 | No invasivo, fácil montaje |
| CC-10 | Semáforo inteligente (cabeza LED) | Unidad | $4.000.000 – $6.000.000 | Cabeza + controlador local |
| CC-11 | Controlador de intersección (TSC) | Unidad | $8.000.000 – $12.000.000 | NTCIP 1202, adaptativo |
| CC-12 | Barrera peatonal automática | Unidad | $12.000.000 – $18.000.000 | Motor, sensores, control |
| CC-13 | Iluminación LED túnel (alta potencia) | Unidad | $2.500.000 – $4.000.000 | Por luminaria, control DALI |
| CC-14 | Sistema de riego túneles | Sistema | $800.000.000 – $1.200.000.000 | Por túnel (bomba, tanque, rociadores) |
| CC-15 | Ventilación túneles (jet fan) | Unidad | $45.000.000 – $70.000.000 | Por ventilador axial reversible |
| CC-16 | Gabinete de control NEMA 4X, 12U | Unidad | $6.000.000 – $9.000.000 | Rack 19", climatización, IP65 |
| CC-17 | Servidor de borde industrial | Unidad | $15.000.000 – $22.000.000 | Edge computing, GPU para AID |
| CC-18 | Fibra óptica monomodo G.652D (instalada) | km | $18.000.000 – $35.000.000 | Incluye ducto, empalmes, ODF |
| CC-19 | Switch industrial 16 puertos, PoE+ | Unidad | $4.000.000 – $6.000.000 | Gestión capa 2, IP40 |
| CC-20 | Radio enlace microondas 5,8 GHz (par) | Par | $12.000.000 – $18.000.000 | Antena + radio, 300 Mbps |
| CC-21 | RSU V2X / Antena 5G privada | Unidad | $25.000.000 – $40.000.000 | Unidad de comunicación vehicular |
| CC-22 | UPS on-line 1 kVA, SNMP | Unidad | $3.500.000 – $5.000.000 | Doble conversión, 4h autonomía |
| CC-23 | Panel solar 300 Wp + estructura | Unidad | $2.500.000 – $4.000.000 | Incluye estructura de montaje |
| CC-24 | Batería Li-Ion 48V 200 Ah | Unidad | $8.000.000 – $12.000.000 | Ciclo profundo, 5.000 ciclos |
| CC-25 | Acometida eléctrica + transformador | Unidad | $15.000.000 – $25.000.000 | Media tensión a baja tensión |
| CC-26 | Tablero distribución + protecciones | Unidad | $4.000.000 – $6.000.000 | Tablero general de gabinete |
| CC-27 | Puesta a tierra + pararrayos | Unidad | $2.000.000 – $3.000.000 | Sistema completo de protección |
| CC-28 | Antena RFID / AVI DSRC 5,8 GHz | Unidad | $8.000.000 – $12.000.000 | Lector peaje electrónico |
| CC-29 | Validador categoría (láser + cámara) | Unidad | $12.000.000 – $18.000.000 | Clasificación automática |
| CC-30 | Barrera de peaje automática | Unidad | $6.000.000 – $9.000.000 | Brazo de 3–6 m, motor hidráulico |
| CC-31 | Cabina de peaje (modular) | Unidad | $45.000.000 – $65.000.000 | Estructura, climatización, equipos |
| CC-32 | WIM (báscula en movimiento) | Unidad | $120.000.000 – $180.000.000 | Plataforma + sensores + electrónica |
| CC-33 | Plataforma pesaje estático | Unidad | $80.000.000 – $120.000.000 | Báscula legal para fiscalización |
| CC-34 | Precinto electrónico | Unidad | $2.000.000 – $3.000.000 | Sello digital GPS + RF |
| CC-35 | Sensor humo/CO túnel | Unidad | $3.000.000 – $4.500.000 | Dual humo + monóxido |
| CC-36 | Compuerta de cierre túnel | Unidad | $55.000.000 – $80.000.000 | Cierre rápido, motorizado |
| CC-37 | Sensor sísmico / acelerómetro | Unidad | $8.000.000 – $12.000.000 | Monitoreo estructural continuo |
| CC-38 | Terminal satelital SAT-B | Unidad | $18.000.000 – $28.000.000 | Respaldo comunicación global |
| CC-39 | Firewall industrial / IPS | Unidad | $6.000.000 – $10.000.000 | Protección perimetral de red |
| CC-40 | Estación meteorológica | Unidad | $8.000.000 – $12.000.000 | Viento, temperatura, visibilidad, lluvia |
| CC-41 | Controlador telegestión (MSG) | Unidad | $5.000.000 – $8.000.000 | IoT energy management |
| CC-42 | Gateway NTCIP multiprotocolo | Unidad | $4.000.000 – $6.000.000 | Traducción NTCIP 1201–1204 |

---

## 6. RANGO INDICATIVO DE INVERSIÓN TOTAL

Basado en los valores referenciales y la extensión del proyecto (306 km, 15 UF, 4 peajes, 2 túneles, 12 intersecciones):

| Concepto | Rango estimado (COP) | % del total |
|----------|----------------------|-----------|
| **Infraestructura de comunicaciones y energía** | $45.000 – $85.000 millones | 15–18% |
| **Detección y vigilancia** (634 dispositivos estimados) | $65.000 – $110.000 millones | 22–25% |
| **Control y actuación** (túneles + intersecciones) | $35.000 – $60.000 millones | 12–15% |
| **Recaudo y peaje** (4 estaciones, TPDA 40.000) | $55.000 – $85.000 millones | 18–20% |
| **Control de carga** (WIM + plataforma) | $15.000 – $25.000 millones | 5–6% |
| **Centro de Control y plataforma** | $25.000 – $40.000 millones | 8–10% |
| **Instalación, ingeniería y pruebas** | $45.000 – $70.000 millones | 15–18% |
| **Contingencia técnica (12%)** | $35.000 – $55.000 millones | — |
| **TOTAL CAPEX ITS** | **$320.000 – $530.000 millones** | **100%** |
| **OPEX años 1–5** (estimado) | $80.000 – $130.000 millones | — |

**Comparación con referencia:**
- Proyecto Estanquillo–Popayán (366 km, 5G, sin peajes): adjudicado en **$8,8 billones COP total** (obra civil + ITS + todo)
- Estimación ITS Chía-Girardot (306 km, 4 peajes, 2 túneles): **$320–530 mil millones COP** = **3,6% – 6,0%** del total del proyecto
- Esto es consistente con el 3–8% de CAPEX que representa ITS en concesiones viales de alta complejidad.

---

## 7. RECOMENDACIONES PARA ARMAR EL MODELO FINANCIERO

### 7.1 Estructura de la hoja de cálculo (Excel)

Para cada uno de los **15 UF / Tramos**, crear pestañas con esta estructura:

| Columna A | Columna B | Columna C | Columna D | Columna E | Columna F | Columna G | Columna H |
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| **UF** | **Tramo / Subtramo** | **Sistema** | **CC** | **Componente** | **Cantidad** | **Unidad** | **Valor Unitario** | **Valor Total** |
| UF 1 | Tramo 1.1 — Variante Chía (0,000–3,086 km) | Red de Comunicaciones | CC-18 | Fibra óptica monomodo G.652D | 3,1 | km | $25.000.000 | $77.500.000 |
| UF 1 | Tramo 1.1 — Variante Chía | Red de Comunicaciones | CC-19 | Switch industrial 16 ptos | 2 | unidad | $5.000.000 | $10.000.000 |
| ... | ... | ... | ... | ... | ... | ... | ... | ... |

### 7.2 Fórmulas de validación

1. **Densidad de componentes por km:** cada UF debe tener una densidad coherente con su tipología (Paquete 1 a 4)
2. **Verificación de doble calzada:** si el componente va en ambos sentidos, cantidad = 2 × cantidad por sentido
3. **Suma por sistema:** cada uno de los 8 sistemas debe sumar un % coherente del total
4. **Suma por UF:** cada UF debe sumar un costo proporcional a su longitud y complejidad

### 7.3 Próximos pasos para completar el modelo

| Paso | Acción | Responsable | Entregable |
|------|--------|-------------|------------|
| 1 | Validar lista de 42 CC con Entregable 1 oficial | ZEUS / Equipo | Lista validada |
| 2 | Asignar cantidades por CC para cada uno de los 15 UF | Equipo técnico | Matriz 15×42 |
| 3 | Obtener cotizaciones reales de 3 proveedores por sistema | Compras / RFI | Cotizaciones |
| 4 | Ajustar valores unitarios con cotizaciones reales | Financiero | Modelo actualizado |
| 5 | Agregar instalación, ingeniería, OPEX, contingencia | Financiero | Modelo completo |
| 6 | Validar totales contra % de CAPEX del proyecto total | Director de proyecto | Aprobación |

---

## 8. CONCLUSIÓN

La estructura de costos recibida como **referencia** es útil como **formato de presentación** pero **no puede usarse como base para decisiones de inversión** ni para licitación porque:

1. **Faltan 37 de 42 componentes** definidos en el Entregable 1
2. **Los valores unitarios no son reales** (todos a $250.000)
3. **Faltan sistemas enteros** (peajes, túneles, control de carga, CCO)
4. **No incluye costos indirectos** (instalación, ingeniería, OPEX, contingencia)

**Lo que se propone crear:**
- Una **matriz completa de 15 UF × 42 CC** con cantidades específicas por tramo
- **Valores unitarios referenciales de mercado** (la tabla de la sección 5)
- **Estructura de Excel** con fórmulas de validación por densidad, doble calzada, y % por sistema
- **Rango total CAPEX ITS: $320.000 – $530.000 millones COP**

¿Se procede a crear el modelo Excel completo con la matriz 15×42 y los valores unitarios referenciales? ⚡
