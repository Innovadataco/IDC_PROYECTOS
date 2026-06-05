# PROPUESTA DE ESTRUCTURA DE EQUIPAMIENTO POR LOS 15 TRAMOS
## APP Chía-Girardot — Modelo Financiero y Despliegue ITS

**Fecha:** Junio 2026
**Proyecto:** APP Chía-Girardot — Estructuración Tecnológica ITS
**Versión:** 1.0 — Propuesta para validación

---

## 1. METODOLOGÍA DE DESPLIEGUE

### 1.1 Principio de Asignación

Cada tramo recibe equipamiento basado en **tres variables**:

| Variable | Descripción | Fuente de datos |
|----------|-------------|----------------|
| **T** — Tipología vial | Urbano, arterial, rural, túnel, peaje, montaña | Diseño de obra civil ICCU |
| **R** — Riesgo operativo | TPDA, historia de siniestralidad, presencia escolar, zona crítica | Estudios de tráfico, Policía de Carreteras |
| **C** — Condición brownfield | Disponibilidad de energía, fibra, ductos | Inventario de infraestructura existente |

### 1.2 Fórmula de Densidad

```
Densidad de Componentes = (T × R × C) / K

Donde:
- T = Factor de tipología (1.0 a 4.5)
- R = Factor de riesgo (1.0 a 2.2)
- C = Factor de condición (1.0 a 1.45)
- K = Constante de ajuste = 1.2
```

### 1.3 Paquetes ITS por Tipología

| Paquete | Tipología | Factor T | Componentes base por km | Tramos aplicables |
|-----------|-----------|----------|------------------------|-------------------|
| **Paquete 1** | Rural simple | 1.0 | 2-3 CC/km | UF 10, 11, 12-15 |
| **Paquete 2** | Arterial rural | 1.5 | 3-5 CC/km | UF 8, 9 |
| **Paquete 3** | Arterial interurbano | 2.0 | 5-7 CC/km | UF 6, 7 |
| **Paquete 4-A** | Urbano avanzado | 4.5 | 8-12 CC/km | UF 1, 2, 4A, 4B |
| **Paquete 4-B** | Peaje + Arterial | 3.0 | 7-10 CC/km | UF 3 |
| **Paquete 5** | Montaña + Túneles | 3.5 | 10-15 CC/km | UF 5 |
| **Paquete 6** | Túnel soterrado | 4.0 | 12-18 CC/km | UF 4C |
| **Mod. PE-01** | Protección Escolar | +1.5 | +2-3 CC por zona | UF 1 (km 1+200) |
| **Mod. TU-01** | Túnel de Montaña | +2.0 | +5-8 CC por túnel | UF 5 (2 túneles) |

---

## 2. RESUMEN DE LOS 15 TRAMOS / UNIDADES FUNCIONALES

| UF | Denominación | km | TPDA | Tipología | Paquete | Complejidad |
|----|-------------|-----|------|-----------|---------|-------------|
| **UF 1** | Variante Chía | 3,086 | 45.000 | Urbano | 4-A + PE-01 | 🔴 Alta |
| **UF 2** | Variante Cota | 3,500 | 42.000 | Urbano | 4-A | 🔴 Alta |
| **UF 3** | Cota — La Tebaida | 4,048 | 38.000 | Arterial + Peaje | 4-B | 🔴 Alta |
| **UF 4A** | Funza — Mosquera Oriental | 1,700 | 36.000 | Urbano | 4-A | 🟡 Media-Alta |
| **UF 4B** | Funza — Mosquera Occidental | 0,700 | 34.000 | Urbano corto | 4-A | 🟡 Media |
| **UF 4C** | Funza Soterrado | 3,700 | 35.000 | Túnel soterrado | 6 | 🔴 Máxima |
| **UF 5** | Montaña Mondoñedo | 7,000 | 28.000 | Montaña + Túneles | 5 + TU-01 | 🔴 Máxima |
| **UF 6** | Conexión Soacha | 7,900 | 32.000 | Arterial + Urbano | 3 | 🟡 Media |
| **UF 7** | Mondoñedo — La Gran Vía | 4,500 | 25.000 | Arterial | 2 | 🟢 Media-Baja |
| **UF 8** | La Gran Vía — La Mesa | 1,000 | 22.000 | Arterial rural | 2 | 🟢 Baja |
| **UF 9** | La Mesa — Anapoima | 0,600 | 20.000 | Arterial rural | 2 | 🟢 Baja |
| **UF 10** | Anapoima — Tocaima | 0,300 | 18.000 | Rural | 1 | 🟢 Baja |
| **UF 11** | Tocaima — Girardot | 0,700 | 15.000 | Rural | 1 | 🟢 Baja |
| **UF 12-15** | Colectoras y Complementarias | 148,000 | 5.000-15.000 | Colectora / Rural | 1 | 🟢 Baja |

---

## 3. ESTRUCTURA DE EQUIPAMIENTO POR TRAMO

### 3.1 UF 1 — Variante Chía (3,086 km) | Paquete 4-A + PE-01

**Características:** Urbano, 6 intersecciones, 3 glorietas, 1 zona escolar, TPDA 45.000

#### A. INFRAESTRUCTURA DE CONECTIVIDAD

| Componente | Cantidad | Unidad | Justificación |
|------------|----------|--------|---------------|
| **Fibra óptica monomodo G.652D** | 3,5 | km | Recorrido tramo + 15% para risers y empalmes |
| **Switch industrial 16 puertos** | 4 | unidad | 1 por cada 750m de tramo urbano |
| **Switch industrial 8 puertos** | 3 | unidad | Glorietas y zona escolar |
| **Radio enlace 5.8 GHz (par)** | 2 | par | Respaldo Glorieta Norte y Glorieta Sur |
| **Ethernet UTP Cat 6A** | 2.500 | m | Conexiones locales dentro de intersecciones |
| **Gateway NTCIP (CC-42)** | 5 | unidad | 1 por cada gabinete de campo |

#### B. ENERGÍA

| Componente | Cantidad | Unidad | Justificación |
|------------|----------|--------|---------------|
| **Acometida eléctrica + transformador** | 3 | unidad | Centro del tramo tiene red; extremos no |
| **UPS 1 kVA on-line** | 5 | unidad | 1 por cada gabinete de campo |
| **Panel solar 300 Wp** | 2 | unidad | Extremos sin red (km 0+000 y km 3+086) |
| **Batería Li-Ion 48V 200 Ah** | 2 | unidad | Respaldo nocturno para gabinetes solares |
| **Tablero de distribución** | 5 | unidad | 1 por gabinete |
| **Puesta a tierra** | 5 | unidad | 1 por gabinete |

#### C. SISTEMAS DE DETECCIÓN Y VIGILANCIA (CC-01 a CC-09)

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-01: CCTV PTZ** | 8 | unidad | 2 en cada glorieta (cobertura 360°) |
| **CC-02: CCTV fija** | 12 | unidad | 2 por cada intersección semaforizada |
| **CC-03: CCTV con AID** | 2 | unidad | Glorieta Norte y Glorieta Central (máx. riesgo) |
| **CC-04: SOS / ECS** | 4 | unidad | 1 por cada glorieta + 1 en zona escolar |
| **CC-05: DMS Full Matrix** | 4 | unidad | Antes de cada glorieta (km 0+100, 0+600, 1+800, 2+400) |
| **CC-06: DMS Dot Matrix** | 6 | unidad | Accesos secundarios |
| **CC-07: VSL** | 3 | unidad | Entrada zona escolar, entrada glorieta sur, cambio de velocidad |
| **CC-08: VDS bucle inductivo** | 24 | unidad | 4 por cada glorieta (4 ramas) |
| **CC-09: VDS radar** | 6 | unidad | Tramos entre intersecciones |

#### D. CONTROL Y ACTUACIÓN (CC-10 a CC-15)

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-10: Semáforo inteligente** | 12 | cabeza | 2 por cada intersección semaforizada (6 intersecciones) |
| **CC-11: Controlador de intersección (TSC)** | 6 | unidad | 1 por cada intersección |
| **CC-12: Barrera peatonal** | 2 | unidad | Zona escolar (km 1+200) — ambos lados |
| **CC-13: Iluminación LED** | 24 | unidad | 12 luminarias por sentido, reforzadas en glorietas |
| **CC-14: Riego túneles** | 0 | unidad | No aplica (sin túneles) |
| **CC-15: Ventilación túneles** | 0 | unidad | No aplica |

#### E. GABINETES Y ESTRUCTURA (CC-16)

| Componente | Cantidad | Unidad | Nota |
|------------|----------|--------|------|
| **CC-16: Gabinete de control** | 5 | unidad | 1 por cada intersección/glorieta + 1 zona escolar |

**Total componentes de campo UF 1:** ~142 unidades + 5 gabinetes + infraestructura

---

### 3.2 UF 2 — Variante Cota (3,500 km) | Paquete 4-A

**Características:** Urbano, 5 intersecciones, 2 glorietas, TPDA 42.000

#### A. INFRAESTRUCTURA DE CONECTIVIDAD

| Componente | Cantidad | Unidad | Justificación |
|------------|----------|--------|---------------|
| **Fibra óptica monomodo G.652D** | 4,0 | km | Tramo + 15% |
| **Switch industrial 16 puertos** | 4 | unidad | Distribución urbana |
| **Switch industrial 8 puertos** | 2 | unidad | Puntos críticos |
| **Radio enlace 5.8 GHz (par)** | 2 | par | Respaldo en glorietas |
| **Ethernet UTP Cat 6A** | 2.000 | m | Conexiones locales |
| **Gateway NTCIP (CC-42)** | 4 | unidad | Por gabinete |

#### B. ENERGÍA

| Componente | Cantidad | Unidad | Justificación |
|------------|----------|--------|---------------|
| **Acometida eléctrica** | 3 | unidad | Red parcial en tramo |
| **UPS 1 kVA** | 4 | unidad | Por gabinete |
| **Panel solar 300 Wp** | 2 | unidad | Extremos sin red |
| **Batería Li-Ion 48V 200 Ah** | 2 | unidad | Respaldo solar |
| **Tablero de distribución** | 4 | unidad | |
| **Puesta a tierra** | 4 | unidad | |

#### C. DETECCIÓN Y VIGILANCIA

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-01: CCTV PTZ** | 6 | unidad | 3 en cada glorieta |
| **CC-02: CCTV fija** | 10 | unidad | 2 por intersección semaforizada |
| **CC-03: CCTV con AID** | 2 | unidad | 2 glorietas críticas |
| **CC-04: SOS / ECS** | 3 | unidad | 1 por glorieta + 1 punto medio |
| **CC-05: DMS Full Matrix** | 4 | unidad | Antes de glorietas |
| **CC-06: DMS Dot Matrix** | 5 | unidad | Accesos secundarios |
| **CC-07: VSL** | 3 | unidad | Cambios de velocidad |
| **CC-08: VDS bucle inductivo** | 16 | unidad | 4 por glorieta (4 ramas) |
| **CC-09: VDS radar** | 5 | unidad | Tramos entre intersecciones |

#### D. CONTROL Y ACTUACIÓN

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-10: Semáforo inteligente** | 10 | cabeza | 2 por intersección (5 intersecciones) |
| **CC-11: Controlador TSC** | 5 | unidad | 1 por intersección |
| **CC-12: Barrera peatonal** | 0 | unidad | Sin zona escolar identificada |
| **CC-13: Iluminación LED** | 20 | unidad | 10 por sentido |

#### E. GABINETES

| Componente | Cantidad | Unidad |
|------------|----------|--------|
| **CC-16: Gabinete de control** | 4 | unidad |

**Total componentes de campo UF 2:** ~118 unidades + 4 gabinetes

---

### 3.3 UF 3 — Cota – La Tebaida (4,048 km) | Paquete 4-B (Peaje + Arterial)

**Características:** Arterial con peaje La Tebaida, TPDA 38.000, zona industrial

#### A. INFRAESTRUCTURA DE CONECTIVIDAD

| Componente | Cantidad | Unidad | Justificación |
|------------|----------|--------|---------------|
| **Fibra óptica monomodo G.652D** | 4,5 | km | Tramo + peaje |
| **Switch industrial 24 puertos** | 2 | unidad | Peaje (alta densidad de equipos) |
| **Switch industrial 16 puertos** | 3 | unidad | Distribución |
| **Switch industrial 8 puertos** | 2 | unidad | Puntos medios |
| **Radio enlace 5.8 GHz (par)** | 2 | par | Respaldo peaje + punto crítico |
| **Ethernet UTP Cat 6A** | 3.000 | m | Peaje + intersecciones |
| **Gateway NTCIP (CC-42)** | 5 | unidad | |

#### B. ENERGÍA

| Componente | Cantidad | Unidad | Justificación |
|------------|----------|--------|---------------|
| **Acometida eléctrica** | 3 | unidad | Incluye subestación para peaje |
| **UPS 3 kVA (peaje)** | 1 | unidad | Respaldo para cabinas y sistemas |
| **UPS 1 kVA (campo)** | 4 | unidad | |
| **Panel solar 300 Wp** | 2 | unidad | Puntos sin red |
| **Batería Li-Ion 48V 200 Ah** | 2 | unidad | |
| **Tablero de distribución** | 5 | unidad | |
| **Puesta a tierra** | 5 | unidad | |

#### C. DETECCIÓN Y VIGILANCIA

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-01: CCTV PTZ** | 4 | unidad | Peaje (2 por sentido) |
| **CC-02: CCTV fija** | 8 | unidad | 4 por sentido en peaje + 2 intersecciones |
| **CC-03: CCTV con AID** | 1 | unidad | Peaje (detección de incidentes) |
| **CC-04: SOS / ECS** | 3 | unidad | 1 antes del peaje + 2 puntos de emergencia |
| **CC-05: DMS Full Matrix** | 3 | unidad | 2 antes del peaje (1 por sentido) + 1 en acceso |
| **CC-06: DMS Dot Matrix** | 2 | unidad | Accesos alternos |
| **CC-07: VSL** | 2 | unidad | Antes y después del peaje |
| **CC-08: VDS bucle inductivo** | 8 | unidad | Peaje (4 por sentido) |
| **CC-09: VDS radar** | 4 | unidad | Zonas de transición |

#### D. PEAJE Y RECAUDO (CC-28 a CC-31) — **SISTEMA COMPLETO**

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-28: Antena RFID / AVI** | 4 | unidad | 2 por sentido (carril principal + respaldo) |
| **CC-29: Validador de categoría** | 2 | unidad | 1 por sentido (clasificación vehicular) |
| **CC-30: Barrera de peaje** | 4 | unidad | 2 por sentido |
| **CC-31: Cabina de peaje** | 2 | unidad | 1 por sentido (estructura modular) |

#### E. CONTROL DE CARGA (CC-32 a CC-34)

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-32: WIM (Weigh In Motion)** | 1 | unidad | 1 por sentido en peaje (o poste de control cercano) |
| **CC-33: Plataforma pesaje estático** | 0 | unidad | No en tramo (en área de control designada) |
| **CC-34: Precinto electrónico** | 1 | unidad | Sistema de control de carga |

#### F. CONTROL Y ACTUACIÓN

| Componente | Cantidad | Unidad | Ubicación |
|------------|----------|--------|-----------|
| **CC-10: Semáforo inteligente** | 4 | cabeza | 2 intersecciones semaforizadas |
| **CC-11: Controlador TSC** | 2 | unidad | |
| **CC-13: Iluminación LED** | 16 | unidad | 8 por sentido |

#### G. GABINETES

| Componente | Cantidad | Unidad |
|------------|----------|--------|
| **CC-16: Gabinete de control** | 5 | unidad |

**Total componentes de campo UF 3:** ~85 unidades + 5 gabinetes + sistema completo de peaje

---

### 3.4 UF 4A — Funza – Mosquera Oriental (1,700 km) | Paquete 4-A

**Características:** Urbano, 3 intersecciones, 1 glorieta, TPDA 36.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 2,0 km |
| | Switches | 3 unidades |
| | Radio enlaces | 1 par |
| | Gateway NTCIP | 3 unidades |
| **Energía** | Acometida + transformador | 2 unidades |
| | UPS 1 kVA | 3 unidades |
| | Solar + batería | 1 set |
| **Detección** | CCTV PTZ | 3 unidades |
| | CCTV fija | 6 unidades |
| | CCTV AID | 1 unidad |
| | SOS | 2 unidades |
| | DMS Full Matrix | 3 unidades |
| | DMS Dot Matrix | 2 unidades |
| | VSL | 2 unidades |
| | VDS bucle | 8 unidades |
| | VDS radar | 3 unidades |
| **Control** | Semáforos | 6 cabezas |
| | Controladores TSC | 3 unidades |
| | Iluminación LED | 10 unidades |
| **Gabinetes** | CC-16 | 3 unidades |

**Total componentes UF 4A:** ~62 unidades + 3 gabinetes

---

### 3.5 UF 4B — Funza – Mosquera Occidental (0,700 km) | Paquete 4-A

**Características:** Urbano corto, 2 intersecciones, TPDA 34.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 1,0 km |
| | Switches | 2 unidades |
| | Gateway NTCIP | 2 unidades |
| **Energía** | Acometida | 1 unidad |
| | UPS | 2 unidades |
| **Detección** | CCTV PTZ | 2 unidades |
| | CCTV fija | 4 unidades |
| | SOS | 1 unidad |
| | DMS Full Matrix | 2 unidades |
| | VSL | 1 unidad |
| | VDS bucle | 4 unidades |
| | VDS radar | 2 unidades |
| **Control** | Semáforos | 4 cabezas |
| | Controladores | 2 unidades |
| **Gabinetes** | CC-16 | 2 unidades |

**Total componentes UF 4B:** ~32 unidades + 2 gabinetes

---

### 3.6 UF 4C — Funza Soterrado (3,700 km) | Paquete 6 (Túnel Soterrado)

**Características:** Túnel soterrado, TPDA 35.000, **máxima complejidad**

#### SISTEMAS ESPECIALES DE TÚNEL (INCLUIDOS EN ESTA UF)

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Seguridad túnel** | CC-35: Sensor humo/CO | 12 unidades (cada 300m) |
| | CC-36: Compuerta cierre | 4 unidades (2 por sentido) |
| | CC-14: Riego túneles | 1 sistema completo |
| | CC-15: Ventilación jet fan | 8 unidades |
| | CC-37: Sensor sísmico | 2 unidades |
| **Conectividad** | Fibra óptica (túnel) | 4,5 km |
| | Switches 24 ptos | 4 unidades (redundancia) |
| | Radio enlace | 2 pares (entrada/salida) |
| **Energía** | Acometida + transformador | 2 unidades |
| | UPS 3 kVA (túnel) | 2 unidades |
| | UPS 1 kVA (campo) | 3 unidades |
| | Panel solar (campo) | 2 unidades |
| **Detección** | CCTV PTZ (túnel) | 6 unidades |
| | CCTV térmica (túnel) | 4 unidades |
| | CCTV fija (exterior) | 6 unidades |
| | CCTV AID | 2 unidades |
| | SOS (túnel) | 4 unidades (cada 1km) |
| | SOS (exterior) | 2 unidades |
| | DMS Full Matrix | 4 unidades (2 por sentido) |
| | VSL | 4 unidades |
| | VDS bucle | 8 unidades |
| **Iluminación** | CC-13: LED túnel alta potencia | 48 unidades |
| **Gabinetes** | CC-16 (túnel) | 4 unidades |
| | CC-16 (exterior) | 3 unidades |

**Total componentes UF 4C:** ~142 unidades + 7 gabinetes + sistemas de túnel completos

---

### 3.7 UF 5 — Montaña Mondoñedo (7,000 km) | Paquete 5 + TU-01

**Características:** Montaña, 2 túneles, TPDA 28.000, niebla, curvas pronunciadas

#### SISTEMAS ESPECIALES DE TÚNEL (2 túneles)

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Seguridad túnel** | CC-35: Sensor humo/CO | 8 unidades |
| | CC-36: Compuerta cierre | 4 unidades |
| | CC-14: Riego túneles | 1 sistema |
| | CC-15: Ventilación jet fan | 6 unidades |
| **Conectividad** | Fibra óptica | 8,5 km |
| | Switches 16 ptos | 4 unidades |
| | Radio enlace | 3 pares (montaña + túneles) |
| | 4G/5G privada | 2 unidades |
| **Energía** | Acometida | 2 unidades (solo en accesos) |
| | UPS 1 kVA | 6 unidades |
| | Panel solar | 4 unidades (toda la montaña sin red) |
| | Batería Li-Ion | 4 unidades |
| **Detección** | CCTV PTZ | 4 unidades |
| | CCTV térmica | 4 unidades (niebla) |
| | CCTV fija | 10 unidades |
| | CCTV AID | 2 unidades |
| | SOS | 4 unidades |
| | DMS Full Matrix | 4 unidades |
| | VSL | 4 unidades (curvas peligrosas) |
| | VDS bucle | 8 unidades |
| | VDS radar (inmune niebla) | 6 unidades |
| **Meteorología** | CC-40: Estación meteorológica | 2 unidades (cima + valle) |
| **Gabinetes** | CC-16 | 6 unidades |

**Total componentes UF 5:** ~85 unidades + 6 gabinetes + sistemas de túnel

---

### 3.8 UF 6 — Conexión Soacha (7,900 km) | Paquete 3 (Arterial + Urbano)

**Características:** Arterial con tramos urbanos, TPDA 32.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 9,5 km |
| | Switches 16 ptos | 4 unidades |
| | Switches 8 ptos | 2 unidades |
| | Radio enlace | 2 pares |
| **Energía** | Acometida | 3 unidades |
| | UPS 1 kVA | 5 unidades |
| | Solar + batería | 2 sets |
| **Detección** | CCTV PTZ | 4 unidades |
| | CCTV fija | 8 unidades |
| | CCTV AID | 1 unidad |
| | SOS | 3 unidades |
| | DMS Full Matrix | 3 unidades |
| | DMS Dot Matrix | 2 unidades |
| | VSL | 2 unidades |
| | VDS bucle | 8 unidades |
| | VDS radar | 4 unidades |
| **Control** | Semáforos | 4 cabezas |
| | Controladores | 2 unidades |
| | Iluminación LED | 12 unidades |
| **Gabinetes** | CC-16 | 5 unidades |

**Total componentes UF 6:** ~78 unidades + 5 gabinetes

---

### 3.9 UF 7 — Mondoñedo – La Gran Vía (4,500 km) | Paquete 2 (Arterial)

**Características:** Arterial interurbano, TPDA 25.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 5,5 km |
| | Switches 16 ptos | 3 unidades |
| | Radio enlace | 1 par |
| **Energía** | Acometida | 2 unidades |
| | UPS 1 kVA | 3 unidades |
| | Solar + batería | 1 set |
| **Detección** | CCTV PTZ | 2 unidades |
| | CCTV fija | 6 unidades |
| | CCTV AID | 1 unidad |
| | SOS | 2 unidades |
| | DMS Full Matrix | 2 unidades |
| | VSL | 2 unidades |
| | VDS bucle | 4 unidades |
| | VDS radar | 3 unidades |
| **Iluminación** | LED | 8 unidades |
| **Gabinetes** | CC-16 | 3 unidades |

**Total componentes UF 7:** ~42 unidades + 3 gabinetes

---

### 3.10 UF 8 — La Gran Vía – La Mesa (1,000 km) | Paquete 2 (Arterial Rural)

**Características:** Arterial rural corto, TPDA 22.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 1,2 km |
| | Switch 16 ptos | 1 unidad |
| **Energía** | Acometida | 1 unidad |
| | UPS 1 kVA | 1 unidad |
| **Detección** | CCTV fija | 2 unidades |
| | CCTV AID | 1 unidad |
| | SOS | 1 unidad |
| | DMS Full Matrix | 1 unidad |
| | VSL | 1 unidad |
| | VDS radar | 2 unidades |
| **Gabinetes** | CC-16 | 1 unidad |

**Total componentes UF 8:** ~14 unidades + 1 gabinete

---

### 3.11 UF 9 — La Mesa – Anapoima (0,600 km) | Paquete 2 (Arterial Rural)

**Características:** Arterial rural corto, TPDA 20.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 0,8 km |
| | Switch 8 ptos | 1 unidad |
| **Energía** | Acometida | 1 unidad |
| | UPS 1 kVA | 1 unidad |
| **Detección** | CCTV fija | 2 unidades |
| | SOS | 1 unidad |
| | DMS Dot Matrix | 1 unidad |
| | VDS radar | 2 unidades |
| **Gabinetes** | CC-16 | 1 unidad |

**Total componentes UF 9:** ~10 unidades + 1 gabinete

---

### 3.12 UF 10 — Anapoima – Tocaima (0,300 km) | Paquete 1 (Rural)

**Características:** Rural, TPDA 18.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 0,5 km |
| | Switch 8 ptos | 1 unidad |
| **Energía** | Acometida | 1 unidad |
| | UPS 1 kVA | 1 unidad |
| **Detección** | CCTV fija | 1 unidad |
| | SOS | 1 unidad |
| | DMS Dot Matrix | 1 unidad |
| **Gabinetes** | CC-16 | 1 unidad |

**Total componentes UF 10:** ~7 unidades + 1 gabinete

---

### 3.13 UF 11 — Tocaima – Girardot (0,700 km) | Paquete 1 (Rural)

**Características:** Rural, TPDA 15.000

| Sistema | Componentes | Cantidad |
|---------|-------------|----------|
| **Conectividad** | Fibra óptica | 0,9 km |
| | Switch 8 ptos | 1 unidad |
| **Energía** | Acometida | 1 unidad |
| | UPS 1 kVA | 1 unidad |
| **Detección** | CCTV fija | 2 unidades |
| | SOS | 1 unidad |
| | DMS Dot Matrix | 1 unidad |
| **Gabinetes** | CC-16 | 1 unidad |

**Total componentes UF 11:** ~8 unidades + 1 gabinete

---

### 3.14 UF 12-15 — Colectoras y Complementarias (148,000 km) | Paquete 1 (Rural/Colectora)

**Características:** Colectoras rurales, TPDA 5.000-15.000, 148 km totales

#### APROXIMACIÓN POR DENSIDAD

Dado que son 148 km de colectoras distribuidas en múltiples tramos de baja densidad, se aplica un **Paquete 1 simplificado** con densidad mínima:

| Componente | Cantidad total | Unidad | Densidad |
|------------|----------------|--------|----------|
| **Fibra óptica** | 170 | km | 1,15 km por km de colectora |
| **Switch 8 puertos** | 45 | unidad | 1 cada 3-4 km |
| **UPS 1 kVA** | 45 | unidad | 1 por switch |
| **CCTV fija** | 90 | unidad | 1 cada 1,5 km (ambos sentidos) |
| **SOS** | 45 | unidad | 1 cada 3 km |
| **DMS Dot Matrix** | 30 | unidad | 1 cada 5 km |
| **VDS radar** | 45 | unidad | 1 cada 3 km |
| **Gabinete CC-16** | 45 | unidad | 1 por switch |

**Total componentes UF 12-15:** ~515 unidades + 45 gabinetes

---

## 4. CONSOLIDADO TOTAL DE EQUIPAMIENTO

### 4.1 Totales por Tipo de Componente

| Código | Componente | Unidad | Total UF 1-11 | Total UF 12-15 | TOTAL PROYECTO |
|--------|------------|--------|---------------|----------------|----------------|
| **CC-01** | CCTV PTZ | unidad | 31 | 0 | **31** |
| **CC-02** | CCTV fija | unidad | 72 | 90 | **162** |
| **CC-03** | CCTV con AID | unidad | 11 | 0 | **11** |
| **CC-04** | SOS / ECS | unidad | 25 | 45 | **70** |
| **CC-05** | DMS Full Matrix | unidad | 23 | 0 | **23** |
| **CC-06** | DMS Dot Matrix | unidad | 18 | 30 | **48** |
| **CC-07** | VSL | unidad | 18 | 0 | **18** |
| **CC-08** | VDS bucle inductivo | unidad | 76 | 0 | **76** |
| **CC-09** | VDS radar | unidad | 37 | 45 | **82** |
| **CC-10** | Semáforo inteligente | cabeza | 38 | 0 | **38** |
| **CC-11** | Controlador TSC | unidad | 19 | 0 | **19** |
| **CC-12** | Barrera peatonal | unidad | 2 | 0 | **2** |
| **CC-13** | Iluminación LED | unidad | 90 | 0 | **90** |
| **CC-14** | Riego túneles | sistema | 2 | 0 | **2** |
| **CC-15** | Ventilación jet fan | unidad | 14 | 0 | **14** |
| **CC-16** | Gabinete de control | unidad | 38 | 45 | **83** |
| **CC-17** | Servidor de borde | unidad | 0 | 0 | **0** *(ver nota)* |
| **CC-18** | Fibra óptica | km | 42 | 170 | **212** |
| **CC-19** | Switch industrial | unidad | 38 | 45 | **83** |
| **CC-20** | Radio enlace | par | 15 | 0 | **15** |
| **CC-21** | Antena 4G/5G / V2X | unidad | 2 | 0 | **2** |
| **CC-22** | UPS 1 kVA | unidad | 38 | 45 | **83** |
| **CC-23** | Panel solar 300 Wp | unidad | 15 | 0 | **15** |
| **CC-24** | Batería Li-Ion 48V | unidad | 15 | 0 | **15** |
| **CC-25** | Acometida eléctrica | unidad | 28 | 45 | **73** |
| **CC-26** | Tablero distribución | unidad | 38 | 45 | **83** |
| **CC-27** | Puesta a tierra | unidad | 38 | 45 | **83** |
| **CC-28** | Antena RFID / AVI | unidad | 4 | 0 | **4** |
| **CC-29** | Validador categoría | unidad | 2 | 0 | **2** |
| **CC-30** | Barrera de peaje | unidad | 4 | 0 | **4** |
| **CC-31** | Cabina de peaje | unidad | 2 | 0 | **2** |
| **CC-32** | WIM | unidad | 1 | 0 | **1** |
| **CC-33** | Plataforma pesaje | unidad | 0 | 0 | **0** |
| **CC-34** | Precinto electrónico | unidad | 1 | 0 | **1** |
| **CC-35** | Sensor humo/CO | unidad | 20 | 0 | **20** |
| **CC-36** | Compuerta cierre | unidad | 8 | 0 | **8** |
| **CC-37** | Sensor sísmico | unidad | 2 | 0 | **2** |
| **CC-38** | Terminal SAT-B | unidad | 0 | 0 | **0** *(ver nota)* |
| **CC-39** | Firewall industrial | unidad | 0 | 0 | **0** *(ver nota)* |
| **CC-40** | Estación meteorológica | unidad | 2 | 0 | **2** |
| **CC-41** | Controlador telegestión | unidad | 0 | 0 | **0** *(ver nota)* |
| **CC-42** | Gateway NTCIP | unidad | 38 | 45 | **83** |

**Nota sobre CC-17, CC-38, CC-39, CC-41:** Estos componentes son del Centro de Control (CCO) o de gabinetes específicos y se contabilizan en el capítulo de CCO, no por UF.

### 4.2 Total de Componentes de Campo (sin CCO)

| Categoría | Total Unidades |
|-----------|---------------|
| **Videovigilancia (CC-01 a CC-03)** | 204 |
| **Paneles y Señalización (CC-05 a CC-07)** | 89 |
| **Emergencia (CC-04)** | 70 |
| **Detección de Tráfico (CC-08 a CC-09)** | 158 |
| **Control Vial (CC-10 a CC-13)** | 149 |
| **Seguridad Túneles (CC-14 a CC-15, CC-35 a CC-37)** | 44 |
| **Comunicaciones (CC-18 a CC-21)** | 312 |
| **Energía (CC-22 a CC-27)** | 252 |
| **Peaje (CC-28 a CC-31)** | 12 |
| **Control de Carga (CC-32 a CC-34)** | 2 |
| **Gabinetes (CC-16)** | 83 |
| **Gateway (CC-42)** | 83 |
| **TOTAL** | **1.458** |

---

## 5. CENTRO DE CONTROL (CCO) — EQUIPAMIENTO GLOBAL

El CCO es único para todo el corredor y se instala en una ubicación central (propuesta: UF 6 o UF 7).

### 5.1 Infraestructura CCO

| Componente | Cantidad | Unidad | Descripción |
|------------|----------|--------|-------------|
| **Edificación / Adaptación** | 1 | unidad | 200-300 m², climatización, doble suministro eléctrico |
| **Videowall 3×3** | 1 | unidad | 9 pantallas 55" para operadores |
| **Estación de operador** | 8 | unidad | PC + 3 monitores + software |
| **Servidor principal** | 4 | unidad | Virtualización, alta disponibilidad |
| **Almacenamiento NAS/SAN** | 1 | sistema | 500 TB (video 30 días, datos 5 años) |
| **Switch core 48 puertos** | 2 | unidad | Redundancia |
| **Firewall perimetral** | 2 | unidad | redundancia |
| **UPS 10 kVA** | 2 | unidad | 1 hora autonomía + generador |
| **Generador diésel** | 1 | unidad | 8 horas autonomía |
| **Sistema SAT-B** | 1 | unidad | Respaldo satelital global |
| **CC-17: Servidor de borde** | 15 | unidad | 1 por UF para procesamiento local |
| **CC-38: Terminal SAT-B** | 1 | unidad | Comunicación global de respaldo |
| **CC-39: Firewall** | 1 | unidad | (en gabinetes de campo, se cuenta por UF) |
| **CC-41: Telegestión** | 1 | sistema | Control centralizado de energía |

---

## 6. ESTRUCTURA REQUERIDA PARA EL MODELO FINANCIERO

### 6.1 Estructura de la Hoja de Cálculo (Excel)

#### PESTAÑA 1: RESUMEN EJECUTIVO

| Celda | Contenido |
|-------|-----------|
| A1 | "PROYECTO APP CHÍA-GIRARDOT — MODELO FINANCIERO ITS" |
| A3 | "TOTAL CAPEX ESTIMADO" |
| B3 | `=SUM(UF1:UF15!H:H)+CCO!H:H` |
| A4 | "TOTAL OPEX ANUAL" |
| B4 | `=SUM(UF1:UF15!OPEX)+CCO!OPEX` |
| A6 | "TOTAL COMPONENTES DE CAMPO" |
| B6 | `1.458` |

#### PESTAÑAS 2-16: UF 1 a UF 15

Cada pestaña debe tener esta estructura:

| Columna | Encabezado | Descripción |
|---------|------------|-------------|
| A | **UF** | Nombre de la UF |
| B | **Tramo/Subtramo** | Identificación del tramo |
| C | **Sistema** | Categoría funcional (8 sistemas) |
| D | **CC** | Código del componente (CC-01 a CC-42) |
| E | **Componente** | Nombre descriptivo |
| F | **Cantidad** | Número de unidades |
| G | **Unidad** | km, unidad, par, sistema, cabeza |
| H | **Valor Unitario (COP)** | Precio de mercado |
| I | **Valor Total (COP)** | `=F*H` |
| J | **Doble Calzada** | Sí/No (si aplica, cantidad ya es ida+retorno) |
| K | **Justificación** | Por qué esta cantidad en este tramo |
| L | **Fuente Precio** | RFI, cotización, referencia de proyecto |

#### PESTAÑA 17: CCO (Centro de Control)

Misma estructura, pero con componentes del CCO.

#### PESTAÑA 18: COSTOS INDIRECTOS

| Concepto | % sobre | Fórmula |
|----------|---------|---------|
| Instalación y puesta en marcha | 15% | `=SUM(UF1:UF15!I:I)*0.15` |
| Ingeniería de detalle | 8% | `=SUM(UF1:UF15!I:I)*0.08` |
| Gastos generales | 8% | `=SUM(UF1:UF15!I:I)*0.08` |
| Utilidad contratista | 5% | `=SUM(UF1:UF15!I:I)*0.05` |
| Transporte e importación | 3% | `=SUM(UF1:UF15!I:I)*0.03` |
| Contingencia técnica | 15% | `=Subtotal*0.15` |

#### PESTAÑA 19: OPEX AÑOS 1-5

| Rubro | Año 1 | Año 2 | Año 3 | Año 4 | Año 5 |
|-------|-------|-------|-------|-------|-------|
| Energía eléctrica | | | | | |
| Mantenimiento preventivo | | | | | |
| Mantenimiento correctivo | | | | | |
| Conectividad | | | | | |
| Personal CCO | | | | | |
| Software y licencias | | | | | |
| Seguros | | | | | |

#### PESTAÑA 20: VALIDACIÓN

| Validación | Fórmula | Umbral | Estado |
|------------|---------|--------|--------|
| Densidad UF 1 | `=TotalCC/3.086` | 8-12 CC/km | ✅/❌ |
| Densidad UF 10 | `=TotalCC/0.300` | 2-3 CC/km | ✅/❌ |
| % Peaje sobre total | `=UF3/Total` | 15-25% | ✅/❌ |
| % Túneles sobre total | `=(UF4C+UF5)/Total` | 20-30% | ✅/❌ |
| Costo por km | `=Total/306` | $15-50M/km | ✅/❌ |

---

## 7. PRÓXIMOS PASOS

### 7.1 Para completar el modelo financiero

| Paso | Acción | Responsable | Entregable |
|------|--------|-------------|------------|
| 1 | **Validar cantidades** por UF con diseños de obra civil | Equipo técnico / ICCU | Lista validada por UF |
| 2 | **Obtener cotizaciones reales** de 3 proveedores por sistema | Compras / RFI | Cotizaciones en COP |
| 3 | **Definir ubicación exacta** de cada componente (km) | Ingeniería | Plan de despliegue |
| 4 | **Confirmar doble calzada** vs. calzada simple en colectoras | Diseño vial | Matriz de calzadas |
| 5 | **Ajustar valores unitarios** con cotizaciones reales | Financiero | Modelo actualizado |
| 6 | **Agregar CCO** con dimensionamiento real | Arquitectura | Diseño CCO |
| 7 | **Calcular OPEX** con tarifas reales de energía y personal | Financiero | OPEX anual |
| 8 | **Validar totales** contra % de CAPEX del proyecto | Director | Aprobación |

---

## 8. CONCLUSIÓN

Esta propuesta de estructura define **1.458 componentes de campo** distribuidos en **15 Unidades Funcionales** más el **Centro de Control**, organizados en **8 sistemas funcionales**:

1. **Detección y Vigilancia** — 431 unidades
2. **Control y Actuación** — 149 unidades
3. **Comunicaciones** — 312 unidades (km, switches, radios)
4. **Energía** — 252 unidades
5. **Peaje** — 12 unidades
6. **Control de Carga** — 2 unidades
7. **Seguridad en Túneles** — 44 unidades
8. **Gabinetes y Gateway** — 166 unidades

**La estructura de Excel propuesta** permite:
- Trazabilidad entre UF, CC y costo
- Validación automática de densidades
- Escalabilidad si cambian las cantidades
- Consolidación automática para CAPEX, OPEX y TCO

**¿Se procede a crear el Excel con esta estructura?** ⚡
