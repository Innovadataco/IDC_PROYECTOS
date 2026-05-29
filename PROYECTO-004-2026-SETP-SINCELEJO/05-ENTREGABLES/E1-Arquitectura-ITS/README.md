# PROYECTO-004-2026-SETP-SINCELEJO
## Documento 1: Arquitectura ITS Completa para SETP Sincelejo
### Sistema Estratégico de Transporte Público — Componente Tecnológico ITS

---

**Versión:** 1.0  
**Fecha:** Mayo 2026  
**Cliente:** METRO SABANAS S.A.S. / Sincelejo  
**Consultor:** INNOVADATACO  
**Clasificación:** CONFIDENCIAL — USO INTERNO  

---

## TABLA DE CONTENIDO

1. Resumen Ejecutivo
2. Introducción y Propósito
3. Marco Normativo y Legal
4. Clasificación de Servicios ITS para SETP Urbano
5. Arquitectura ITS de Referencia (4 Niveles)
6. Centro de Control de Operaciones (CCO)
7. Sistema de Infraestructura de Paraderos
8. Equipamiento a Bordo de Buses
9. Software y Aplicaciones del Sistema
10. Conectividad y Red de Telecomunicaciones
11. Ciberseguridad y Gobernanza de Datos
12. Requerimientos Funcionales (RF)
13. Requisitos No Funcionales (RNF)
14. Indicadores Clave de Rendimiento (KPI)
15. Plan de Implementación por Fases
16. Anexos Técnicos

---

## 1. RESUMEN EJECUTIVO

El presente documento establece la arquitectura técnica completa del componente de Sistemas Inteligentes de Transporte (ITS) para el Sistema Estratégico de Transporte Público (SETP) de Sincelejo, operado por METRO SABANAS S.A.S.

### Alcance del Documento
Este documento cubre exclusivamente el **componente tecnológico ITS** del SETP Sincelejo, incluyendo:
- Sistema de Rastreo y Control de Flota (SRC)
- Sistema de Gestión de Cobro y Tarificación (SGCF)
- Sistema de Información a Usuarios (SIU)
- Sistema de Seguridad y Telecomunicaciones (SST)

### Supuestos Base del Diseño

| Parámetro | Valor | Fuente |
|:---|:---|:---|
| Flota total buses | 34 unidades | MS-130-2025 (versión reducida) |
| Rutas operativas | 5 rutas | MS-130-2025 |
| Paraderos estimados | ~40 paraderos | Estimado sobre 5 rutas urbanas |
| Pasajeros/día estimados | 7.670 | MS-130-2025 |
| Ubicación CCO | Oficinas Metro Sabanas Sincelejo | Supuesto conservador |
| Medios de pago | Efectivo + tarjeta prepago NFC | Supuesto (no definido en docs) |
| Tarifa base estimada | $2.800 COP | Estimado mercado local |

**Nota crítica:** Los supuestos anteriores están basados en la documentación oficial más reciente (MS-130-2025). Se requiere validación por parte de METRO SABANAS para confirmar cantidades definitivas.

### Contexto del Proyecto

Sincelejo enfrenta una competencia desleal del mototaxismo (45.000 unidades vs 34 buses), un crecimiento del 44% en vehículos particulares desde 2020, y efectos del teletrabajo post-COVID. El componente tecnológico ITS es crítico para:

1. **Diferenciación competitiva:** Ofrecer información en tiempo real, pagos digitales, y seguridad pasajero
2. **Eficiencia operativa:** Optimizar despacho, tiempos de ciclo, y uso de flota
3. **Seguridad:** CCTV, botón de pánico, y monitoreo 24/7 del CCO
4. **Recaudo transparente:** Control de ingresos y prevención de fugas
5. **Cumplimiento normativo:** Decreto 482/2023 (política transporte público), Decreto 909/2023 (tarjeta única), Resolución 20203040034065

---

## 2. INTRODUCCIÓN Y PROPÓSITO

### 2.1 Contexto del SETP Sincelejo

El SETP Sincelejo es un sistema de transporte público urbano diseñado para reorganizar la movilidad de la ciudad, reemplazando el servicio informal actual con un sistema formalizado de buses con rutas fijas, paraderos, y operación planificada.

### 2.2 Propósito del Documento

Este documento tiene como objetivo:
- Definir la arquitectura tecnológica completa del componente ITS
- Especificar componentes, equipamiento, y software requeridos
- Establecer estándares de conectividad, seguridad, e interoperabilidad
- Servir como base para licitación, implementación, y operación

### 2.3 Alcance y Delimitación

| Incluido | Excluido |
|:---|:---|
| ITS para buses urbanos (34 unidades) | Flota adicional futura (hasta 75) |
| Paraderos y terminales (~40) | Expansión a rutas intermunicipales |
| CCO y su infraestructura | Modelo financiero del proyecto general |
| Software especializado ITS | Desarrollo de apps desde cero (se recomienda comprar) |
| Conectividad (celular, satelital, WiFi) | Infraestructura vial física (ciclovías, pavimento) |
| Ciberseguridad y gobernanza de datos | Regulación de tarifas (es competencia de la ANSV) |

---

## 3. MARCO NORMATIVO Y LEGAL

### 3.1 Normativa Nacional Colombia

| Norma | Descripción | Aplicación al SETP |
|:---|:---|:---|
| **Decreto 393/2010** | Estatuto de Transporte Nacional | Marco legal del transporte público |
| **Ley 1801/2016** | Código Nacional de Seguridad y Convivencia | Poder de policía sobre transporte |
| **Decreto 1079/2015** | Decreto Único Sector Transporte | Reglamentación del transporte público |
| **Decreto 482/2023** | Política Nacional de Transporte Público | Modernización e integración ITS |
| **Decreto 909/2023** | Sistema Nacional de Pago Electrónico | Tarjeta única interoperable |
| **Resolución 20203040034065** | Lineamientos técnicos SETP | Especificaciones mínimas del sistema |
| **Resolución 20223040028675** | PMITS Colombia | Plan Maestro ITS (adaptado a urbano) |
| **Resolución 20213040035125** | Interoperabilidad recaudo electrónico | Estándar IPTC |
| **Resolución 376/2024** | Recaudo electrónico obligatorio | Aplica a sistemas >50 vehículos |
| **Resolución 2163/2016** | Régimen taxis | Referencia para sistemas de rastreo |

### 3.2 Normativa Local Sincelejo

| Documento | Descripción |
|:---|:---|
| **Decreto Municipal 2023-XXX** | Regulación del transporte público en Sincelejo |
| **POT Sincelejo** | Plan de Ordenamiento Territorial — corredores de transporte |
| **Acuerdo Municipal SETP** | Creación del sistema y concesión a METRO SABANAS |

### 3.3 Estándares Técnicos Internacionales

| Estándar | Dominio | Propósito |
|:---|:---|:---|
| **ISO 14813 (ARC-IT)** | Arquitectura ITS | Estructura funcional e interfaces |
| **DATEX II v3.5** | Intercambio datos tráfico | Comunicación con SINITT nacional |
| **ISO/IEC 27001** | Gobernanza de información | Confidencialidad, integridad, disponibilidad |
| **NTCIP 1203/1204** | Señalización dinámica / CCTV | Protocolos de comunicación dispositivos |
| **IEEE 802.11p / C-V2X** | Comunicación vehicular | V2I para movilidad cooperativa |
| **IEC 62443** | Seguridad OT en campo | Blindaje hardware de vía |
| **EMV / ISO 14443** | Pagos sin contacto | Estándar tarjetas NFC |

---

## 4. CLASIFICACIÓN DE SERVICIOS ITS PARA SETP URBANO

Adaptación del catálogo PMITS Colombia al contexto urbano de Sincelejo:

### 4.1 Servicios de Operación (SO)

| Código | Servicio | Descripción | Funciones Clave |
|:---|:---|:---|:---|
| **SO-01** | Rastreo y Control de Flota (SRC) | Monitoreo GPS 24/7 de 34 buses | Localización, velocidad, desvío ruta, tiempo parada |
| **SO-02** | Gestión de Despacho | Control de salidas, frecuencias, y adherencia a horario | Planificación de turnos, control de headway |
| **SO-03** | Gestión de Incidentes Operativos | Atención de averías, accidentes, desvíos | Registro, escalamiento, coordinación |
| **SO-04** | Gestión de Paraderos | Monitoreo de ocupación y estado | Detección de aglomeraciones, vandalismo |

### 4.2 Servicios de Recaudo (SR)

| Código | Servicio | Descripción | Funciones Clave |
|:---|:---|:---|:---|
| **SR-01** | Validación de Pasajeros | Control de acceso con tarjeta NFC | Validación saldo, registro de viaje |
| **SR-02** | Recaudo Electrónico | Procesamiento de pagos sin contacto | Tarjeta única, recarga, reporte |
| **SR-03** | Control de Ingresos | Prevención de fugas de recaudo | Conciliación validaciones vs dinero depositado |
| **SR-04** | Tarificación Inteligente | Tarifa dinámica por zona/hora | Configuración de tarifas, exenciones |

### 4.3 Servicios de Información (SI)

| Código | Servicio | Descripción | Funciones Clave |
|:---|:---|:---|:---|
| **SI-01** | Información en Paraderos | Pantallas con tiempos de llegada | ETA por ruta, alertas de servicio |
| **SI-02** | App Móvil Pasajero | Aplicación ciudadana | Rutas, paraderos, tiempos, recarga |
| **SI-03** | Información Web | Portal SETP | Mapa de rutas, noticias, PQRS |
| **SI-04** | Señalización en Buses | Pantallas internas con próxima parada | Audio+visual, anuncios, alertas |

### 4.4 Servicios de Seguridad (SS)

| Código | Servicio | Descripción | Funciones Clave |
|:---|:---|:---|:---|
| **SS-01** | CCTV en Buses | Cámaras de seguridad interior/exterior | Grabación 24h, detección incidentes |
| **SS-02** | Botón de Pánico | Alarma silenciosa a CCO | Activación, geolocalización, respuesta |
| **SS-03** | CCTV en Paraderos | Vigilancia paraderos críticos | Grabación, detección vandalismo |
| **SS-04** | Control de Acceso | Acceso restringido a áreas críticas | CCO, terminales, depósito |

### 4.5 Servicios de Telecomunicaciones (ST)

| Código | Servicio | Descripción | Funciones Clave |
|:---|:---|:---|:---|
| **ST-01** | Conectividad Celular | Datos 4G/5G para buses y paraderos | VPN, redundancia, QoS |
| **ST-02** | Red WiFi Pasajero | Internet gratuito en buses | Portal cautivo, analytics |
| **ST-03** | Comunicación Operativa | Radio/voz CCO-conductores | Push-to-talk, grabación |
| **ST-04** | Satelital de Respaldo | Enlace emergencia | Activación automática ante falla |

---

## 5. ARQUITECTURA ITS DE REFERENCIA (4 NIVELES)

Basada en ARC-IT (ISO 14813), adaptada al SETP urbano:

### 5.1 Nivel 1: Arquitectura de Servicios (Enterprise View)

```
┌─────────────────────────────────────────────────────────────┐
│           ENTIDADES STAKEHOLDER SETP SINCELEJO              │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│   │ Pasajero │  │ Conductor│  │  CCO     │  │ Alcaldía │  │
│   │  (SIU)   │  │  (SRC)   │  │(Central) │  │(Regulador│  │
│   └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘  │
│        │             │             │             │          │
│        └─────────────┴─────────────┴─────────────┘          │
│                          │                                  │
│                    ┌─────┴─────┐                          │
│                    │  SETP     │                            │
│                    │ PLATFORM  │                            │
│                    │ (Integrador)│                          │
│                    └───────────┘                            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Relaciones de datos:**
- Pasajero ↔ SIU: Tiempos de llegada, recarga tarjeta, rutas
- Conductor ↔ SRC: Ruta del día, alertas, comunicación CCO
- CCO ↔ Todos: Monitoreo, control, emergencias, reportes
- Alcaldía ↔ Regulador: Indicadores de servicio, quejas, cumplimiento

### 5.2 Nivel 2: Arquitectura Lógica (Functional View)

**Subsistemas principales y sus funciones:**

```
┌────────────────────────────────────────────────────────────┐
│              SUBSISTEMAS FUNCIONALES SETP ITS                │
├────────────────────────────────────────────────────────────┤
│                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │    SRC       │  │    SGCF      │  │     SIU      │     │
│  │  (Rastreo)   │  │  (Recaudo)   │  │  (Información│     │
│  │              │  │              │  │   Usuarios)  │     │
│  │ • GPS        │  │ • Validación │  │ • Pantallas  │     │
│  │ • Velocidad  │  │ • Tarjeta   │  │   paradero   │     │
│  │ • Geocercas  │  │ • Recarga   │  │ • App móvil   │     │
│  │ • Despacho   │  │ • Conciliac.│  │ • Web         │     │
│  │ • Reportes   │  │ • Reportes  │  │ • Alertas     │     │
│  └──────┬───────┘  └──────┬──────┘  └──────┬──────┘     │
│         │                 │                │              │
│         └─────────────────┴────────────────┘              │
│                           │                               │
│                    ┌──────┴──────┐                        │
│                    │    SST      │                        │
│                    │ (Seguridad  │                        │
│                    │  Telecom)   │                        │
│                    │             │                        │
│                    │ • CCTV       │                        │
│                    │ • Botón pánico│                       │
│                    │ • Conectividad│                       │
│                    │ • Ciberseg.  │                        │
│                    └─────────────┘                        │
│                                                             │
└────────────────────────────────────────────────────────────┘
```

**Flujos de información principales:**
1. **SRC → SIU:** Posición bus → ETA en paradero
2. **SRC → SGCF:** Eventos bus → Conciliación recaudo
3. **SGCF → SIU:** Saldo tarjeta → Consulta app
4. **SST → Todos:** Alertas seguridad, CCTV, conectividad
5. **Todos → CCO:** Consolidación datos operación

### 5.3 Nivel 3: Arquitectura Física (Physical View)

**Equipamiento de campo:**

```
┌─────────────────────────────────────────────────────────────┐
│              COMPONENTES FÍSICOS DEL SISTEMA                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  BUSES (34 unidades)                                        │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐              │
│  │  OBU-01    │ │  OBU-02    │ │  OBU-03    │              │
│  │  GPS       │ │  Validador │ │  Pantalla  │              │
│  │  Tracker   │ │  NFC       │ │  interior  │              │
│  └────────────┘ └────────────┘ └────────────┘              │
│                                                             │
│  PARADEROS (~40)                                            │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐              │
│  │  PPD-01    │ │  PPD-02    │ │  PPD-03    │              │
│  │  Pantalla  │ │  Cámara    │ │  WiFi AP   │              │
│  │  LED ETA   │ │  CCTV      │ │  hotspot   │              │
│  └────────────┘ └────────────┘ └────────────┘              │
│                                                             │
│  CCO (1 centro)                                             │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐              │
│  │  Servidor  │ │  Firewall  │ │  UPS       │              │
│  │  Principal │ │  NGFW      │ │  10kVA     │              │
│  └────────────┘ └────────────┘ └────────────┘              │
│                                                             │
│  NUBE / CLOUD                                               │
│  ┌────────────┐ ┌────────────┐                             │
│  │  SaaS ITS  │ │  Backup    │                             │
│  │  Plataforma│ │  Storage   │                             │
│  └────────────┘ └────────────┘                             │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 5.4 Nivel 4: Arquitectura de Comunicaciones (Communications View)

**Red de comunicaciones del SETP:**

```
┌─────────────────────────────────────────────────────────────┐
│              RED DE COMUNICACIONES SETP                     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│                    ┌─────────────┐                         │
│                    │    CLOUD    │                         │
│                    │  Platform   │                         │
│                    │  (SaaS)     │                         │
│                    └──────┬──────┘                         │
│                           │                                 │
│              ┌────────────┼────────────┐                   │
│              │     VPN / TLS / API    │                   │
│              └────────────┼────────────┘                   │
│                           │                                 │
│                    ┌──────┴──────┐                         │
│                    │    CCO      │                         │
│                    │  Gateway    │                         │
│                    │  Principal  │                         │
│                    └──────┬──────┘                         │
│                           │                                 │
│        ┌──────────────────┼──────────────────┐            │
│        │         4G/5G Celular + VPN          │            │
│        └──────────────────┼──────────────────┘            │
│                           │                                 │
│     ┌─────────────────────┼─────────────────────┐        │
│     │                     │                     │          │
│ ┌───┴───┐           ┌────┴────┐          ┌────┴────┐    │
│ │ BUSES │           │PARADEROS│          │TERMINAL │    │
│ │  34   │           │   ~40   │          │    1    │    │
│ └───────┘           └─────────┘          └─────────┘    │
│                                                             │
│  Respaldo: Satelital (Starlink/Iridium) para CCO          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 6. CENTRO DE CONTROL DE OPERACIONES (CCO)

### 6.1 Ubicación y Infraestructura Física

| Aspecto | Especificación |
|:---|:---|
| **Ubicación** | Oficinas principales Metro Sabanas Sincelejo |
| **Área mínima** | 80 m² |
| **Altura libre** | ≥ 2.8 m |
| **Piso técnico** | Elevado (acceso cableado) |
| **Climatización** | Split inverter 36.000 BTU (redundante) |
| **Iluminación** | LED 500 lux en área operativa |
| **Acceso** | Control biométrico + tarjeta |
| **UPS** | 10 kVA / 2h autonomía |
| **Generador** | 15 kVA diesel (respaldo) |
| **Puesto operadores** | 4 estaciones de trabajo (24/7) |

### 6.2 Hardware del CCO

| Componente | Especificación | Cantidad |
|:---|:---|:---|
| **Servidor Principal ITS** | Dell PowerEdge R650 / HPE DL380 Gen10 — 2x Xeon Silver, 64GB RAM, 4TB SSD RAID 10 | 2 (HA) |
| **Servidor Base de Datos** | 2x Xeon Gold, 128GB RAM, 8TB SSD NVMe (PostgreSQL/PostGIS) | 2 (HA) |
| **Servidor Video (NVR)** | 64 canales, 2TB almacenamiento por canal (60 días retención) | 1 |
| **Firewall NGFW** | Palo Alto PA-440 / Fortinet FortiGate 200F | 1 |
| **Switch Core** | Cisco Catalyst 9300 / HP Aruba 6300 — 48 puertos GbE + 4x 10GbE | 2 (redundante) |
| **Switch Access** | 24 puertos GbE con PoE+ | 4 |
| **Router principal** | 4G/5G dual SIM + fibra óptica | 1 |
| **Videowall** | 2x2 LCD 55" (4 pantallas) | 1 |
| **Estaciones operador** | PC i7, 32GB RAM, 3 monitores 27" | 4 |
| **KVM** | 16 puertos IP (acceso remoto servidores) | 1 |
| **Rack 42U** | Con PDU, ventilación, y gestión de cables | 2 |

### 6.3 Software del CCO

| Sistema | Función | Tipo | Licenciamiento |
|:---|:---|:---|:---|
| **Plataforma ITS** | Integración SRC+SGCF+SIU | SaaS / On-prem | Suscripción anual |
| **SIG (GIS)** | Visualización mapa buses, rutas, paraderos | PostGIS + QGIS / ArcGIS | Perpetuo |
| **NVR Software** | Gestión video CCTV buses y paraderos | Milestone / Genetec | Por cámara |
| **Dashboard BI** | Indicadores operativos y reportes | Grafana / Power BI | Suscripción |
| **Help Desk** | Gestión incidentes y tickets | Jira Service Management | Suscripción |
| **Comunicaciones** | Radio IP, PTT, mensajería | Zello / Motorola WAVE | Por usuario |

### 6.4 Diseño de la Sala de Control

```
┌─────────────────────────────────────────────────────────────┐
│                    SALA DE CONTROL CCO                        │
│                      (Vista superior)                         │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                                                     │   │
│   │              [ VIDEOWALL 2x2 55" ]                  │   │
│   │                                                     │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                             │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐     │
│   │ Puesto 1│  │ Puesto 2│  │ Puesto 3│  │ Puesto 4│     │
│   │Operador │  │Operador │  │Operador │  │Supervisor│     │
│   │ Turno   │  │ Turno   │  │ Turno   │  │  CCO    │     │
│   │         │  │         │  │         │  │         │     │
│   │ 3x27"   │  │ 3x27"   │  │ 3x27"   │  │ 2x27"   │     │
│   └─────────┘  └─────────┘  └─────────┘  └─────────┘     │
│                                                             │
│                    ┌───────────┐                           │
│                    │   RACK    │                           │
│                    │ SERVIDORES│                           │
│                    │  + RED    │                           │
│                    └───────────┘                           │
│                                                             │
│   [BIOMÉTRICO] ──── [PUERTA] ──── [BIOMÉTRICO]            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 7. SISTEMA DE INFRAESTRUCTURA DE PARADEROS

### 7.1 Tipología de Paraderos

| Tipo | Descripción | Cantidad Estimada | Equipamiento |
|:---|:---|:---|:---|
| **Tipo I — Básico** | Paradero simple, alta demanda | ~20 | Pantalla LED ETA, iluminación LED, señal vertical |
| **Tipo II — Intermedio** | Paradero con cubierta, mediana demanda | ~15 | Pantalla LED, cámara CCTV, WiFi AP, bancas |
| **Tipo III — Terminal** | Terminal de intercambio, alta demanda | ~5 | Pantalla grande, CCTV, WiFi, oficina auxiliar, baños |

### 7.2 Ficha Técnica: Paradero Tipo I (Básico)

| Parámetro | Especificación |
|:---|:---|
| **Código** | PP-I-XXX |
| **Ubicación** | Andén de calzada, corredor principal |
| **Dimensiones** | 3m (ancho) × 1.5m (profundidad) × 2.5m (alto) |
| **Estructura** | Acero galvanizado + aluminio anodizado |
| **Pantalla LED ETA** | P10, 64×32 cm, 4G conectada, alimentación solar+batería |
| **Alimentación** | Panel solar 100W + batería LiFePO4 100Ah |
| **Iluminación** | LED 20W con sensor crepuscular |
| **Señalización** | Poste 3m con banderola SETP, códigos QR ruta |
| **Vandalismo** | Recubrimiento anti-graffiti, tornillería inviolable |
| **Costo estimado** | Por definir en estudio de mercado |

### 7.3 Ficha Técnica: Paradero Tipo II (Intermedio)

| Parámetro | Especificación |
|:---|:---|
| **Código** | PP-II-XXX |
| **Ubicación** | Zonas de alta demanda, centros comerciales, hospitales |
| **Dimensiones** | 6m × 2.5m × 2.8m (con cubierta) |
| **Estructura** | Acero galvanizado + vidrio templado + techo policarbonato |
| **Pantalla LED ETA** | P8, 96×48 cm, 4G, contenido dinámico |
| **Cámara CCTV** | IP 2MP, IR 30m, audio bidireccional, almacenamiento edge 7 días |
| **WiFi AP** | 802.11ac, 300 usuarios concurrentes, portal cautivo |
| **Bancas** | 2 bancas anti-vandalismo (4 puestos cada una) |
| **Alimentación** | Conexión eléctrica municipal + respaldo UPS 1kVA |
| **Costo estimado** | Por definir en estudio de mercado |

### 7.4 Ficha Técnica: Paradero Tipo III (Terminal)

| Parámetro | Especificación |
|:---|:---|
| **Código** | PP-III-XXX |
| **Ubicación** | Terminales de intercambio, centros de ciudad |
| **Dimensiones** | 15m × 8m × 3.5m (edificio) |
| **Estructura** | Mampostería + acero + vidrio (diseño arquitectónico) |
| **Pantalla LED** | P5 interior, 192×96 cm, contenido multimedia |
| **CCTV** | 4 cámaras IP 4MP, NVR local 30 días |
| **WiFi** | 4 APs 802.11ax, 1.000 usuarios |
| **Oficina auxiliar** | 10 m² con PC, impresora, comunicación CCO |
| **Baños** | 2 cabinas (PMR accesible) |
| **Aire acondicionado** | Split 24.000 BTU |
| **Alimentación** | Eléctrica municipal + generador 5kVA + UPS 3kVA |
| **Costo estimado** | Por definir en estudio de mercado |

---

## 8. EQUIPAMIENTO A BORDO DE BUSES

### 8.1 Especificación por Bus (34 unidades)

| Sistema | Componente | Especificación | Cantidad por Bus |
|:---|:---|:---|:---|
| **SRC** | GPS Tracker | Ubicación 5s, velocidad, ruta, geocercas | 1 |
| **SRC** | Tablet conductor | Android 10", 4G, app despacho | 1 |
| **SGCF** | Validador NFC | ISO 14443, EMV contactless, 200ms lectura | 2 (entrada+salida) |
| **SGCF** | Impresora tickets | Térmica 80mm, Bluetooth | 1 |
| **SIU** | Pantalla interior | LED 22", próxima parada, anuncios | 2 |
| **SIU** | Sistema audio | Amplificador 100W, 4 bocinas, TTS | 1 |
| **SS** | CCTV interior | IP 2MP, gran angular 120°, IR 10m, audio | 4 |
| **SS** | CCTV exterior | IP 2MP frontal + trasera, DVR embarcado 30 días | 2 |
| **SS** | Botón pánico | Silencioso, 3G/4G, geolocalización, CCO | 2 (conductor+pasajero) |
| **SS** | Caja fuerte | Acero 3mm, combinación electrónica, anclaje | 1 |
| **ST** | Router 4G/5G | Dual SIM, WiFi hotspot, VPN, QoS | 1 |
| **ST** | Red bus | Switch 8 puertos GbE PoE | 1 |
| **ST** | UPS bus** | 500VA, 30 min autonomía | 1 |

### 8.2 Diagrama de Instalación a Bordo

```
┌─────────────────────────────────────────────────────────────┐
│                    INTERIOR DEL BUS                          │
│                    (Vista lateral)                          │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   ┌──────────┐                                              │
│   │ Validador│  ← Entrada                                   │
│   │  NFC     │                                              │
│   └──────────┘                                              │
│                                                             │
│        ┌──────────┐                                        │
│        │ Pantalla │  ← Próxima parada                       │
│        │  22" LED │                                        │
│        └──────────┘                                        │
│                                                             │
│   ┌──────────┐  ┌──────────┐  ┌──────────┐                │
│   │ Cámara 1 │  │ Cámara 2 │  │ Cámara 3 │                │
│   │(Delante) │  │(Mitad)   │  │(Trasera) │                │
│   └──────────┘  └──────────┘  └──────────┘                │
│                                                             │
│                      ┌──────────┐                          │
│                      │ Botón    │  ← Pánico pasajero       │
│                      │  pánico  │                          │
│                      └──────────┘                          │
│                                                             │
│   ┌──────────┐                                              │
│   │ Validador│  ← Salida                                    │
│   │  NFC     │                                              │
│   └──────────┘                                              │
│                                                             │
│   ┌────────────────────────────────────────┐               │
│   │         CABINA CONDUCTOR               │               │
│   │  ┌────────┐ ┌────────┐ ┌────────┐      │               │
│   │  │ Tablet │ │ GPS    │ │ Botón  │      │               │
│   │  │ 10"    │ │ Tracker│ │ pánico│      │               │
│   │  └────────┘ └────────┘ └────────┘      │               │
│   │  ┌────────┐ ┌────────┐                 │               │
│   │  │ Router │ │ UPS    │                 │               │
│   │  │ 4G/5G  │ │ 500VA  │                 │               │
│   │  └────────┘ └────────┘                 │               │
│   │  ┌────────┐ ┌────────┐                 │               │
│   │  │ Cámara │ │ Caja   │                 │               │
│   │  │ frontal│ │ fuerte │                 │               │
│   │  └────────┘ └────────┘                 │               │
│   └────────────────────────────────────────┘               │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 8.3 Requerimientos Eléctricos del Bus

| Parámetro | Valor |
|:---|:---|
| **Consumo total estimado** | 350W |
| **Alimentación bus** | 24V DC (convertidor 24V→12V/5V) |
| **UPS embarcado** | 500VA / 30 min |
| **Protección** | Fusibles independientes por sistema |
| **Instalación** | Cableado protegido en conductos anti-vandalismo |

---

## 9. SOFTWARE Y APLICACIONES DEL SISTEMA

### 9.1 Arquitectura de Software

```
┌─────────────────────────────────────────────────────────────┐
│              ARQUITECTURA DE SOFTWARE SETP ITS              │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌───────────────────────────────────────────────────────┐  │
│  │           CAPA DE PRESENTACIÓN                        │  │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌──────────┐  │  │
│  │  │ App     │ │ Web     │ │ CCO     │ │ Pantallas│  │  │
│  │  │ móvil   │ │ portal  │ │ dashboard│ │ paradero│  │  │
│  │  │(pasajero)│ │(público)│ │(operador)│ │(LED)    │  │  │
│  │  └─────────┘ └─────────┘ └─────────┘ └──────────┘  │  │
│  └───────────────────────────────────────────────────────┘  │
│                           │                                  │
│  ┌───────────────────────────────────────────────────────┐  │
│  │           CAPA DE APLICACIÓN / LÓGICA                 │  │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌──────────┐  │  │
│  │  │ SRC     │ │ SGCF    │ │ SIU     │ │ SST     │  │  │
│  │  │ engine  │ │ engine  │ │ engine  │ │ engine  │  │  │
│  │  │         │ │         │ │         │ │         │  │  │
│  │  │• GPS    │ │• Validac│ │• ETA    │ │• CCTV   │  │  │
│  │  │• Ruta   │ │• Recarga│ │• Rutas  │ │• Alertas│  │  │
│  │  │• Veloc. │ │• Concil.│ │• Notif. │ │• Report.│  │  │
│  │  └─────────┘ └─────────┘ └─────────┘ └──────────┘  │  │
│  └───────────────────────────────────────────────────────┘  │
│                           │                                  │
│  ┌───────────────────────────────────────────────────────┐  │
│  │           CAPA DE DATOS / INFRAESTRUCTURA             │  │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌──────────┐  │  │
│  │  │ DB      │ │ Cache   │ │ Message │ │ Storage │  │  │
│  │  │PostgreSQL│ │ Redis   │ │ Queue   │ │ S3/MinIO│  │  │
│  │  │+ PostGIS │ │         │ │RabbitMQ │ │         │  │  │
│  │  └─────────┘ └─────────┘ └─────────┘ └──────────┘  │  │
│  └───────────────────────────────────────────────────────┘  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 9.2 Sistema de Rastreo y Control de Flota (SRC)

| Módulo | Función | Tecnología |
|:---|:---|:---|
| **Rastreo GPS** | Ubicación en tiempo real de 34 buses | GPS + GLONASS + Galileo, 5s intervalo |
| **Geocercas** | Alerta desvío de ruta | Polígonos configurables por ruta |
| **Velocidad** | Alerta exceso de velocidad | Umbral configurable por tramo |
| **Tiempo parada** | Control permanencia en paradero | Detección automática, alerta >5min |
| **Despacho** | Control salidas de terminal | Planificación vs realidad, alerta retraso |
| **Reportes** | Kilometraje, consumo, eventos | Automáticos diarios/semanales/mensuales |

### 9.3 Sistema de Gestión de Cobro y Tarificación (SGCF)

| Módulo | Función | Tecnología |
|:---|:---|:---|
| **Validación** | Lectura tarjeta NFC, descuento saldo | ISO 14443-A/B, MIFARE DESFire, EMV |
| **Tarificación** | Cálculo tarifa por zona/hora/regla | Motor de reglas configurable |
| **Recarga** | Puntos de recarga virtual y físicos | App, web, corresponsales bancarios |
| **Conciliación** | Validaciones vs depósitos conductor | Reporte diario automático, alertas discrepancia |
| **Reportes** | Ingresos, tendencias, peak hours | Dashboard BI, exporte Excel/PDF |
| **Integración** | Con sistema nacional de pago | API Ministerio Transporte (SITP nacional) |

**Nota importante:** El Decreto 909/2023 establece la tarjeta única nacional de transporte. El SGCF debe ser compatible con este estándar para interoperabilidad futura.

### 9.4 Sistema de Información a Usuarios (SIU)

| Módulo | Función | Tecnología |
|:---|:---|:---|
| **Pantallas paradero** | ETA por ruta, alertas de servicio | LED P8/P10, 4G, gestión remota |
| **App móvil** | Rutas, paraderos, tiempos, recarga | iOS + Android, React Native / Flutter |
| **Web** | Portal público SETP | Next.js / WordPress, mapa interactivo |
| **Audio bus** | Anuncio próxima parada | TTS (texto-a-voz), 2 idiomas (es+wayuu) |
| **Pantalla bus** | Próxima parada, anuncios | LED 22", contenido desde CCO |
| **Notificaciones push** | Alertas servicio, recarga exitosa | Firebase / OneSignal |

**Nota cultural:** Sincelejo tiene presencia Wayuu importante. Se recomienda audio bilingüe español-wayuu en buses y paraderos de zonas con alta población indígena.

### 9.5 Sistema de Seguridad y Telecomunicaciones (SST)

| Módulo | Función | Tecnología |
|:---|:---|:---|
| **CCTV buses** | Grabación 24h, acceso remoto CCO | IP 2MP, H.265, NVR edge 30 días |
| **CCTV paraderos** | Vigilancia paraderos Tipo II-III | IP 2-4MP, NVR local/cloud |
| **Botón pánico** | Alerta silenciosa a CCO | 4G, GPS, audio bidireccional oculto |
| **Acceso CCO** | Control entrada salas críticas | Biometría + tarjeta + registro |
| **Firewall** | Protección perímetro red | NGFW con IPS, sandboxing |
| **VPN** | Comunicación segura bus-CCO-cloud | WireGuard / OpenVPN |
| **SIEM** | Análisis seguridad centralizado | Wazuh / Splunk / Elastic |
| **Backup** | Respaldo automático datos críticos | 3-2-1: local + nube + offline |

---

## 10. CONECTIVIDAD Y RED DE TELECOMUNICACIONES

### 10.1 Arquitectura de Red

```
┌─────────────────────────────────────────────────────────────┐
│           ARQUITECTURA DE RED SETP SINCELEJO                │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   ┌─────────────────────────────────────────────────────┐   │
│   │                  NUBE / CLOUD                        │   │
│   │  ┌─────────┐ ┌─────────┐ ┌─────────┐              │   │
│   │  │SaaS ITS │ │ Storage │ │ Backup  │              │   │
│   │  │Platform │ │  S3     │ │ Diario  │              │   │
│   │  └─────────┘ └─────────┘ └─────────┘              │   │
│   └────────────────────┬────────────────────────────────┘   │
│                        │ VPN / TLS / API REST              │
│   ┌────────────────────┴────────────────────────────────┐   │
│   │                    CCO SINCELEJO                     │   │
│   │  ┌─────────┐ ┌─────────┐ ┌─────────┐              │   │
│   │  │ Firewall│ │ Router  │ │Switch   │              │   │
│   │  │  NGFW   │ │ Principal│ │ Core    │              │   │
│   │  └─────────┘ └─────────┘ └─────────┘              │   │
│   │        │              │                            │   │
│   │   ┌────┴────┐    ┌────┴────┐                      │   │
│   │   │ Fibra   │    │ 4G/5G   │                      │   │
│   │   │ Primaria│    │ Movistar│                      │   │
│   │   │ ETB     │    │ Claro   │                      │   │
│   │   └────┬────┘    └────┬────┘                      │   │
│   └────────┼──────────────┼───────────────────────────┘   │
│            │              │                                  │
│   ┌────────┴──────────────┴────────┐                      │
│   │         RED CELULAR 4G/5G       │                      │
│   │     (Movistar + Claro dual SIM) │                      │
│   └────────┬──────────────────┬──────┘                      │
│            │                  │                             │
│    ┌───────┴───────┐   ┌─────┴──────┐                     │
│    │   BUSES       │   │ PARADEROS  │                     │
│    │   (34)        │   │   (~40)    │                     │
│    │               │   │            │                     │
│    │ Router 4G/5G  │   │ 4G modem   │                     │
│    │ + WiFi AP     │   │ + Pantalla │                     │
│    │ + VPN client  │   │ + Cámara   │                     │
│    └───────────────┘   └────────────┘                     │
│                                                             │
│   RESPALDO SATELITAL (CCO)                                │
│   ┌─────────┐                                              │
│   │ Starlink│  ← Activación automática ante falla          │
│   │ / BGAN  │     de fibra + celular                       │
│   └─────────┘                                              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 10.2 Especificaciones de Conectividad

| Enlace | Tecnología | Velocidad | Redundancia |
|:---|:---|:---|:---|
| **CCO → Internet** | Fibra óptica ETB + 4G/5G dual SIM | 100 Mbps simétrico | Sí (failover automático) |
| **Bus → CCO** | 4G/5G dual SIM (Movistar + Claro) | 20 Mbps down / 5 Mbps up | Sí (dual SIM) |
| **Paradero → CCO** | 4G/5G modem dedicado | 10 Mbps | No (monomando, aceptable) |
| **CCO → Nube** | VPN TLS 1.3 sobre Internet | 100 Mbps | Sí (vía fibra + celular) |
| **Respaldo CCO** | Starlink / BGAN satelital | 50 Mbps | Automático <60s |

### 10.3 Requerimientos de Ancho de Banda

| Flujo | Ancho de banda estimado | Prioridad |
|:---|:---|:---|
| **Video CCTV (34 buses)** | 34 × 2 Mbps = 68 Mbps | Alta |
| **Video CCTV paraderos** | 25 × 1 Mbps = 25 Mbps | Media |
| **Datos SRC (GPS)** | 34 × 5 kbps = 170 kbps | Alta |
| **Datos SGCF** | 34 × 10 kbps = 340 kbps | Crítica |
| **Audio/video botón pánico** | Eventual, 1 Mbps | Crítica |
| **Pantallas paradero** | 40 × 100 kbps = 4 Mbps | Baja |
| **WiFi pasajero** | Variable, hasta 20 Mbps | Baja |
| **Total pico estimado** | ~120 Mbps | — |

---

## 11. CIBERSEGURIDAD Y GOBERNANZA DE DATOS

### 11.1 Principios de Seguridad (Zero Trust)

| Principio | Implementación |
|:---|:---|
| **Nunca confiar, siempre verificar** | Autenticación multifactor en todos los accesos |
| **Privilegio mínimo** | Roles diferenciados: operador, supervisor, admin, auditor |
| **Segmentación de red** | VLANs separadas: operación, video, invitados, gestión |
| **Cifrado end-to-end** | TLS 1.3 para datos, VPN para conectividad bus-CCO |
| **Monitoreo continuo** | SIEM + IDS/IPS en perímetro y segmentos críticos |

### 11.2 Medidas de Seguridad por Capa

| Capa | Medida | Implementación |
|:---|:---|:---|
| **Perímetro** | Firewall NGFW | Palo Alto / Fortinet — IPS, sandboxing, GeoIP |
| **Red** | Segmentación VLAN | 4 VLANs: ITS-Op (100), CCTV-Video (200), WiFi-Public (300), Mgmt (400) |
| **Aplicación** | WAF + API Gateway | Protección inyección, rate limiting, autenticación JWT |
| **Datos** | Cifrado + Tokenización | AES-256 en reposo, TLS 1.3 en tránsito, tokenización tarjetas |
| **Endpoint** | EDR + Hardening | CrowdStrike / SentinelOne, configuración CIS Benchmark |
| **Físico** | Control acceso | Biometría CCO, gabinetes bloqueados, CCTV 24/7 |

### 11.3 Gobernanza de Datos

| Aspecto | Política |
|:---|:---|
| **Retención CCTV** | 60 días operativos, 2 años incidentes |
| **Retención datos recaudo** | 10 años (obligación fiscal) |
| **Retención GPS** | 2 años |
| **Acceso datos personales** | Solo autorizado, registro de auditoría |
| **Borrado** | Anonimización post retención, destrucción segura |
| **Cumplimiento** | Ley 1581/2012 (datos personales), Decreto 1377/2013 |
| **Auditoría** | Trimestral, reporte a alta dirección |

### 11.4 Plan de Respuesta a Incidentes

| Fase | Acción | Tiempo objetivo |
|:---|:---|:---|
| **Detección** | SIEM alerta, operador CCO valida | < 5 min |
| **Contención** | Aislar sistema afectado, preservar evidencia | < 30 min |
| **Erradicación** | Eliminar amenaza, aplicar parches | < 4 horas |
| **Recuperación** | Restaurar servicios, monitoreo intensivo | < 8 horas |
| **Lecciones** | Post-mortem, actualización procedimientos | < 72 horas |
| **Comunicación** | Informar afectados si datos personales | < 72 horas (Ley 1581) |

---

## 12. REQUERIMIENTOS FUNCIONALES (RF)

### RF-SRC-001 a RF-SRC-020 — Sistema de Rastreo y Control de Flota

| Código | Requerimiento | Prioridad |
|:---|:---|:---|
| **RF-SRC-001** | El sistema debe rastrear la ubicación GPS de cada bus con precisión ≤ 5m, actualización cada 5 segundos | Crítica |
| **RF-SRC-002** | El sistema debe detectar desvíos de ruta con alerta automática al CCO en < 10 segundos | Crítica |
| **RF-SRC-003** | El sistema debe registrar velocidad instantánea y promedio por tramo | Alta |
| **RF-SRC-004** | El sistema debe generar alerta de exceso de velocidad configurable por tramo | Alta |
| **RF-SRC-005** | El sistema debe controlar tiempos de permanencia en paraderos, alerta > 5 min | Media |
| **RF-SRC-006** | El sistema debe permitir planificación de despacho con comparación plan vs real | Alta |
| **RF-SRC-007** | El sistema debe generar reportes automáticos: kilometraje, consumo, eventos | Media |
| **RF-SRC-008** | El sistema debe permitir comunicación bidireccional CCO-conductor (mensaje + voz) | Alta |
| **RF-SRC-009** | El sistema debe registrar eventos del conductor: login/logout, inicio/fin ruta | Media |
| **RF-SRC-010** | El sistema debe soportar geocercas configurables por ruta y sentido | Media |

### RF-SGCF-001 a RF-SGCF-015 — Sistema de Gestión de Cobro

| Código | Requerimiento | Prioridad |
|:---|:---|:---|
| **RF-SGCF-001** | El validador debe leer tarjeta NFC en ≤ 200ms | Crítica |
| **RF-SGCF-002** | El sistema debe descontar saldo correctamente y registrar transacción | Crítica |
| **RF-SGCF-003** | El sistema debe permitir múltiples tarifas: base, diferencial, exenciones | Alta |
| **RF-SGCF-004** | El sistema debe generar reporte de conciliación diario conductor-sistema | Crítica |
| **RF-SGCF-005** | El sistema debe permitir recarga virtual (app/web) y física (corresponsal) | Alta |
| **RF-SGCF-006** | El sistema debe soportar tarjeta única nacional (Decreto 909/2023) | Crítica |
| **RF-SGCF-007** | El sistema debe operar offline por ≥ 2 horas con sincronización posterior | Crítica |

### RF-SIU-001 a RF-SIU-015 — Sistema de Información a Usuarios

| Código | Requerimiento | Prioridad |
|:---|:---|:---|
| **RF-SIU-001** | Las pantallas de paradero deben mostrar ETA por ruta con precisión ≤ 2 min | Crítica |
| **RF-SIU-002** | La app móvil debe mostrar mapa con rutas, paraderos, y buses en tiempo real | Alta |
| **RF-SIU-003** | La app debe permitir consulta de saldo y recarga de tarjeta | Alta |
| **RF-SIU-004** | El sistema de audio debe anunciar próxima parada en español y wayuu | Media |
| **RF-SIU-005** | El portal web debe mostrar información de servicio, noticias, y PQRS | Media |

### RF-SS-001 a RF-SS-015 — Sistema de Seguridad

| Código | Requerimiento | Prioridad |
|:---|:---|:---|
| **RF-SS-001** | CCTV interior del bus debe grabar 24/7 con calidad ≥ 720p | Crítica |
| **RF-SS-002** | Botón de pánico debe alertar CCO en < 5 segundos con ubicación precisa | Crítica |
| **RF-SS-003** | CCTV paraderos debe detectar vandalismo con alerta automática | Media |
| **RF-SS-004** | Acceso a CCO debe requerir autenticación biométrica + tarjeta | Alta |

---

## 13. REQUISITOS NO FUNCIONALES (RNF)

| Código | Requisito | Valor | Métrica |
|:---|:---|:---|:---|
| **RNF-01** | Disponibilidad sistema ITS | ≥ 99.5% | Uptime anual |
| **RNF-02** | Disponibilidad CCO | ≥ 99.9% | Uptime anual |
| **RNF-03** | Tiempo recuperación CCO (RTO) | ≤ 4 horas | Después desastre |
| **RNF-04** | Pérdida datos aceptable (RPO) | ≤ 15 minutos | Punto recuperación |
| **RNF-05** | Latencia GPS bus → CCO | ≤ 10 segundos | 95 percentil |
| **RNF-06** | Latencia alerta botón pánico | ≤ 5 segundos | 99 percentil |
| **RNF-07** | Precisión GPS | ≤ 5 metros | 95 percentil |
| **RNF-08** | Capacidad concurrente app | ≥ 10.000 usuarios | Simultáneos |
| **RNF-09** | Escalabilidad buses | ≥ 100 unidades | Sin rediseño arquitectura |
| **RNF-10** | Vida útil equipamiento de campo | ≥ 7 años | En condiciones normales |
| **RNF-11** | Temperatura operación equipamiento | -10°C a +60°C | Ambiente tropical Sincelejo |
| **RNF-12** | Humedad operación | ≤ 95% HR | Sin condensación |
| **RNF-13** | Protección polvo/agua equipamiento exterior | IP65 mínimo | NEMA 4X |
| **RNF-14** | Cumplimiento ciberseguridad | ISO 27001 + IEC 62443 | Certificación |
| **RNF-15** | Cumplimiento datos personales | Ley 1581/2012 | Auditoría anual |

---

## 14. INDICADORES CLAVE DE RENDIMIENTO (KPI)

| Código | Indicador | Fórmula | Meta | Frecuencia |
|:---|:---|:---|:---|:---|
| **KPI-01** | Disponibilidad flota | Buses operativos / Total × 100 | ≥ 90% | Diario |
| **KPI-02** | Adherencia a ruta | Kilómetros en ruta / Total × 100 | ≥ 95% | Diario |
| **KPI-03** | Cumplimiento frecuencia | Salidas puntuales / Total × 100 | ≥ 85% | Diario |
| **KPI-04** | Velocidad promedio comercial | Distancia / Tiempo ciclo | ≥ 18 km/h | Semanal |
| **KPI-05** | Pasajeros por kilómetro | Validaciones / Kilómetros recorridos | ≥ 8 pax/km | Mensual |
| **KPI-06** | Recaudo por bus | Ingresos / Número buses / Días | ≥ Meta operación | Diario |
| **KPI-07** | Fugas de recaudo detectadas | (Validaciones × tarifa - Depósitos) / Ingresos | ≤ 3% | Mensual |
| **KPI-08** | Tiempo de respuesta botón pánico | Tiempo alerta CCO - Activación | ≤ 30 seg | Por evento |
| **KPI-09** | Satisfacción pasajero | Encuesta 1-5 estrellas | ≥ 4.0 | Trimestral |
| **KPI-10** | Disponibilidad sistema ITS | Uptime plataforma | ≥ 99.5% | Mensual |
| **KPI-11** | Reducción tiempos de espera | (Antes - Después) / Antes × 100 | ≥ 20% | Semestral |
| **KPI-12** | Penetración app pasajero | Usuarios activos / Población objetivo | ≥ 30% | Trimestral |
| **KPI-13** | Incidentes de seguridad | Número eventos / 100.000 km | ≤ 2 | Mensual |
| **KPI-14** | Eficiencia energética | kWh / km recorrido | Reducir 10% | Anual |
| **KPI-15** | Cumplimiento normativo | Requisitos cumplidos / Total × 100 | 100% | Trimestral |

---

## 15. PLAN DE IMPLEMENTACIÓN POR FASES

### Fase 1: Infraestructura Base (Meses 1-2)

| Actividad | Duración | Entregable |
|:---|:---|:---|
| Adecuación física CCO | 3 semanas | CCO operativo con climatización, acceso, UPS |
| Instalación hardware CCO | 2 semanas | Servidores, red, firewall, videowall |
| Contratación conectividad | 2 semanas | Fibra + 4G/5G operativo |
| Configuración plataforma SaaS | 2 semanas | Plataforma ITS configurada |

### Fase 2: Equipamiento de Campo (Meses 2-4)

| Actividad | Duración | Entregable |
|:---|:---|:---|
| Instalación equipamiento buses (lote 1: 17) | 4 semanas | 17 buses equipados y probados |
| Instalación equipamiento buses (lote 2: 17) | 4 semanas | 34 buses equipados y probados |
| Instalación paraderos Tipo I (20) | 6 semanas | 20 paraderos básicos operativos |
| Instalación paraderos Tipo II (15) | 6 semanas | 15 paraderos intermedios operativos |
| Instalación paraderos Tipo III (5) | 4 semanas | 5 terminales operativas |

### Fase 3: Integración y Pruebas (Meses 4-5)

| Actividad | Duración | Entregable |
|:---|:---|:---|
| Integración SRC-SGCF-SIU | 3 semanas | Flujos end-to-end operativos |
| Pruebas de sistema | 3 semanas | Protocolo pruebas aprobado |
| Pruebas de carga y estrés | 2 semanas | Validación 10.000 usuarios concurrentes |
| Pruebas de seguridad | 2 semanas | Pentest aprobado |
| Capacitación operadores CCO | 2 semanas | 8 operadores certificados |
| Capacitación conductores | 2 semanas | 34 conductores certificados |

### Fase 4: Puesta en Marcha y Operación (Meses 5-6)

| Actividad | Duración | Entregable |
|:---|:---|:---|
| Pilotaje operativo (ruta 1) | 2 semanas | Ruta Cecar-Pioneros operando con ITS |
| Expansión a 5 rutas | 4 semanas | Sistema completo operativo |
| Ajustes y optimización | 2 semanas | Sistema estabilizado |
| Entrega final | 1 semana | Documentación, llaves, capacitación final |

### Cronograma Resumido

```
Mes:    1    2    3    4    5    6    7    8    9   10   11   12
        ├────┤    ├────────────┤    ├────────────┤    ├────┤
        │F1: Infraestructura  │    │              │    │    │
        │         CCO          │    │              │    │    │
        ├──────────────────────┤    │              │    │    │
        │    F2: Equipamiento de campo              │    │    │
        │    Buses + Paraderos                      │    │    │
        ├───────────────────────────────────────────┤    │    │
        │              F3: Integración y Pruebas         │    │
        ├──────────────────────────────────────────────────┤    │
        │                        F4: Marcha y Operación         │
        └────────────────────────────────────────────────────────┘
```

---

## 16. ANEXOS TÉCNICOS

### Anexo A: Matriz de Componentes por Sistema

| Sistema | Componente | Cantidad | Ubicación | Prioridad |
|:---|:---|:---|:---|:---|
| SRC | GPS Tracker | 34 | Bus | Crítica |
| SRC | Tablet conductor | 34 | Bus | Alta |
| SGCF | Validador NFC | 68 | Bus (2 por bus) | Crítica |
| SGCF | Impresora ticket | 34 | Bus | Media |
| SIU | Pantalla LED paradero Tipo I | 20 | Paradero | Alta |
| SIU | Pantalla LED paradero Tipo II | 15 | Paradero | Alta |
| SIU | Pantalla LED paradero Tipo III | 5 | Terminal | Alta |
| SIU | Pantalla bus interior | 68 | Bus (2 por bus) | Media |
| SS | CCTV interior bus | 136 | Bus (4 por bus) | Crítica |
| SS | CCTV exterior bus | 68 | Bus (2 por bus) | Alta |
| SS | CCTV paradero Tipo II | 15 | Paradero | Media |
| SS | CCTV paradero Tipo III | 20 | Terminal (4 c/u) | Media |
| SS | Botón pánico | 68 | Bus (2 por bus) | Crítica |
| ST | Router 4G/5G bus | 34 | Bus | Crítica |
| ST | WiFi AP bus | 34 | Bus | Media |
| ST | UPS bus | 34 | Bus | Alta |
| ST | Switch PoE bus | 34 | Bus | Media |

### Anexo B: Inventario Total de Equipamiento

| Categoría | Total unidades |
|:---|:---|
| **Dispositivos en buses** | 782 |
| **Dispositivos en paraderos** | 80 |
| **Equipamiento CCO** | 25 |
| **TOTAL EQUIPAMIENTO DE CAMPO** | **887** |

### Anexo C: Estándares y Certificaciones Requeridas

| Equipamiento | Certificación mínima |
|:---|:---|
| GPS Tracker | FCC, CE, IP65 |
| Validador NFC | EMVCo, PCI PTS, CE |
| Pantallas LED | CE, FCC, IP65 |
| Cámaras CCTV | ONVIF Profile S, CE, IP67 |
| Router 4G/5G | FCC, CE, PTCRB |
| Botón pánico | CE, FCC, IP67, anti-vandalismo IK10 |
| UPS | CE, UL, autonomía certificada |

### Anexo D: Recomendaciones de Proveedores (Referenciales)

| Categoría | Proveedores sugeridos | País |
|:---|:---|:---|
| Plataforma ITS SaaS | Vixtera, Kibus, Moovit | Colombia / Internacional |
| GPS Tracking | Queclink, CalAmp, Geotab | China / USA |
| Validadores NFC | Conduent, Scheidt & Bachmann, Kapsch | USA / Austria |
| Pantallas LED paradero | Daktronics, Yaham, Absen | USA / China |
| CCTV | Hikvision, Axis, Hanwha | China / Suecia |
| Redes 4G/5G | Cisco, Cradlepoint, Sierra Wireless | USA |
| NVR/Video | Milestone, Genetec | Dinamarca / Canadá |
| Ciberseguridad | Palo Alto, Fortinet, CrowdStrike | USA |

**Nota:** Las recomendaciones son referenciales. El estudio de mercado de INNOVADATACO identificará proveedores óptimos según disponibilidad local, soporte, y precio.

---

## CONCLUSIONES

El componente tecnológico ITS del SETP Sincelejo representa una inversión crítica para la viabilidad del sistema. Con 34 buses, ~40 paraderos, y un CCO central, la arquitectura propuesta cubre:

1. **Rastreo y control total** de la flota en tiempo real
2. **Recaudo transparente** con tarjeta NFC interoperable
3. **Información al pasajero** vía app, web, y pantallas en paraderos
4. **Seguridad integral** con CCTV y botón de pánico
5. **Conectividad robusta** con redundancia celular y satelital
6. **Ciberseguridad Zero Trust** protegiendo datos de recaudo y operación

La implementación estimada es de **6 meses** desde aprobación hasta operación plena, con inversión por definir tras estudio de mercado detallado.

**Próximos pasos recomendados:**
1. Validación de supuestos con METRO SABANAS
2. Estudio de mercado de equipamiento (INNOVADATACO)
3. Selección de plataforma ITS SaaS
4. Diseño detallado de red y CCO
5. Licitación de equipamiento e instalación

---

*Documento generado por INNOVADATACO — ZEUS Enterprise System*  
*Mayo 2026 — CONFIDENCIAL*

---

# 5. ARQUITECTURA ITS POR NIVELES

## 5.1 Visión Integrada de la Arquitectura

La arquitectura ITS del SETP Sincelejo se describe en cuatro niveles de abstracción que van desde la estrategia de negocio hasta los componentes físicos de campo.

```
┌─────────────────────────────────────────────────────────────────────┐
│ NIVEL 1: SERVICIOS ESTRATÉGICOS ITS                                 │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐                   │
│  │   SRC   │ │  SGCF   │ │   SIU   │ │   SST   │                   │
│  │ Recaudo │ │  Flota  │ │ Usuario │ │ Segur.  │                   │
│  └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘                   │
├───────┼───────────┼───────────┼───────────┼─────────────────────────┤
│ NIVEL 2: VISTA LÓGICA                                               │
│  Software • Plataformas • APIs • Bases de datos • Microservicios    │
├───────┼───────────┼───────────┼───────────┼─────────────────────────┤
│ NIVEL 3: VISTA FÍSICA                                               │
│  Buses • Paraderos • CCO • Servidores • Dispositivos IoT            │
├───────┼───────────┼───────────┼───────────┼─────────────────────────┤
│ NIVEL 4: VISTA DE COMUNICACIONES                                    │
│  4G/5G • Radio • WiFi • VPN • Protocolos • Internet dedicado        │
└─────────────────────────────────────────────────────────────────────┘
```

## 5.2 Nivel 1: Servicios Estratégicos ITS

### 5.2.1 Relación entre Servicios Estratégicos

```
                    ┌──────────────────┐
                    │   USUARIO FINAL   │
                    │  (Ciudadano)      │
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
        ┌─────▼─────┐  ┌────▼────┐  ┌──────▼──────┐
        │    SIU     │  │   SRC   │  │    SGCF     │
        │ Información │  │ Recaudo │  │ Control     │
        │ al Usuario  │  │ y Pago  │  │ de Flota    │
        └─────┬──────┘  └────┬────┘  └──────┬──────┘
              │              │              │
              └──────────────┼──────────────┘
                             │
                    ┌────────▼────────┐
                    │       SST        │
                    │ Seguridad de      │
                    │ Transacciones     │
                    └─────────────────┘
                             │
                    ┌────────▼────────┐
                    │  AUTORIDADES    │
                    │ MinTransporte   │
                    │ SuperTransporte │
                    │ ANSV            │
                    └─────────────────┘
```

## 5.3 Nivel 2: Vista Lógica

### 5.3.1 Arquitectura de Software

```
┌─────────────────────────────────────────────────────────────────────┐
│ CAPA DE PRESENTACIÓN / CANALES                                      │
│  App Móvil (iOS/Android) • Web Responsive • Pantallas Paraderos     │
│  Call Center • WhatsApp Bot • Dashboard CCO                         │
├─────────────────────────────────────────────────────────────────────┤
│ CAPA DE API GATEWAY                                                 │
│  API REST (JSON/HTTPS) • API GraphQL • WebSocket (tiempo real)    │
│  MQTT (IoT buses) • Rate Limiting • Authentication (OAuth2)       │
├─────────────────────────────────────────────────────────────────────┤
│ CAPA DE MICROSERVICIOS                                              │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐     │
│  │  Tarifas│ │ Clearing│ │  GPS    │ │  Video  │ │  Alertas│     │
│  │  Engine │ │  Engine │ │ Service │ │ Service │ │  Engine │     │
│  └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘     │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐                  │
│  │  Conteo │ │  User   │ │  Auth   │ │  Report │                  │
│  │ Pasaj.  │ │  Mgmt   │ │  Service│ │  Engine │                  │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘                  │
├─────────────────────────────────────────────────────────────────────┤
│ CAPA DE DATOS                                                       │
│  PostgreSQL (transaccional) • Redis (cache) • TimescaleDB (series)  │
│  MinIO/S3 (objetos) • ClickHouse (analytics) • Elasticsearch (logs) │
├─────────────────────────────────────────────────────────────────────┤
│ CAPA DE INFRAESTRUCTURA / ORQUESTACIÓN                              │
│  Kubernetes / Docker Swarm • CI/CD • Monitoring (Prometheus/Grafana)│
│  Log Aggregation (ELK/Loki) • Backup • Disaster Recovery           │
└─────────────────────────────────────────────────────────────────────┘
```

### 5.3.2 Plataformas SaaS vs. On-Premise

| Componente | Modelo Preferido | Justificación |
|------------|-----------------|---------------|
| SRC — Motor de tarifas y clearing | SaaS con instancia dedicada | Complejidad de certificaciones de pago; actualización continua de reglas. |
| SGCF — GPS y control de flota | SaaS con edge local | Dependencia crítica de conectividad; necesidad de funcionamiento offline. |
| SIU — App móvil y web | SaaS + desarrollo custom | Frontend propio para marca Metro Sabanas. |
| SST — HSM y criptografía | HSM cloud (AWS CloudHSM, Azure Dedicated HSM) | FIPS 140-2 Nivel 3 sin inversión en hardware físico. |
| BI y Analytics | SaaS o self-hosted (Metabase, Superset) | Baja flota = datasets manejables; herramientas open-source viables. |
| Documental | Cloud o self-hosted (Nextcloud) | Integración con stack existente de Metro Sabanas. |

### 5.3.3 Bases de Datos y Persistencia

| Tipo de Dato | Tecnología | Justificación |
|--------------|-----------|---------------|
| Transacciones de recaudo | PostgreSQL + particionamiento por fecha | ACID compliance; auditoría; reportes regulatorios. |
| Posiciones GPS (series temporales) | TimescaleDB o InfluxDB | Alta frecuencia de escritura; consultas de rango eficientes. |
| Cache y sesiones | Redis | Baja latencia; TTL automático; manejo de tokens OAuth. |
| Archivos de video | MinIO / S3 compatible | Object storage; lifecycle policies; replicación multi-zona. |
| Logs y auditoría | Elasticsearch + Kibana o Loki + Grafana | Full-text search; agregación; alertas de seguridad. |
| Analytics y BI | ClickHouse o BigQuery | Columnar; compresión; consultas analíticas complejas. |


## 5.4 Nivel 3: Vista Física

### 5.4.1 Distribución Geográfica de Componentes

```
                    ┌─────────────────────────┐
                    │    CLOUD (AWS/Azure)    │
                    │  • Servidores virtuales │
                    │  • Bases de datos       │
                    │  • HSM / KMS            │
                    │  • APIs / Microservicios│
                    └───────────┬─────────────┘
                                │ Internet dedicado
                                │ 100 Mbps simétrico
                    ┌───────────▼─────────────┐
                    │   CENTRO DE CONTROL      │
                    │      DE OPERACIONES      │
                    │  Sincelejo, Oficinas MS  │
                    │  • Firewall + VPN        │
                    │  • Switch Gigabit        │
                    │  • 4 pantallas 55"       │
                    │  • 5 puestos de trabajo  │
                    │  • CCTV + Biometría      │
                    └───────────┬─────────────┘
                                │ 4G/5G + Radio
              ┌─────────────────┼─────────────────┐
              │                 │                 │
       ┌──────▼──────┐   ┌──────▼──────┐   ┌──────▼──────┐
       │   PARADEROS │   │    BUSES    │   │  TERMINALES │
       │  • Tipo I   │   │  • 34 buses │   │  • Tipo III │
       │  • Tipo II  │   │  • GPS      │   │  • Transfer │
       │  • Tipo III │   │  • Validador│   │  • Cámaras  │
       │  • CCTV     │   │  • WiFi     │   │  • WiFi     │
       │  • WiFi     │   │  • Botón    │   │  • Botón    │
       │  • Pantalla │   │    pánico   │   │  emergencia │
       └─────────────┘   └─────────────┘   └─────────────┘
```

### 5.4.2 Inventario de Componentes Físicos

#### Centro de Control de Operaciones (CCO)

| Categoría | Componente | Cantidad | Especificación Técnica |
|-----------|------------|----------|------------------------|
| **Video Wall** | Televisor industrial 55" UHD | 4 | Resolución 3840×2160; brillo ≥ 500 cd/m²; funcionamiento 24/7; entrada HDMI/DP; VESA 400×400; temperatura 0-40°C |
| **Video Wall** | Matriz de video (video wall controller) | 1 | 4 salidas HDMI; soporta 2×2; scaling; bezel compensation; control RS-232/LAN |
| **Estaciones de trabajo** | Computador doble pantalla (planeación + conciliación) | 2 | CPU ≥ Intel i7 / AMD Ryzen 7; RAM 32 GB; SSD 1 TB NVMe; 2 monitores 27" FHD; GPU integrada; Windows 11 Pro / Ubuntu 22.04 LTS |
| **Estaciones de trabajo** | Computador inicialización tarjetas | 2 | CPU ≥ Intel i5; RAM 16 GB; SSD 512 GB; lector/escritor Mifare; impresora térmica; Windows 11 Pro |
| **Estaciones de trabajo** | Computador programación de rutas | 1 | CPU ≥ Intel i7; RAM 32 GB; SSD 1 TB; 2 monitores 27"; software GIS (QGIS / ArcGIS) |
| **Seguridad electrónica** | Antena inicialización SAM | 4 | Frecuencia 13.56 MHz; protocolo ISO 14443A/B; compatibilidad Mifare Classic/Desfire; interfaz USB |
| **Energía** | UPS online 5 KVA | 1 | Tecnología online doble conversión; potencia 5 KVA / 4.5 KW; tiempo de autonomía ≥ 30 minutos; pantalla LCD; conectividad USB/RS-232 para monitoreo |
| **Redes** | Switch Gigabit administrable L3 | 1 | 24 puertos 10/100/1000 Mbps; 4 puertos SFP+; PoE+; VLAN; QoS; Spanning Tree; ACLs; SNMP; montaje rack 19" |
| **Redes** | Rack 19" 42U | 1 | Gabinete de piso; puertas perforadas; ventilación; bandeja gestión de cables; PDU |
| **Mobiliario** | Puesto de trabajo ergonómico | 5 | Mesa ajustable en altura; silla ergonómica; soporte dual monitor; iluminación LED; organización de cables |
| **Seguridad física** | Cámara CCTV CCO | 4 | Domo IP 4MP; lente 2.8-12 mm; IR 30 m; H.265; PoE; montaje techo |
| **Seguridad física** | Control de acceso biométrico | 1 | Lector huella + tarjeta; capacidad ≥ 1000 usuarios; registro de eventos; interfaz TCP/IP; integración con cerradura electromagnética |


#### Paraderos y Terminales

| Tipo | Cantidad | Componente | Especificación |
|------|----------|------------|----------------|
| **Tipo I — Básico** | ~20 | Señalización vertical | Poste de aluminio 2.5 m; panel informativo 60×40 cm; resistente a UV y vandalismo; código QR impreso (URL del micrositio) |
| **Tipo I — Básico** | ~20 | Información estática | Mapa de ruta y paradas; horarios de referencia; tarifas; números de contacto; laminado anti-reflejo |
| **Tipo II — Intermedio** | ~15 | Cobertura techada | Estructura metálica galvanizada; techo de policarbonato alveolar; dimensiones 2.5×1.2 m; resistencia viento 120 km/h |
| **Tipo II — Intermedio** | ~15 | Pantalla LED/TFT 21" | Panel 21.5" TFT; resolución 1920×1080; brillo ≥ 1000 cd/m²; conectividad 4G/WiFi; alimentación 12V DC; gabinete IP65; temperatura -10°C a +50°C |
| **Tipo II — Intermedio** | ~15 | Sistema energía solar | Panel solar 100W; regulador MPPT 10A; batería AGM 100Ah; autonomía ≥ 3 días sin sol; gabinete estanco |
| **Tipo II — Intermedio** | ~15 | Punto WiFi | Access point industrial 2.4 GHz; alcance 50 m; portal cautivo; 30 usuarios simultáneos; alimentación PoE |
| **Tipo III — Terminal** | ~5 | Estructura completa | Infraestructura de obra civil con techo, paredes, bancas, iluminación LED; accesibilidad PCD (rampa, espacio de maniobra) |
| **Tipo III — Terminal** | ~5 | Pantalla 43" | 2 unidades por terminal; panel 43" UHD; brillo ≥ 1500 cd/m²; orientación vertical/horizontal; control remoto; 4G/WiFi |
| **Tipo III — Terminal** | ~5 | Sistema de sonido | Altavoces activos 2×20W; amplificador integrado; conectividad Bluetooth/line-in; anuncios automáticos de llegada de bus |
| **Tipo III — Terminal** | ~5 | WiFi gratuito | Router 4G/5G industrial; access point dual band; ancho de banda compartido 50 Mbps; portal cautivo; estadísticas de uso |
| **Tipo III — Terminal** | ~5 | Punto de recarga USB | Módulo 4 puertos USB-A; 5V 2.4A por puerto; protección contra cortocircuito; iluminación LED indicadora |
| **Tipo III — Terminal** | ~5 | Cámaras CCTV | 2 cámaras IP 4MP por terminal; domo exterior; IR 40 m; H.265; NVR local 4 canales; grabación 30 días |
| **Tipo III — Terminal** | ~5 | Botón de emergencia | Botón antivandalismo; contacto seco; conexión a central de alarmas; señalización luminosa; identificación de terminal por código |

#### Equipamiento a Bordo (por cada uno de los 34 buses)

| Componente | Cantidad por bus | Especificación Técnica |
|------------|-----------------|------------------------|
| **Validador / Procesador de transacciones** | 1 | CPU ARM Cortex-A72 o similar; 2 GB RAM; 8 GB eMMC; pantalla táctil 7" 1024×600; lector Mifare Classic/Desfire (13.56 MHz); lector QR (cámara 2MP); lector EMV contactless (ISO 14443); módulo 4G/5G; GPS/GNSS multiconstelación; WiFi 802.11ac; Bluetooth 5.0; audio; 2× USB; alimentación 12-24V DC; consumo < 15W; temperatura -20°C a +60°C; certificación IP54; EMV Nivel 1 |
| **Torniquete electromecánico** | 1 | Tipo unidireccional; trinquete electromagnético; apertura por validador; sensor de paso (fotocélula); indicador LED; cierre automático; alimentación 12V DC; durabilidad ≥ 1.000.000 ciclos; acero inoxidable; ancho de paso 55 cm; tiempo de apertura 3-5 seg |
| **Cámaras conteo pasajeros** | 2 (una por puerta) | Tecnología 3D estéreo o térmica; resolución ≥ 640×480; fiabilidad ≥ 97% certificada; conteo bidireccional; integración con validador; alimentación PoE; temperatura -10°C a +50°C; IP54 |
| **Cámaras videovigilancia** | 2 | Resolución 1920×1080 (1080p); lente 2.8 mm (110°); IR 15 m; audio integrado; H.265; PoE; domo antivandalismo; IP54 |
| **Grabador central DVR** | 1 | 4 canales; H.265; 1080p @ 30 fps; SSD ≥ 500 GB; Ethernet Gigabit; PoE switch integrado 4 puertos; alimentación 12V DC; temperatura -20°C a +60°C; IP54; ONVIF; exportación por evento; sincronización NTP |
| **Consola / tablet conductor** | 1 | Tablet rugerizada 7" táctil; resolución 1280×800; brillo ≥ 600 cd/m²; CPU ARM octa-core; 4 GB RAM; 64 GB eMMC; 4G/5G; GPS; WiFi; Bluetooth; cámara frontal; altavoz; batería ≥ 8000 mAh; Android 12+ o Linux; MIL-STD-810G; IP65; montaje en soporte de succión/válvula; alimentación 12V DC |
| **Botón de pánico** | 2 (conductor + pasajeros) | Botón antivandalismo de contacto seco; señalización LED; transmisión inmediata por 4G/5G a CCO; geolocalización; alerta sonora en cabina; respuesta ≤ 30 seg |
| **Router WiFi industrial** | 1 | Router 4G/5G industrial; WiFi dual band 2.4/5 GHz 802.11ac/ax; ≥ 50 usuarios simultáneos; portal cautivo; ancho de banda compartido 20 Mbps; 4 LAN Gigabit; 1 WAN; VPN (IPsec/OpenVPN); firewall; montaje DIN rail; alimentación 12-24V DC; temperatura -20°C a +60°C; IP54 |
| **Cableado y accesorios** | 1 set | Cable UTP Cat6; cable coaxial RG59; cableado potencia 12V/24V; canalización; conectores; terminales; fusibles; bornes; etiquetado; documentación de cableado |
| **Antena GPS/GNSS externa** | 1 | GPS+GLONASS+Galileo+BeiDou; ganancia ≥ 28 dB; conector SMA; cable 3 m; montaje magnético o fijación; IP67; temperatura -40°C a +85°C |

### 5.4.3 Consolidado de Inventario Físico

| Categoría | Unidades | Nota |
|-----------|----------|------|
| Buses equipados ITS | 34 | Flota completa |
| Validadores | 34 | Uno por bus |
| Torniquetes | 34 | Uno por bus |
| Cámaras conteo pasajeros | 68 | 2 por bus |
| Cámaras videovigilancia | 68 | 2 por bus |
| DVRs | 34 | Uno por bus |
| Tablets conductor | 34 | Uno por bus |
| Botones de pánico | 68 | 2 por bus |
| Routers WiFi | 34 | Uno por bus |
| Antenas GPS | 34 | Una por bus |
| Paraderos Tipo I | ~20 | Sin energía |
| Paraderos Tipo II | ~15 | Con energía solar |
| Paraderos Tipo III | ~5 | Terminales de transferencia |
| Pantallas paraderos Tipo II | ~15 | 21" TFT |
| Pantallas paraderos Tipo III | ~10 | 43" UHD (2 por terminal) |
| Cámaras CCTV terminales | ~10 | 2 por terminal |
| Puestos CCO | 5 | Operadores + supervisor |
| Pantallas CCO | 4 | 55" UHD video wall |


## 5.5 Nivel 4: Vista de Comunicaciones

### 5.5.1 Arquitectura de Red

```
                            ┌─────────────────┐
                            │   INTERNET      │
                            │  PÚBLICO        │
                            └────────┬────────┘
                                     │
                            ┌────────▼────────┐
                            │  FIREWALL UTM     │
                            │  (Fortinet/Palo)  │
                            │  • IDS/IPS        │
                            │  • VPN SSL/IPsec  │
                            │  • Filtrado WEB   │
                            └────────┬────────┘
                                     │
              ┌──────────────────────┼──────────────────────┐
              │                      │                      │
     ┌────────▼────────┐    ┌───────▼────────┐    ┌───────▼────────┐
     │   RED IT        │    │   RED OT       │    │   RED GUESTS   │
     │  (Empresarial)  │    │  (Operacional) │    │  (WiFi público)│
     │  • Servidores   │    │  • Buses       │    │  • Paraderos   │
     │  • CCO admin    │    │  • Paraderos   │    │  • Buses       │
     │  • Gestión      │    │  • CCTV        │    │  • Portal      │
     │  • VLAN 10      │    │  • VLAN 20     │    │  • VLAN 30     │
     └─────────────────┘    └────────────────┘    └────────────────┘
```

### 5.5.2 Tecnologías de Conectividad

| Tecnología | Uso | Especificación | Cobertura |
|------------|-----|----------------|-----------|
| **Fibra óptica / Internet dedicado** | Backbone CCO → Cloud | 100 Mbps simétrico mínimo; SLA ≥ 99.9%; IP fija; latencia < 50 ms a Bogotá; redundancia física | Oficinas Metro Sabanas |
| **4G/5G (datos operativos)** | Buses, paraderos Tipo III, CCO backup | Plan empresarial M2M/IoT; APN privado; QoS garantizado; roaming nacional; SIM gestionada centralmente; ancho de banda ≥ 20 Mbps por bus | 100% de la flota y terminales |
| **4G/5G (transacciones financieras)** | Validadores en buses | Canal dedicado con prioridad de red; cifrado end-to-end; latencia < 200 ms; failover a offline | 100% de buses |
| **Radio trunking (backup)** | Corredores principales | Sistema digital DMR/TETRA; cobertura urbana; canal de emergencia; independiente de celular | Rutas principales |
| **WiFi (pasajeros)** | Buses y paraderos Tipo III | 802.11ac/ax; portal cautivo; ancho de banda compartido; filtrado de contenido; estadísticas | 100% de buses; 100% terminales |
| **WiFi (operacional)** | Buses, paraderos, CCO | Red interna segregada; acceso restringido; gestión centralizada; monitoreo | 100% de dispositivos |
| **VPN (site-to-site)** | CCO ↔ Cloud; CCO ↔ proveedores | IPsec o WireGuard; túneles cifrados; autenticación de certificados; split tunneling | Todos los sitios |
| **VPN (cliente)** | Acceso remoto administrativo | OpenVPN / WireGuard; MFA; acceso restringido por rol; sesiones auditadas | Administradores |
| **MQTT** | IoT buses → Cloud | Broker mosquitto o HiveMQ; tópicos jerárquicos; QoS 1; TLS; persistencia | 34 buses |
| **WebSocket** | Tiempo real SIU → Usuarios | Conexión persistente; heartbeat; reconexión automática; compresión | App/Web |
| **REST API** | Integración general | JSON; OAuth 2.0; rate limiting; versioning; documentación OpenAPI | Todos los sistemas |
| **GraphQL** | Consultas flexibles (BI, app) | Endpoint único; introspección; resolvers; caching | App móvil, dashboards |
| **EMV / Mifare / QR** | Protocolos de pago | ISO 14443; ISO 7816; EMVCo; códigos QR ISO/IEC 18004 | Validadores |

## 5.6 Atributos de Calidad de la Arquitectura

| Atributo | Definición | Métrica | Mecanismo |
|----------|------------|---------|-----------|
| **Integración** | Capacidad de los subsistemas para intercambiar datos y funciones | Latencia de sincronización < 5 segundos entre SRC-SGCF-SIU | APIs REST unificadas; bus de mensajes; esquemas de datos compartidos |
| **Interoperabilidad** | Capacidad de interactuar con sistemas externos | 100% de reportes regulatorios generables automáticamente | Formato JSON/XML estándar; APIs abiertas documentadas; integración con MinTransporte y SuperTransporte |
| **Escalabilidad** | Capacidad de crecer sin degradación | Sistema operativo con 100 buses sin rediseño arquitectónico | Arquitectura microservicios; auto-scaling horizontal; bases de datos particionables |
| **Neutralidad tecnológica** | No dependencia de proveedor único | Migración de proveedor cloud en < 30 días | Contenedores Docker; Kubernetes; estándares abiertos; código propio donde aplique |
| **Estabilidad** | Resistencia a fallas y continuidad de servicio | Disponibilidad ≥ 99.9% (SLA); RTO < 4 horas; RPO < 15 minutos | Redundancia multi-zona; backup automático; failover automático; monitoreo 24/7 |
| **Ciberseguridad** | Protección contra amenazas digitales | 0 brechas de seguridad críticas; cumplimiento ISO 27001; pentest anual | Defensa en profundidad; Zero Trust; cifrado end-to-end; segmentación de red; SIEM; IAM |


---

# 6. CENTRO DE CONTROL DE OPERACIONES (CCO)

## 6.1 Concepto de Operación del CCO

El Centro de Control de Operaciones es el **corazón neuronal** del SETP Sincelejo. Desde este espacio, un equipo reducido pero capacitado (5 personas en turnos) monitorea, coordina, planifica y responde ante cualquier evento que afecte la operación de los 34 buses, la experiencia de 7.670 pasajeros diarios y la integridad financiera del sistema.

El CCO no es una sala de monitoreo pasivo. Es un **centro de decisión operativa** donde se cruzan en tiempo real:
- La posición de cada bus (SGCF)
- El estado de recaudo de cada vehículo (SRC)
- Las alertas de seguridad y emergencia (SST + SGCF)
- Las consultas y quejas de los usuarios (SIU)
- Los reportes regulatorios pendientes (Documental)

## 6.2 Ubicación y Condiciones Físicas

| Aspecto | Especificación |
|-----------|----------------|
| **Ubicación** | Oficinas principales de Metro Sabanas S.A.S., Sincelejo, Sucre |
| **Área mínima** | 40 m² (sala CCO + pequeño almacén técnico) |
| **Climatización** | Aire acondicionado split 24.000 BTU (funcionamiento 24/7); temperatura 22-24°C; humedad 40-60% |
| **Iluminación** | LED regulable; sin parpadeo; control independiente de video wall vs. puestos de trabajo |
| **Aislamiento acústico** | Puerta acústica; paredes con tratamiento absorvente; piso técnico opcional |
| **Energía** | UPS 5 KVA online + grupo electrógeno backup (opcional) |
| **Conectividad** | Fibra óptica 100 Mbps simétrico + 4G/5G backup |
| **Seguridad física** | Control de acceso biométrico; CCTV interno; botón de pánico silencioso conectado a cuerpos de seguridad |

## 6.3 Hardware del CCO

### 6.3.1 Video Wall y Monitoreo Visual

El video wall constituye la interfaz visual principal para el monitoreo situacional. Con 4 pantallas de 55" en configuración 2×2, se distribuyen los siguientes dashboards:

| Pantalla | Contenido | Fuente de datos |
|----------|-----------|-----------------|
| **Pantalla 1 (superior izquierda)** | Mapa en tiempo real de la flota | SGCF — posición GPS de los 34 buses; estado (en ruta, detenido, desviado, en terminal); color por cumplimiento de frecuencia |
| **Pantalla 2 (superior derecha)** | Alertas y eventos operativos | SGCF + SST — exceso de velocidad, fuera de ruta, botón de pánico, falla de validador, bus detenido > 10 minutos |
| **Pantalla 3 (inferior izquierda)** | Recaudo en tiempo real | SRC — transacciones por minuto; acumulado del día; comparativa vs. día anterior; alertas de anomalías de recaudo |
| **Pantalla 4 (inferior derecha)** | Videovigilancia en vivo | SGCF — cámaras de buses (rotación automática); cámaras de terminales; acceso manual a cámara específica |

### 6.3.2 Puestos de Trabajo

| Puesto | Rol | Hardware | Software principal |
|--------|-----|----------|-------------------|
| **Puesto 1: Supervisor de turno** | Coordina operación; toma decisiones tácticas; atiende emergencias | 2 monitores 27" FHD; computador i7/32GB/1TB SSD | Dashboard unificado; comunicaciones; documental |
| **Puesto 2: Operador de flota** | Monitorea rutas, frecuencias, desviaciones; contacta conductores | 2 monitores 27" FHD; computador i7/32GB/1TB SSD | SGCF; mapa GIS; chat/radio; app de mensajería |
| **Puesto 3: Operador de recaudo** | Concilia transacciones; atiende inconsistencias; genera reportes financieros | 2 monitores 27" FHD; computador i7/32GB/1TB SSD | SRC; planilla Excel avanzada; BI; portal bancario |
| **Puesto 4: Atención al usuario** | Responde PQRSD; maneja WhatsApp/call center; bloquea tarjetas | 2 monitores 27" FHD; computador i5/16GB/512GB SSD | SIU; CRM; call center software; WhatsApp Business |
| **Puesto 5: Inicialización y SAM** | Emite tarjetas; inicializa SAM; atiende operadores; gestiona inventario | 1 monitor 27" + lector/escritor Mifare; computador i5/16GB/512GB SSD | Software de emisión; HSM local; impresora térmica; inventario |

## 6.4 Software del CCO

### 6.4.1 Plataformas SaaS Operativas

| Plataforma | Función | Acceso desde CCO | Integración |
|------------|---------|------------------|-------------|
| **SRC SaaS** | Recaudo, clearing, compensación | Dashboard web; reportes descargables; conciliación automática | SGCF (posición para tarifa zonal); bancos (PSE); SAP Metro Sabanas |
| **SGCF SaaS** | GPS, control de flota, alertas | Mapa en tiempo real; panel de alertas; histórico de recorridos; videovigilancia | SRC (ocupación); SIU (predicción de llegada); API MinTransporte |
| **SIU SaaS** | Información al usuario | Configuración de contenidos; monitoreo de pantallas; estadísticas de app | SGCF (posición); SRC (saldo, recarga); redes sociales |
| **SST SaaS** | Seguridad de transacciones | Monitoreo de HSM; gestión de claves; auditoría de criptografía; certificados | SRC (cifrado); todos los sistemas (autenticación) |
| **BI / Analytics** | Inteligencia de negocio | Dashboards de KPIs; reportes programados; análisis de tendencias; alertas de negocio | Todos los sistemas (data warehouse) |

### 6.4.2 Capacidades Operativas del CCO

| Capacidad | Descripción | Tecnología Habilitadora |
|-----------|-------------|------------------------|
| **Monitoreo en tiempo real de 34 buses** | Cada bus reporta posición, velocidad, estado de puertas, estado de validador, ocupación estimada, cada 3-5 segundos | GPS/GNSS + 4G/5G + MQTT + dashboard GIS |
| **Gestión de recaudo y compensación automática** | Las transacciones se validan, registran, concilian y distribuyen automáticamente entre ente gestor y operadores | Motor de clearing + reglas de compensación + integración bancaria |
| **Atención de incidentes y emergencias** | Botón de pánico genera alerta en CCO con geolocalización, video en vivo, contacto automático a cuerpos de emergencia | CEP + geocercas + integración con Policía / Bomberos / Secretaría de Movilidad |
| **Programación y ajuste de rutas y frecuencias** | El supervisor modifica horarios, frecuencias, asignación de buses a rutas, en respuesta a demanda o eventos | Planificador de rutas + GIS + algoritmo de optimización + comunicación al conductor vía tablet |
| **Generación de reportes y KPIs** | Reportes automáticos diarios/semanales/mensuales de operación, recaudo, calidad, incidentes; exportables a Excel/PDF | BI + report scheduler + templates regulatorios |
| **Integración con autoridades** | Generación y envío automático de reportes a MinTransporte, SuperTransporte, ANSV; integración con sistemas de reporte nacional | APIs regulatorias + formatos XML/JSON estándar + firma digital |

## 6.5 Seguridad del CCO

| Capa | Medida | Especificación |
|------|--------|----------------|
| **Perímetro físico** | Control de acceso biométrico + tarjeta | Huella dactilar + tarjeta Mifare; registro de hora de ingreso/egreso; alerta de acceso no autorizado |
| **Vigilancia** | CCTV interno 24/7 | 4 cámaras domo IP 4MP; grabación 90 días; acceso remoto seguro; detección de movimiento |
| **Red** | Segmentación OT/IT | VLAN separadas para operación (OT), administración (IT) y visitantes (Guests); firewall entre segmentos; ACLs estrictas |
| **Monitoreo de seguridad** | SIEM (Security Information and Event Management) | Agregación de logs de firewall, servidores, aplicaciones, bases de datos; correlación de eventos; alertas automáticas; dashboard de amenazas |
| **Backup** | Backup en tiempo real + offsite | Replicación continua de bases de datos a cloud secundario; backup de video; RPO < 15 minutos; RTO < 4 horas |
| **Continuidad** | UPS + procedimiento de emergencia | UPS 5 KVA soporta 30 minutos; procedimiento documentado de apagado ordenado; grupo electrógeno opcional; failover 4G/5G |


---

# 7. PARADEROS Y TERMINALES

## 7.1 Estrategia de Tipificación

Sincelejo no requiere uniformidad tecnológica en todos sus paraderos. La estrategia de tipificación permite optimizar la inversión asignando mayor equipamiento donde la demanda lo justifica, manteniendo funcionalidad básica en puntos de baja afluencia.

### 7.1.1 Matriz de Tipificación

| Tipo | Cantidad estimada | Ubicación típica | Perfil de demanda | Energía | Conectividad |
|------|-------------------|-------------------|---------------------|---------|--------------|
| **I — Básico** | ~20 | Calles secundarias; barrios periféricos; puntos de baja afluencia | < 50 pasajeros/hora | No requiere | Ninguna (pasiva) |
| **II — Intermedio** | ~15 | Corredores principales; zonas comerciales; instituciones educativas | 50-200 pasajeros/hora | Solar + batería | 4G/5G; WiFi |
| **III — Terminal de transferencia** | ~5 | Intercambios entre rutas; centros comerciales; hospital; terminal de transporte | > 200 pasajeros/hora | Conexión eléctrica | 4G/5G dedicado; WiFi; Ethernet |

### 7.1.2 Justificación de la Tipificación

- **Tipo I**: La inversión en pantallas y energía solar no se justifica económicamente en paraderos con baja afluencia. El código QR permite al usuario con smartphone acceder a la misma información que tendría en una pantalla, delegando el costo del display al dispositivo personal.
- **Tipo II**: La energía solar es viable en Sincelejo dada la alta radiación solar promedio (5.5 kWh/m²/día). El costo de un sistema solar de 100W + batería 100Ah es recuperable en 2-3 años frente a la conexión eléctrica urbana en zonas donde no hay infraestructura cercana.
- **Tipo III**: Las terminales de transferencia son puntos críticos de la red. El usuario toma decisiones de ruta aquí; la información en tiempo real reduce el tiempo de espera percibido y mejora la satisfacción. La inversión en infraestructura completa es estratégica.

## 7.2 Especificación Detallada por Tipo

### 7.2.1 Paradero Tipo I — Básico

| Componente | Especificación | Función |
|------------|----------------|---------|
| **Poste de señalización** | Aluminio anodizado 2.5 m; base de concreto 40×40 cm; resistencia a viento 120 km/h; color corporativo Metro Sabanas | Identificación del paradero; visibilidad desde 50 m |
| **Panel informativo** | Lámina de aluminio compuesto 60×40 cm; impresión UV resistente a desgaste; antigrafiti (opcional); fijación con tornillos antivandalismo | Información estática: nombre de paradero, rutas que pasan, destinos, horarios de referencia, tarifas, código QR |
| **Código QR** | Impreso en panel; URL del micrositio del SETP; URL con parámetro de paradero para pre-carga de información | Acceso a información dinámica (tiempos de llegada, mapa, alertas) mediante smartphone del usuario |
| **Señalética de accesibilidad** | Símbolo internacional de silla de ruedas; altura 1.2 m; braille (opcional) | Cumplimiento de normativa de accesibilidad |

**Costo referencial:** Por definir en estudio de mercado (estimado: $500.000 - $1.000.000 COP por unidad)

### 7.2.2 Paradero Tipo II — Intermedio

| Componente | Especificación | Función |
|------------|----------------|---------|
| **Estructura techada** | Perfiles de aluminio extruido; techo de policarbonato alveolar 6 mm UV protegido; dimensiones 2.5 m (ancho) × 1.2 m (profundo) × 2.4 m (alto); piso antideslizante; bancas integradas (2); resistencia viento 120 km/h | Protección solar y lluvia; espacio de espera confortable; durabilidad ≥ 15 años |
| **Pantalla LED/TFT 21"** | Panel 21.5" TFT-LCD; resolución 1920×1080; brillo ≥ 1000 cd/m² (legible a pleno sol); ángulo de visión 178°; vida útil 50.000 horas; control remoto; conectividad 4G/WiFi; alimentación 12V DC; gabinete metálico IP65; temperatura operación -10°C a +50°C; ventilación forzada | Visualización de tiempos de llegada de cada ruta; estado de servicio (normal, retrasado, suspendido); hora; temperatura; mensajes institucionales |
| **Controlador de pantalla** | Mini PC industrial (Intel Celeron J4125 o similar); 4 GB RAM; 64 GB eMMC; 4G modem integrado; WiFi; Ethernet; GPIO; alimentación 12V; Linux; IP65; gestión remota | Procesamiento de contenido; conexión a backend SIU; reproducción de contenido offline; actualización OTA |
| **Sistema de energía solar** | Panel solar fotovoltaico 100W monocristalino; eficiencia ≥ 18%; regulador MPPT 10A; batería AGM de ciclo profundo 100Ah; autonomía ≥ 3 días sin radiación solar; gabinete estanco IP65 para batería; protección contra sobrecarga y descarga profunda; indicador LED de estado de carga | Alimentación autónoma de pantalla, controlador y WiFi; independencia de red eléctrica; bajo costo operativo |
| **Access point WiFi** | Punto de acceso industrial 2.4 GHz; potencia 100 mW; alcance 50 m; soporte 30 usuarios simultáneos; portal cautivo; ancho de banda compartido 10 Mbps; alimentación PoE o 12V; montaje interior de estructura | Conectividad gratuita para usuarios; canal de comunicación adicional; captura de estadísticas de uso |
| **Iluminación interior** | LED 12W; panel solar con sensor crepuscular; autonomía 8 horas; temperatura de color 4000K | Iluminación de seguridad durante la noche; bajo consumo |

**Costo referencial:** Por definir en estudio de mercado (estimado: $8.000.000 - $12.000.000 COP por unidad, incluyendo obra civil base)

### 7.2.3 Paradero Tipo III — Terminal de Transferencia

| Componente | Especificación | Función |
|------------|----------------|---------|
| **Infraestructura de obra civil** | Fundación de concreto; estructura metálica o mampostería; techo de teja metálica o policarbonato; piso cerámico antideslizante; bancas de concreto/madera (4-6); espacio para silla de ruedas; rampa de acceso PCD; iluminación LED 20W; dimensiones 6×3 m mínimo; altura 3 m; resistencia sismo A | Confort y accesibilidad; durabilidad; identidad urbana del SETP |
| **Pantalla 43" UHD** | 2 unidades por terminal; panel 43" 4K UHD; resolución 3840×2160; brillo ≥ 1500 cd/m² (alta luminosidad); orientación horizontal o vertical; control remoto; conectividad 4G/5G/WiFi/Ethernet; alimentación 110-240V; gabinete metálico IP65; sistema de ventilación forzada; protección solar; antivandalismo | Información de rutas y tiempos; publicidad institucional; mapa de conexiones; alertas de servicio; instrucciones de transferencia |
| **Controlador de pantalla** | Mini PC industrial (Intel i3 o similar); 8 GB RAM; 128 GB SSD; 4G/5G modem; WiFi; Ethernet; GPIO; alimentación 12V; Windows 10 IoT o Linux; IP65; gestión remota; soporte 2 pantallas | Procesamiento de contenido; conexión a backend SIU; reproducción offline; actualización OTA; soporte de video 4K |
| **Sistema de sonido** | 2 altavoces activos de 20W cada uno; amplificador integrado; conectividad Bluetooth y line-in; anuncios automáticos programados; volumen ajustable según hora; altavoces orientados hacia zona de espera | Anuncios de llegada de buses; alertas de servicio; información de transferencia; mensajes de seguridad |
| **WiFi gratuito** | Router 4G/5G industrial (Cisco, Cradlepoint, Sierra Wireless o similar); access point dual band 2.4/5 GHz 802.11ac; ancho de banda compartido 50 Mbps; ≥ 100 usuarios simultáneos; portal cautivo con términos de uso; estadísticas de uso; filtrado de contenido básico; QoS | Conectividad gratuita; mejora de experiencia de usuario; captura de datos demográficos; canal de comunicación |
| **Punto de recarga USB** | Módulo empotrado en banca o pared; 4 puertos USB-A; 5V 2.4A por puerto; protección contra cortocircuito, sobrecarga y sobretensión; LED indicador de estado; apagado automático si no hay dispositivo; bajo consumo en standby | Servicio de valor agregado; mejora de percepción; atractivo para usuarios jóvenes |
| **Cámaras CCTV** | 2 cámaras IP domo exterior 4MP por terminal; lente 2.8-12 mm; IR 40 m; WDR 120 dB; H.265; PoE; IP67; montaje en pared o techo; cubierta antivandalismo; NVR local 4 canales; disco 2 TB; grabación 24/7; retención 30 días; acceso remoto seguro | Seguridad de usuarios; disuasión de vandalismo; evidencia de incidentes; monitoreo desde CCO |
| **Botón de emergencia** | Botón de parada de emergencia antivandalismo; contacto seco; conexión a central de alarmas vía 4G o radio; señalización LED roja intermitente; identificación de terminal por código único; prueba mensual automática; respuesta esperada < 5 minutos | Atención de emergencias médicas, de seguridad o mecánicas; conexión a Policía, Bomberos o ambulancia |
| **Conectividad dedicada** | Modem 4G/5G industrial con plan de datos empresarial; antena exterior direccional o omnidireccional; SLA ≥ 99%; IP fija opcional; VPN hacia CCO; QoS garantizado; monitoreo de señal; failover automático a red alternativa | Conectividad confiable para pantallas, cámaras, botón de emergencia; independencia de WiFi público |

**Costo referencial:** Por definir en estudio de mercado (estimado: $45.000.000 - $75.000.000 COP por unidad, incluyendo obra civil completa)

## 7.3 Gestión Energética de Paraderos

| Tipo | Fuente principal | Backup | Consumo estimado | Gestión |
|------|-----------------|--------|------------------|---------|
| **Tipo I** | Ninguna (pasivo) | N/A | 0 W | Sin gestión |
| **Tipo II** | Solar 100W + batería 100Ah | Ninguna | 30-50 W (pantalla + controlador + WiFi) | Regulador MPPT; monitoreo remoto de estado de batería; alerta de bajo voltaje |
| **Tipo III** | Conexión eléctrica urbana 110V | Ninguna (o UPS pequeño para pantallas) | 200-400 W (pantallas + sonido + WiFi + cámaras + recarga USB) | Medidor de consumo; monitoreo remoto; alerta de corte de energía; contacto con operador de red |


---

# 8. EQUIPAMIENTO A BORDO (BUSES)

## 8.1 Concepto de "Bus Inteligente"

Cada uno de los 34 buses del SETP Sincelejo se convierte en una **unidad de borde computacional** (edge computing) que:
- Recauda y valida pagos autónomamente (incluso offline)
- Se localiza y reporta en tiempo real
- Graba video de seguridad continuo
- Cuenta pasajeros con precisión
- Informa al conductor sobre su operación
- Ofrece WiFi a los usuarios
- Responde a emergencias

El diseño del equipamiento a bordo prioriza la **robustez** sobre la sofisticación. Los buses operan en condiciones de vibración, temperatura, humedad y polvo que destruyen equipamiento de oficina. Cada componente debe estar certificado para operación móvil, con temperatura de funcionamiento extendida, protección contra polvo y salpicaduras, y resistencia a vibración.

## 8.2 Especificaciones Técnicas Detalladas por Componente

### 8.2.1 Validador / Procesador de Transacciones

| Atributo | Especificación | Justificación |
|----------|----------------|---------------|
| **Procesador** | ARM Cortex-A72 quad-core @ 1.5 GHz o equivalente (Intel Atom x7-E3950, Rockchip RK3399) | Suficiente para procesar transacciones, criptografía, red y UI simultáneamente |
| **RAM** | 2 GB LPDDR4 | Soporte de sistema operativo, aplicación, cache de transacciones y manejo de listas blancas |
| **Almacenamiento** | 8 GB eMMC + ranura microSD | Sistema operativo, aplicación, logs, cache de transacciones offline; microSD para almacenamiento extendido |
| **Pantalla** | Táctil capacitiva 7"; resolución 1024×600; brillo ≥ 500 cd/m²; tratamiento anti-reflejo | Visibilidad en condiciones de luz variable; interacción táctil para diagnóstico y configuración |
| **Lector Mifare** | 13.56 MHz; ISO 14443A/B; Mifare Classic 1K/4K; Mifare DESFire EV1/EV2/EV3; NFC Forum Type 1/2/3/4 | Tarjeta del sistema; tarjetas bancarias contactless; pagos con smartphone NFC |
| **Lector QR** | Cámara 2MP; enfoque 10-50 cm; decodificación en < 200 ms; soporta QR estándar, Aztec, Data Matrix | Pagos con app móvil; tickets digitales; promociones |
| **Lector EMV** | Contactless; ISO 14443; EMVCo certificado; Nivel 1 (hardware) y Nivel 2 (software) | Aceptación de tarjetas de crédito/débito; inclusión financiera; atracción de usuarios sin tarjeta del sistema |
| **Módulo celular** | 4G LTE Cat 4 o 5G; dual SIM; bandas Colombianas (B2, B4, B28); APN privado; GPS integrado | Transmisión de transacciones; posicionamiento; backup de conectividad; roaming |
| **GPS/GNSS** | Multiconstelación: GPS (L1), GLONASS, Galileo, BeiDou; precisión < 5 m; 10 Hz actualización | Posicionamiento preciso; geocercas; tarifa zonal; predicción de llegada |
| **WiFi** | 802.11ac; 2.4/5 GHz; modo AP + STA | Conexión a router interno del bus; diagnóstico; actualización OTA |
| **Bluetooth** | 5.0; BLE | Mantenimiento; beaconing; diagnóstico cercano |
| **Audio** | Buzzer + altavoz 2W | Feedback sonoro al usuario (aceptado, rechazado, saldo bajo) |
| **Interfaces** | 2× USB 2.0; 1× RS-232; 1× Ethernet 10/100 | Periféricos; conexión legacy; diagnóstico |
| **Alimentación** | 12-24 V DC; protección contra sobretensión, inversión de polaridad, picos de arranque | Compatibilidad con red eléctrica del bus (12V o 24V según modelo) |
| **Consumo** | < 15 W en operación | Bajo impacto en batería del bus; operación con motor apagado |
| **Temperatura** | -20°C a +60°C | Operación en Sincelejo (clima cálido) y en condiciones de aparcamiento al sol |
| **Protección** | IP54 (polvo y salpicaduras) | Resistencia a limpieza del bus, polvo y salpicaduras ocasionales |
| **Certificación** | EMV Nivel 1 (hardware); CE; FCC; certificación eléctrica local | Cumplimiento de estándares internacionales de pagos y seguridad eléctrica |
| **Montaje** | Panel frontal o pedestal en entrada del bus; ángulo ajustable 15-45°; fijación antivandalismo | Acceso ergonómico al usuario; resistencia a impactos y vandalismo |

