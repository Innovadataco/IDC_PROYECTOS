# PROYECTO-004-2026-SETP-SINCELEJO
## Documento 1: Arquitectura ITS Completa para SETP Sincelejo
### Sistema Estratégico de Transporte Público — Componente Tecnológico ITS

---

**Versión:** 1.1 (Reestructurado)  
**Fecha:** Mayo 2026  
**Cliente:** METRO SABANAS S.A.S. / Sincelejo  
**Consultor:** INNOVADATACO  
**Clasificación:** CONFIDENCIAL — USO INTERNO  

---

## TABLA DE CONTENIDO

1. Introducción y Propósito
2. Marco Normativo y Legal
3. Concepto de Operación (CONOPS)
4. Arquitectura ITS de Referencia
5. Clasificación de Servicios ITS para SETP Urbano
6. Servicios Estratégicos Detallados (SRC, SGCF, SIU, SST)
7. Equipamiento a Bordo de Buses
8. Centro de Control de Operaciones (CCO)
9. Fichas Técnicas de Componentes de Campo
10. Conectividad y Red de Telecomunicaciones
11. Ciberseguridad y Gobernanza de Datos
12. Requerimientos Funcionales (RF) y No Funcionales (RNF)
13. Plan de Implementación por Fases
14. Anexos Técnicos

---

# 1. INTRODUCCIÓN Y PROPÓSITO

## 1.1 Contexto del SETP Sincelejo

Sincelejo, capital del departamento de Sucre, concentra una dinámica urbana creciente que exige una transformación estructural de su sistema de movilidad. El Sistema Estratégico de Transporte Público (SETP) de Sincelejo, adoptado mediante Decreto 393 de 2010 y reconfigurado a través del modelo tarifa técnica + Fondo de Estabilización Tarifaria (FEST) con una concesión de 20 años, representa el esfuerzo institucional más significativo para ordenar, formalizar y modernizar el transporte público colectivo en la ciudad.

El ente gestor, **Metro Sabanas S.A.S.**, opera actualmente una flota de **34 buses** distribuidos en **5 rutas estructuradas**, con una demanda oficial de **7.670 pasajeros diarios** — cifra resultante de la reestructuración operativa definida en la Medida de Simulación de Servicio MS-130 de 2025.

## 1.2 Naturaleza del Proyecto: Brownfield con Ambición Greenfield

El presente proyecto se clasifica como **Brownfield** — es decir, se ejecuta sobre una infraestructura de transporte existente con operación comercial activa, regulación vigente, rutas establecidas y una organización institucional funcional. No obstante, el componente tecnológico ITS se aborda con una ambición **Greenfield**: diseñar desde cero una arquitectura integral de sistemas inteligentes de transporte que eleve progresivamente la operación a estándares de ciudad inteligente, interoperabilidad nacional y trazabilidad regulatoria completa.

La modalidad contractual (tarifa técnica + FEST) impone una condición crítica: los sistemas de recaudo, control, información y seguridad transaccional deben ser **auditables, transparentes y resilientes**, porque el flujo de compensación económica entre el ente gestor, los operadores y las autoridades regulatorias depende directamente de la calidad de los datos que estos sistemas producen.

## 1.3 Propósito del Documento

Este documento define el marco técnico, funcional, operativo y normativo para la estructuración, adquisición, implementación y operación del componente tecnológico ITS del SETP Sincelejo, garantizando que la arquitectura propuesta sea:

- **Integrada**: Cada subsistema conversa con los demás en tiempo real, no opera en silos.
- **Interoperable**: Compatible con los sistemas de reporte del MinTransporte, SuperTransporte, ANSV y otras entidades regulatorias.
- **Escalable**: Diseñada para crecer desde 34 buses hasta 100+ sin rediseño arquitectónico radical.
- **Neutral tecnológicamente**: No depende de un único proveedor, plataforma o estándar propietario.
- **Cibersegura**: Con defensa en profundidad desde el campo hasta el cloud.
- **Auditables**: Cada transacción, evento y decisión del sistema es trazable, inmutable y reportable.

## 1.4 Alcance y Delimitación

| Incluido | Excluido |
|:---|:---|
| ITS para buses urbanos (34 unidades) | Paraderos con equipamiento ITS |
| CCO y su infraestructura completa | Infraestructura vial física |
| Software especializado ITS (SRC, SGCF, SIU, SST) | Modelo financiero del proyecto general |
| Conectividad (celular, satelital, WiFi) | EtB — no aplica |
| Ciberseguridad y gobernanza de datos | Regulación de tarifas (ANSV) |
| Fichas técnicas de cada componente ITS | Desarrollo de apps desde cero |

---

# 2. MARCO NORMATIVO Y LEGAL

## 2.1 Jerarquía Normativa Aplicable

### 2.1.1 Marco de Transporte Público

| Norma | Tipo | Alcance Relevante |
|-------|------|-----------------|
| **Decreto 393 de 2010** | Adopción del SETP | Creación legal del SETP en Sincelejo; modelo de organización, concesión y operación. Base del FEST y tarifa técnica. |
| **Decreto 482 de 2023** | Modificación modelo transporte | Actualización del modelo de transporte; reconfiguración de roles entre ente gestor, operadores y autoridades. |
| **Decreto 909 de 2023** | Reglamentación SETP | Especificación de obligaciones técnicas, operativas y de información del ente gestor; reportes a SuperTransporte y MinTransporte. |
| **Decreto 1079 de 2015** | Sector transporte | Reglamentación del Ministerio de Transporte en materia de transporte terrestre automotor; estándares de servicio, calidad y seguridad. |
| **Decreto 2060 de 2023** | Política ITS Nacional | Marco de política para ITS en Colombia; definición de estándares, interoperabilidad y gobernanza de datos en sistemas de transporte. |
| **CONPES 3637 de 2010** | Política pública | Documento de origen del SETP Sincelejo; lineamientos de política de movilidad sostenible y ordenamiento del transporte. |

### 2.1.2 Marco Tecnológico y ITS

| Norma | Tipo | Alcance Relevante |
|-------|------|-----------------|
| **Resolución 20203040034065** | Estándares ITS | Definición de estándares técnicos para Sistemas Inteligentes de Transporte en Colombia; especificación de subsistemas, interfaces y protocolos de comunicación. |
| **Resolución 20223040028675 (PMITS)** | Estándares ITS | Plan Maestro de ITS; funciones mínimas técnicas y atributos de calidad para proyectos ITS. |
| **Ley 1702 de 2013** | Prioridad nacional | Declaración de interés nacional de los proyectos de ITS; habilitación de mecanismos de financiación y agilización administrativa. |
| **Ley 2251 de 2022** | Seguridad vial | Sistema Seguro; integración de tecnología para prevención de siniestros, monitoreo de comportamiento de conductores y reporte a la ANSV. |

### 2.1.3 Marco de Protección de Datos y Ciberseguridad

| Norma | Tipo | Alcance Relevante |
|-------|------|-----------------|
| **Ley 1581 de 2012** | Protección de datos | Régimen de protección de datos personales; obligaciones de custodia, tratamiento, transparencia y derechos ARCO. |
| **Decreto 1377 de 2013** | Reglamentación Ley 1581 | Autorización de tratamiento de datos; políticas de privacidad y consentimiento informado. |
| **Circular Externa 052 de 2021** | Ciberseguridad financiera | Requisitos de seguridad para entidades que operan con datos de medios de pago. |
| **ISO 27001:2022** | Estándar internacional | Sistema de gestión de seguridad de la información. |
| **NIST Cybersecurity Framework** | Marco de referencia | Estructura de identificar, proteger, detectar, responder, recuperar. |
| **IEC 62443** | Estándar industrial | Seguridad ciberfísica para sistemas de control industrial; aplica a redes OT y dispositivos de campo. |

### 2.1.4 Marco Contractual y Financiero

| Documento | Tipo | Alcance Relevante |
|-----------|------|-----------------|
| **Contrato de concesión FEST** | Contractual | Vigencia de 20 años; obligaciones de inversión en tecnología; reportes de operación y compensación. |
| **Medida de Simulación MS-130 de 2025** | Técnico-regulatorio | Reducción oficial de la flota a 34 buses y 5 rutas; base de diseño de capacidad del sistema ITS. |

## 2.2 Implicaciones Arquitectónicas de la Normativa

1. **Decreto 2060 de 2023** establece la política nacional de ITS, obligando a los sistemas a reportar estructura de subsistemas al MinTransporte; la arquitectura debe generar estos reportes automáticamente.
2. **Resolución 20203040034065** define los estándares técnicos de ITS; obliga a interoperabilidad mediante protocolos abiertos y trazabilidad funcional.
3. **Resolución 20223040028675 (PMITS)** establece los atributos de calidad: integración, interoperabilidad, escalabilidad, neutralidad tecnológica, estabilidad, ciberseguridad.
4. **Ley 1581/2012** impone que los datos de geolocalización de usuarios, transacciones de pago y registros de videovigilancia sean tratados bajo estrictos controles de consentimiento y derechos ARCO.
5. **Ley 2251/2022** exige que el SGCF integre capacidades de detección de comportamientos de riesgo del conductor (fatiga, exceso de velocidad, frenadas bruscas) y reporte automático a la ANSV.
6. **Decreto 909/2023** define la periodicidad y contenido de los reportes de operación: kilómetros recorridos, pasajeros transportados, ingresos por recaudo, cumplimiento de frecuencias, incidentes.

---

# 3. CONCEPTO DE OPERACIÓN (CONOPS)

## 3.1 Modelo de Referencia Operacional

El Concepto de Operación (CONOPS) se establece como el instrumento técnico y el eje articulador de la inteligencia operativa del SETP Sincelejo. Se define como el Plano Maestro Operativo diseñado para garantizar que la interacción entre los diversos actores estratégicos, los procesos de gestión y la plataforma tecnológica responda a una lógica de servicio sistémica, coherente y de alto desempeño.

A diferencia de los documentos de diseño físico, que se limitan a la descripción de componentes, el CONOPS se enfoca en la fisiología del sistema; es decir, en la dinámica de procesamiento y la lógica funcional que permite transformar datos en decisiones operativas de alto valor.

## 3.2 Actores del Sistema

| Actor | Rol | Interacción con ITS |
|-------|-----|---------------------|
| **Usuario final (pasajero)** | Beneficiario del servicio | Utiliza app móvil, consulta información en canales digitales, paga con tarjeta/QR/EMV, reporta PQRSD |
| **Conductor** | Operador del bus | Recibe instrucciones por consola táctil, reporta novedades, activa botón de pánico en emergencias |
| **Centro de Control de Operaciones (CCO)** | Núcleo de supervisión | Monitorea flota en tiempo real, gestiona incidentes, valida recaudo, programa rutas y frecuencias |
| **Metro Sabanas S.A.S.** | Ente gestor | Recibe reportes operativos, audita compensación, reporta a autoridades, define política tarifaria |
| **Operadores de buses** | Prestadores del servicio | Reciben despacho, cumplen rutas/frecuencias, reciben compensación basada en datos ITS |
| **MinTransporte** | Regulador nacional | Recibe reportes periódicos de operación, valida cumplimiento normativo |
| **SuperTransporte** | Entidad de transporte | Recibe reportes de recaudo, pasajeros, incidentes; valida compensación tarifaria |
| **ANSV** | Seguridad vial | Recibe alertas de exceso de velocidad, incidentes, comportamiento de riesgo |
| **Bancos / Fintech** | Medios de pago | Procesan transacciones EMV, recargas digitales, compensación |

## 3.3 Escenarios Operacionales

### 3.3.1 Operación Normal

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    ESCENARIO: OPERACIÓN NORMAL                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  PASAJERO ──► Paradero ──► Aborda bus ──► Valida pago ──► Viaja          │
│       │           │              │             │              │            │
│       │           │              │             │              │            │
│       ▼           ▼              ▼             ▼              ▼            │
│  App móvil   Bus reporta     Consola     Validador      CCTV + Conteo      │
│  (ETA, rutas)  posición GPS   conductor  (Mifare/QR)   registran viaje     │
│                                                                             │
│  CCO recibe: ──► Posición de todos los buses (mapa en tiempo real)       │
│                ──► Estado de recaudo por ruta y bus                         │
│                ──► Ocupación estimada por bus                              │
│                ──► Cumplimiento de itinerarios                             │
│                ──► Alertas automáticas (velocidad, desvío)                │
│                                                                             │
│  Pasajero finaliza viaje ──► Validador registra salida ──► App notifica   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.3.2 Operación Degradada (pérdida de conectividad 4G)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              ESCENARIO: OPERACIÓN DEGRADADA (SIN 4G)                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Bus pierde conectividad celular ──► Sistema entra modo OFFLINE            │
│                                                                             │
│  Validador: ──► Procesa pagos con lista blanca local (última versión)      │
│             ──► Almacena transacciones en cola local (SQLite)               │
│             ──► Acepta Mifare/QR con saldo local                            │
│             ──► Rechaza EMV (requiere conectividad bancaria)               │
│                                                                             │
│  GPS: ──► Continúa registrando posiciones ──► Almacena localmente         │
│                                                                             │
│  CCTV: ──► Continúa grabando en DVR local (SSD ≥500GB)                     │
│                                                                             │
│  CCO: ──► Última posición conocida del bus permanece en mapa              │
│       ──► Alerta "Bus N sin conectividad > 5 minutos"                      │
│       ──► Operador contacta conductor por radio/WiFi si disponible         │
│                                                                             │
│  Al restaurar 4G: ──► Sincronización automática de transacciones           │
│                   ──► Sincronización de posiciones GPS retrasadas           │
│                   ──► Resolución de conflictos de saldo                      │
│                   ──► Alerta "Bus N conectado, N transacciones sincronizadas"│
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.3.3 Operación de Contingencia (incidente grave / botón de pánico)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│           ESCENARIO: CONTINGENCIA (BOTÓN DE PÁNICO ACTIVADO)                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Conductor o pasajero presiona botón de pánico                              │
│       │                                                                     │
│       ▼                                                                     │
│  Bus: ──► GPS registra posición exacta con timestamp                       │
│      ──► CCTV inicia grabación de emergencia (marca indeleble)             │
│      ──► Sistema abre comunicación bidireccional con CCO                  │
│      ──► Notificación push a supervisor de ruta                            │
│                                                                             │
│  CCO: ──► Alerta sonora/visual en mapa (rojo intermitente)                 │
│      ──► Operador visualiza cámara en vivo del bus afectado                │
│      ──► Comunicación voz con conductor                                    │
│      ──► Evalúa gravedad (accidente, robo, avería, desorden público)     │
│                                                                             │
│  Respuesta según tipo:                                                     │
│  • Accidente: ──► Ambulancia + BOMBEROS + POLICÍA + Grúa                   │
│  • Robo: ──► POLICÍA + Unidad de respuesta Metro Sabanas                  │
│  • Avería: ──► Grúa + Bus de reemplazo si disponible                        │
│  • Desorden: ──► POLICÍA + Supervisor de ruta                              │
│                                                                             │
│  Post-incidente: ──► Reporte automático a ANSV                             │
│                ──► Reporte a SuperTransporte                               │
│                ──► Actualización de estadísticas de seguridad               │
│                ──► Revisión de video por comité de seguridad               │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 3.4 Modos de Operación

| Modo | Descripción | Condición de entrada | Acciones |
|------|-------------|---------------------|----------|
| **Normal** | Operación estándar con todos los sistemas funcionales | Conectividad estable, servicios cloud disponibles | Monitoreo continuo, recaudo en tiempo real, reportes automáticos |
| **Degradado** | Funcionamiento con capacidad reducida | Pérdida parcial de conectividad, latencia alta | Modo offline en validadores, almacenamiento local, sincronización diferida |
| **Contingencia** | Respuesta a eventos críticos | Botón de pánico, accidente, falla masiva | Protocolos de emergencia, activación de cadenas de respuesta, evidencia preservada |
| **Mantenimiento** | Sistemas en mantenimiento programado | Ventanas definidas (typicamente 02:00-04:00) | Actualizaciones de firmware, calibración de equipos, limpieza de datos |

## 3.5 Niveles de Servicio y Métricas de Desempeño (KPIs Operacionales)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad del sistema de recaudo | ≥ 99,9% | Tiempo de funcionamiento del SRC |
| Latencia de validación de pago | < 300 ms | Tiempo entre acercar tarjeta y confirmación |
| Precisión de localización GPS | < 5 m (CEP 95%) | Comparación con referencia geodésica |
| Latencia de transmisión de posición | < 3 seg | Tiempo entre captura y visualización en CCO |
| Tiempo de respuesta a botón de pánico | < 10 seg | Desde activación hasta alerta en CCO |
| Fiabilidad de conteo de pasajeros | ≥ 97% | Comparación conteo manual en muestreo |
| Tiempo de retención de video | ≥ 30 días | Capacidad de almacenamiento y políticas |
| Precisión de predicción ETA | ± 2 min (90%) | Comparación ETA vs. tiempo real de llegada |
| Disponibilidad de app móvil | ≥ 99,5% | Tiempo de respuesta del backend |
| Tasa de resolución de PQRSD | < 24 horas | Tiempo entre recepción y cierre |

---

# 4. ARQUITECTURA ITS DE REFERENCIA

## 4.1 Visión Integrada de la Arquitectura

La arquitectura ITS del SETP Sincelejo se describe en cuatro niveles de abstracción que van desde la estrategia de negocio hasta los componentes físicos de campo. Esta división por niveles permite que cada stakeholder (directivos, arquitectos de software, ingenieros de campo, auditores) encuentre el nivel de detalle que requiere sin perder la coherencia sistémica.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ NIVEL 1: SERVICIOS ESTRATÉGICOS ITS                                         │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐                           │
│  │   SRC   │ │  SGCF   │ │   SIU   │ │   SST   │                           │
│  │ Recaudo │ │  Flota  │ │ Usuario │ │ Segur.  │                           │
│  └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘                           │
├───────┼───────────┼───────────┼───────────┼─────────────────────────────────┤
│ NIVEL 2: VISTA LÓGICA                                                       │
│  Software • Plataformas • APIs • Bases de datos • Microservicios            │
├───────┼───────────┼───────────┼───────────┼─────────────────────────────────┤
│ NIVEL 3: VISTA FÍSICA                                                       │
│  Buses • CCO • Dispositivos IoT • Servidores • Redes                        │
├───────┼───────────┼───────────┼───────────┼─────────────────────────────────┤
│ NIVEL 4: VISTA DE COMUNICACIONES                                            │
│  4G/5G • WiFi • VPN • Protocolos • Internet dedicado                        │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 4.2 Nivel 1: Servicios Estratégicos ITS

Este nivel representa la visión del negocio: qué hace el sistema para Metro Sabanas y para el ciudadano. Los cuatro servicios estratégicos (SRC, SGCF, SIU, SST) son los pilares sobre los que se construye todo el resto de la arquitectura.

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

- **SIU** consume datos de **SGCF** (posición de buses para predicción de llegada) y de **SRC** (saldo, tarifas).
- **SRC** consume datos de **SGCF** (validación de parada para tarifa zonal) y de **SST** (autenticación de transacciones).
- **SGCF** consume datos de **SRC** (carga de pasajeros para estimación de ocupación) y genera reportes para autoridades.
- **SST** protege todas las transacciones de **SRC** y autentica usuarios de **SIU**.

## 4.3 Nivel 2: Vista Lógica

### 4.3.1 Arquitectura de Software

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ CAPA DE PRESENTACIÓN / CANALES                                              │
│  App Móvil (iOS/Android) • Web Responsive • Dashboard CCO                  │
│  Call Center • WhatsApp Bot • API Gateway                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA DE API GATEWAY                                                         │
│  API REST (JSON/HTTPS) • API GraphQL • WebSocket (tiempo real)            │
│  MQTT (IoT buses) • Rate Limiting • Authentication (OAuth2)                │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA DE MICROSERVICIOS                                                      │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐           │
│  │  Tarifas│ │ Clearing│ │  GPS    │ │  Video  │ │  Alertas│           │
│  │  Engine │ │  Engine │ │ Service │ │ Service │ │  Engine │           │
│  └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘           │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐                          │
│  │  Conteo │ │  User   │ │  Auth   │ │  Report │                          │
│  │ Pasaj.  │ │  Mgmt   │ │  Service│ │  Engine │                          │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘                          │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA DE DATOS                                                               │
│  PostgreSQL (transaccional) • Redis (cache) • TimescaleDB (series)        │
│  MinIO/S3 (objetos) • ClickHouse (analytics) • Elasticsearch (logs)       │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA DE INFRAESTRUCTURA / ORQUESTACIÓN                                      │
│  Kubernetes / Docker Swarm • CI/CD • Monitoring (Prometheus/Grafana)      │
│  Log Aggregation (ELK/Loki) • Backup • Disaster Recovery                   │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.3.2 Plataformas SaaS vs. On-Premise

| Componente | Modelo Preferido | Justificación |
|------------|-----------------|---------------|
| SRC — Motor de tarifas y clearing | SaaS con instancia dedicada | Complejidad de certificaciones de pago; actualización continua de reglas |
| SGCF — GPS y control de flota | SaaS con edge local | Dependencia crítica de conectividad; necesidad de funcionamiento offline |
| SIU — App móvil y web | SaaS + desarrollo custom | Frontend propio para marca Metro Sabanas; backend puede ser SaaS |
| SST — HSM y criptografía | HSM cloud | FIPS 140-2 Nivel 3 sin inversión en hardware físico |
| BI y Analytics | SaaS o self-hosted | Baja flota = datasets manejables; herramientas open-source viables |

### 4.3.3 Bases de Datos y Persistencia

| Tipo de Dato | Tecnología | Justificación |
|--------------|-----------|---------------|
| Transacciones de recaudo | PostgreSQL + particionamiento | ACID compliance; auditoría; reportes regulatorios |
| Posiciones GPS (series temporales) | TimescaleDB o InfluxDB | Alta frecuencia de escritura; consultas de rango eficientes |
| Cache y sesiones | Redis | Baja latencia; TTL automático; manejo de tokens OAuth |
| Archivos de video | MinIO / S3 compatible | Object storage; lifecycle policies; replicación multi-zona |
| Logs y auditoría | Elasticsearch + Kibana | Full-text search; agregación; alertas de seguridad |
| Analytics y BI | ClickHouse o BigQuery | Columnar; compresión; consultas analíticas complejas |

## 4.4 Nivel 3: Vista Física

### 4.4.1 Distribución Geográfica de Componentes

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
                                │
                       ┌────────▼────────┐
                       │   34 BUSES      │
                       │ • GPS           │
                       │ • Validador     │
                       │ • CCTV          │
                       │ • WiFi          │
                       │ • Botón pánico  │
                       └─────────────────┘
```

### 4.4.2 Inventario de Componentes Físicos

#### Centro de Control de Operaciones (CCO)

| Categoría | Componente | Cantidad | Especificación Técnica |
|-----------|------------|----------|------------------------|
| **Video Wall** | Televisor industrial 55" UHD | 4 | Resolución 3840×2160; brillo ≥ 500 cd/m²; funcionamiento 24/7; entrada HDMI/DP; VESA 400×400; temperatura 0-40°C |
| **Video Wall** | Matriz de video (video wall controller) | 1 | 4 salidas HDMI; soporta 2×2; scaling; bezel compensation; control RS-232/LAN |
| **Estaciones de trabajo** | Computador doble pantalla (planeación + conciliación) | 2 | CPU ≥ Intel i7 / AMD Ryzen 7; RAM 32 GB; SSD 1 TB NVMe; 2 monitores 27" FHD; Windows 11 Pro / Ubuntu 22.04 LTS |
| **Estaciones de trabajo** | Computador inicialización tarjetas | 2 | CPU ≥ Intel i5; RAM 16 GB; SSD 512 GB; lector/escritor Mifare; impresora térmica; Windows 11 Pro |
| **Estaciones de trabajo** | Computador programación de rutas | 1 | CPU ≥ Intel i7; RAM 32 GB; SSD 1 TB; 2 monitores 27"; software GIS (QGIS / ArcGIS) |
| **Seguridad electrónica** | Antena inicialización SAM | 4 | Frecuencia 13.56 MHz; protocolo ISO 14443A/B; compatibilidad Mifare Classic/Desfire; interfaz USB |
| **Energía** | UPS online 5 KVA | 1 | Tecnología online doble conversión; potencia 5 KVA / 4.5 KW; autonomía ≥ 30 minutos; pantalla LCD; USB/RS-232 |
| **Redes** | Switch Gigabit administrable L3 | 1 | 24 puertos 10/100/1000 Mbps; 4 puertos SFP+; PoE+; VLAN; QoS; Spanning Tree; ACLs; SNMP; rack 19" |
| **Redes** | Rack 19" 42U | 1 | Gabinete de piso; puertas perforadas; ventilación; bandeja gestión de cables; PDU |
| **Mobiliario** | Puesto de trabajo ergonómico | 5 | Mesa ajustable en altura; silla ergonómica; soporte dual monitor; iluminación LED |
| **Seguridad física** | Cámara CCTV CCO | 4 | Domo IP 4MP; lente 2.8-12 mm; IR 30 m; H.265; PoE; montaje techo |
| **Seguridad física** | Control de acceso biométrico | 1 | Lector huella + tarjeta; capacidad ≥ 1000 usuarios; registro de eventos; TCP/IP; cerradura electromagnética |

## 4.5 Nivel 4: Vista de Comunicaciones

La Vista de Comunicaciones establece la infraestructura que garantiza la interconexión segura y confiable de todos los componentes del sistema. Este nivel asegura que el flujo de información entre el campo, el CCO y los sistemas externos sea continuo, permitiendo la coordinación de operaciones críticas y la toma de decisiones en tiempo real.

| Componente | Tecnología | Especificación |
|------------|------------|---------------|
| **Red troncal CCO-Cloud** | Fibra óptica / Internet dedicado | Mínimo 100 Mbps simétrico; SLA ≥ 99.5%; latencia < 50 ms |
| **Red buses-CCO** | 4G/5G QoS | Plan de datos corporativo; priorización de tráfico operativo; SIM dual (operadores diferentes) |
| **Respaldo satelital** | Iridium / Inmarsat (opcional) | Para zonas sin cobertura celular; mensajería corta; posición GPS |
| **WiFi buses** | 802.11ac/ax industrial | Dual band 2.4/5 GHz; portal cautivo; VLAN separada (operativo vs. pasajeros) |
| **Red CCO** | Ethernet Gigabit | Switches administrables L2/L3; VLAN por subsistema; PoE para cámaras |
| **VPN** | IPsec / WireGuard | Túneles seguros hacia cloud y proveedores SaaS; certificados X.509 |
| **Firewall** | UTM / Next-Gen Firewall | Stateful inspection; IDS/IPS; filtrado por aplicación; DLP; segmentación OT/IT |
| **Radio** | VHF/UHF o Push-to-Talk LTE | Comunicación voz entre CCO y conductores; respaldo ante falla celular |

---

# 5. CLASIFICACIÓN DE SERVICIOS ITS PARA SETP URBANO

## 5.1 Taxonomía Adaptada al Transporte Público Urbano

La Resolución 20203040034065 define una taxonomía de servicios ITS orientada a infraestructura vial y corredores. Para el SETP Sincelejo, se adapta esta taxonomía al dominio del **transporte público colectivo urbano sobre buses**, con una jerarquía que va desde el dominio estratégico hasta los componentes físicos de campo.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  DOMINIO: TRANSPORTE PÚBLICO URBANO COLECTIVO (TPUC)                       │
├─────────────────────────────────────────────────────────────────────────────┤
│  ÁREA DE SERVICIO: ITS-SETP-SINCELEJO                                      │
│  ├── Servicio Estratégico 1: Gestión de Recaudo y Tarificación (SRC)     │
│  │   ├── Subsistema: Validación de Medios de Pago                         │
│  │   ├── Función Técnica: Lectura Mifare / QR / EMV                      │
│  │   └── Componente de Campo: CC-SRC-01 Validador a bordo (bus)          │
│  ├── Servicio Estratégico 2: Gestión y Control de Flota (SGCF)         │
│  │   ├── Subsistema: Localización y Navegación                            │
│  │   ├── Función Técnica: GPS/GNSS tiempo real                            │
│  │   └── Componente de Campo: CC-SGCF-01 Antena GPS + módulo IoT          │
│  ├── Servicio Estratégico 3: Información al Usuario (SIU)                │
│  │   ├── Subsistema: Predicción de Tiempos de Llegada                     │
│  │   ├── Función Técnica: Algoritmo ETA basado en ML                      │
│  │   └── Componente de Campo: CC-SIU-01 Router WiFi + App móvil           │
│  └── Servicio Estratégico 4: Seguridad de Transacciones (SST)            │
│      ├── Subsistema: Criptografía y Autenticación                        │
│      ├── Función Técnica: Cifrado AES-256 / HSM                            │
│      └── Componente de Campo: CC-SST-01 SAM / HSM en validador           │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 5.2 Cadena de Valor Tecnológica

Para garantizar que el SETP Sincelejo opere bajo un estándar de excelencia técnica y operativa, la gestión de los ITS se estructura mediante una Cadena de Valor Tecnológica compuesta por cinco niveles de integración. Esta jerarquía no constituye una simple segmentación funcional, sino una ruta de trazabilidad y alineación sistémica, en la cual cada nivel superior fundamenta, condiciona y justifica la existencia del nivel inferior.

| Eslabón | Nivel | Descripción | Ejemplo SETP Sincelejo |
|---------|-------|-------------|------------------------|
| **E.1 Dominio** | Estratégico | Entorno de misión donde se definen objetivos de alto nivel | Transporte Público Urbano Ordenado, Seguro, Eficiente |
| **E.2 Servicio Estratégico** | Operacional | Interfaz de valor y beneficio final que perciben usuario y autoridad | Recaudo Centralizado, Control de Flota, Información al Usuario, Seguridad de Transacciones |
| **E.3 Función Técnica** | Lógico | ADN del sistema; procesos de software que dotan de capacidad analítica | Algoritmo de tarificación zonal, Motor de predicción ETA, Algoritmo de detección de incidentes |
| **E.4 Subsistema** | Sistémico | Puente de integración que coordina hardware, middleware y software | Subsistema de Validación, Subsistema de Rastreo, Subsistema de Videovigilancia |
| **E.5 Componente de Campo** | Físico | Elemento físico, electrónico desplegado en campo; ejecutor final de la visión | Validador en bus, GPS tracker, Cámara CCTV, Botón de pánico, Antena SAM |

**Nota de Unificación Técnica:** Para efectos de trazabilidad, se establece que los Niveles de Arquitectura (N1 al N4) detallados en el Capítulo 4 corresponden a los eslabones de la Cadena de Valor presentados en este capítulo. Esta simetría garantiza que la ingeniería del sistema (Vista Lógica) y la operación del SETP (CONOPS) compartan el mismo ADN funcional, facilitando la auditoría y la gobernanza del dato.

---

# 6. SERVICIOS ESTRATÉGICOS DETALLADOS

## 6.1 Servicio Estratégico 1: Gestión de Recaudo y Tarificación (SRC)

### 6.1.1 Propósito

Automatizar, centralizar, auditar y transparentar el recaudo de tarifas en todo el sistema, eliminando el manejo de efectivo en primera instancia y habilitando medios de pago modernos.

### 6.1.2 Subsistemas

| Subsistema | Descripción | Funciones Técnicas | Componentes de Campo |
|------------|-------------|--------------------|----------------------|
| Validación de Medios de Pago | Proceso de lectura, autenticación y aceptación de medios de pago | Lectura Mifare Classic/Desfire; lectura QR dinámico/estático; lectura EMV contactless; procesamiento offline | CC-SRC-01 Validador a bordo (bus); CC-SRC-02 Torniquete electromecánico; CC-SST-01 Antena SAM |
| Motor de Tarifas | Cálculo de valor a pagar según reglas de negocio | Tarifa zonal; tarifa temporal (pico/plano); fare capping (tope diario); descuentos (adulto mayor, estudiante, PCD) | Motor de reglas (cloud); base de datos de tarifas; API REST |
| Clearing y Compensación | Distribución automática de ingresos entre ente gestor y operadores | Conciliación transaccional; cálculo de compensación por km/pasajero; generación de órdenes de pago; reporte a SuperTransporte | Motor de reglas (BRMS); base de datos transaccional; integración bancaria (PSE) |
| Operación Offline | Continuidad de servicio ante falla de conectividad | Cola de transacciones local; sincronización diferida; resolución de conflictos; listas blancas/negras | Cache local en validador; base de datos SQLite; algoritmo de merge |

### 6.1.3 Flujo de Recaudo

```
PASAJERO ──► Acerca tarjeta Mifare a validador
       │
       ▼
  VALIDADOR ──► Lee saldo ──► Consulta tarifa (zona, hora, perfil)
       │
       ▼
  ¿Saldo ≥ Tarifa? ──► SÍ ──► Descuenta saldo ──► Emite beep verde + imprime ticket
       │                                              │
       │ NO                                           ▼
       │                                    Transacción se registra:
       ▼                                    • Localmente (SQLite)
  Rechaza pago ──► Beep rojo + mensaje      • En cache para sync
       │                                    • Con timestamp, ubicación GPS, ID bus
       ▼
  Pasajero puede: ──► Recargar (app/agente)  ──► Pagar con QR/EMV/efectivo
       │
       ▼
  CCO recibe transacción en tiempo real ──► Dashboard de recaudo actualizado
       │
       ▼
  Clearing nocturno: ──► Calcula compensación por operador ──► Genera orden de pago
```

### 6.1.4 KPIs del SRC

| KPI | Objetivo |
|-----|----------|
| Tiempo de validación | < 300 ms |
| Tasa de transacciones rechazadas | < 0,5% |
| Disponibilidad del sistema de recaudo | ≥ 99,9% |
| Tiempo de sincronización offline | < 5 minutos al restaurar conectividad |
| Precisión de conciliación | 100% (sin discrepancias no justificadas) |

## 6.2 Servicio Estratégico 2: Gestión y Control de Flota (SGCF)

### 6.2.1 Propósito

Conocer en tiempo real dónde está cada bus, si cumple su ruta y frecuencia, detectar desviaciones, alertar anomalías y generar evidencia operativa para la compensación y el reporte regulatorio.

### 6.2.2 Subsistemas

| Subsistema | Descripción | Funciones Técnicas | Componentes de Campo |
|------------|-------------|--------------------|----------------------|
| Localización y Navegación | Rastreo GPS/GNSS de la flota | Posicionamiento multiconstelación; geocercas por ruta; cálculo de desviación; predicción de llegada | CC-SGCF-01 Antena GPS/GNSS; módulo IoT; acelerómetro; giroscopio |
| Control de Itinerarios | Verificación de cumplimiento de rutas y frecuencias | Comparación ruta planificada vs. real; detección de saltos de parada; cálculo de holgura; alerta de desviación | Servidor de planificación; base de datos GIS; algoritmo de matching |
| Alertas Operativas | Detección y notificación de eventos anormales | Exceso de velocidad; fuera de ruta; botón de pánico; frenadas bruscas; tiempo de detención excesivo; puertas abiertas en movimiento | Motor de eventos (CEP); panel de alertas CCO; notificación push/WhatsApp |
| Videovigilancia | Grabación y transmisión de video a bordo | Codificación H.265; streaming en tiempo real; grabación continua 24/7; extracción por evento; almacenamiento 30 días | CC-SGCF-03 Cámaras 1080p; CC-SGCF-04 DVR SSD; switch PoE; NVR central |
| Conteo de Pasajeros | Cuantificación bidireccional de embarques y desembarques | Sensores ópticos / térmicos / 3D; fiabilidad ≥ 97%; conteo por puerta; agregación por ruta y franja horaria | CC-SGCF-02 Cámaras de conteo; procesador de video; algoritmo ML |

### 6.2.3 Flujo de Control de Flota

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    FLUJO DE CONTROL DE FLOTA                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  GPS/GNSS ──► Captura posición cada 1-3 segundos                           │
│       │                                                                     │
│       ▼                                                                     │
│  MÓDULO IoT ──► Agrega acelerómetro, giroscopio, odómetro                  │
│       │                                                                     │
│       ▼                                                                     │
│  TRANSMISIÓN 4G ──► Envia a plataforma cloud (MQTT/HTTPS)                 │
│       │                                                                     │
│       ▼                                                                     │
│  PLATAFORMA SGCF ──► Procesa posición ──► Compara con ruta planificada    │
│       │                              ──► Calcula ETA                        │
│       │                              ──► Detecta desviación               │
│       │                              ──► Evalúa cumplimiento frecuencia   │
│       │                                                                     │
│       ▼                                                                     │
│  ¿Evento anormal? ──► SÍ ──► Genera alerta ──► Notifica CCO               │
│       │                      (velocidad, desvío, pánico)                  │
│       │                                                                     │
│       NO                                                                    │
│       │                                                                     │
│       ▼                                                                     │
│  CCO visualiza: ──► Mapa con posición de 34 buses                         │
│                 ──► Estado de ruta (verde=cumple, rojo=desviado)          │
│                 ──► ETA a paraderos                                         │
│                 ──► Ocupación estimada (conteo pasajeros)                   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2.4 KPIs del SGCF

| KPI | Objetivo |
|-----|----------|
| Precisión de localización GPS | < 5 metros (CEP 95%) |
| Latencia de transmisión de posición | < 3 segundos |
| Fiabilidad de conteo de pasajeros | ≥ 97% |
| Tiempo de retención de video | ≥ 30 días |
| Tiempo de respuesta de alerta | < 10 segundos |
| Cumplimiento de rutas planificadas | ≥ 95% (por ruta/día) |

## 6.3 Servicio Estratégico 3: Información al Usuario (SIU)

### 6.3.1 Propósito

Reducir la incertidumbre del usuario del transporte público, empoderándolo con información de planificación, tiempos de espera, tarifas y estados de servicio en canales digitales y físicos accesibles.

### 6.3.2 Subsistemas

| Subsistema | Descripción | Funciones Técnicas | Componentes de Campo |
|------------|-------------|--------------------|----------------------|
| App Móvil | Aplicación nativa iOS y Android | Planificación de viaje; consulta de saldo; recarga; seguimiento de bus en tiempo real; notificaciones push; calificación | Backend mobile; API Gateway; push notifications; App Store / Play Store |
| Micrositio Web | Portal responsive de consulta | Rutas, paradas, horarios; mapa interactivo; consulta de saldo y movimientos; PQRSD; chatbot | Servidor web; CMS; CDN; SSL/TLS |
| Call Center / WhatsApp | Atención y canal de comunicación | PQRSD; reporte de novedades; consulta de saldo; bloqueo de tarjeta; emergencias | Plataforma de contact center; bot conversacional; WhatsApp Business API |
| WiFi en Buses | Conectividad gratuita para usuarios | Portal cautivo; autenticación ligera; ancho de banda compartido; contenido local cacheado | CC-SIU-01 Router WiFi industrial; access point; controlador de portal |

### 6.3.3 Flujo de Información al Usuario

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                  FLUJO DE INFORMACIÓN AL USUARIO                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  USUARIO abre App móvil                                                     │
│       │                                                                     │
│       ▼                                                                     │
│  App consulta: ──► Backend SIU ──► API Gateway                             │
│       │                              │                                      │
│       │                              ▼                                      │
│       │                       ┌─────────────┐                              │
│       │                       │  SGCF (GPS) │ ──► Posición buses           │
│       │                       │  SRC (Saldo)│ ──► Saldo tarjeta             │
│       │                       │  Tarifas    │ ──► Tarifa actual             │
│       │                       └─────────────┘                              │
│       │                                                                     │
│       ▼                                                                     │
│  App muestra: ──► Mapa con buses en tiempo real                            │
│              ──► Tiempo estimado de llegada (ETA)                          │
│              ──► Ruta seleccionada con paradas                             │
│              ──► Saldo y últimos movimientos                               │
│              ──► Alertas de servicio (demoras, desvíos)                    │
│                                                                             │
│  Cuando bus se acerca: ──► Notificación push "Su bus llega en 3 minutos"    │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.3.4 KPIs del SIU

| KPI | Objetivo |
|-----|----------|
| Precisión de predicción de llegada | ± 2 minutos en 90% de los casos |
| Disponibilidad de app | ≥ 99,5% |
| Tiempo de respuesta de micrositio | < 2 segundos |
| Cobertura WiFi en flota | 100% |
| Tasa de resolución de PQRSD | < 24 horas |

## 6.4 Servicio Estratégico 4: Seguridad de Transacciones (SST)

### 6.4.1 Propósito

Garantizar la integridad, confidencialidad, autenticidad y no repudio de cada transacción de pago, protegiendo los datos del usuario, los fondos del sistema y la reputación del ente gestor ante reguladores y bancos.

### 6.4.2 Subsistemas

| Subsistema | Descripción | Funciones Técnicas | Componentes de Campo |
|------------|-------------|--------------------|----------------------|
| Módulo de Seguridad (SAM/HSM) | Custodia de claves criptográficas | Generación de claves en hardware; almacenamiento seguro; operaciones criptográficas aceleradas; certificación FIPS 140-2 Nivel 3 | CC-SST-01 SAM embebida en validador; HSM cloud; HSM on-premise (opcional) |
| Cifrado de Comunicaciones | Protección de datos en tránsito | TLS 1.3; cifrado de capa de aplicación; perfect forward secrecy; certificados digitales gestionados | Certificados SSL; CA interna; renovación automática |
| Gestión de Claves | Ciclo de vida completo de claves | Generación, distribución, rotación, revocación, destrucción; escrow; separación de roles | Servidor de gestión de claves (KMS); políticas de rotación; auditoría |
| Autenticación y Autorización | Control de acceso a sistemas y datos | OAuth 2.0 + OpenID Connect; MFA; RBAC; ABAC | Identity Provider; servidor de tokens; políticas de acceso |
| Cumplimiento EMV | Alineación con estándar de pagos internacional | Certificación EMV Nivel 1 (hardware) y Nivel 2 (software); pruebas de laboratorio | Laboratorio EMV acreditado; toolkit de pruebas |

### 6.4.3 Flujo de Seguridad de Transacciones

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              FLUJO DE SEGURIDAD DE TRANSACCIONES                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  TARJETA MIFARE ──► Lectura por antena SAM                                  │
│       │                                                                     │
│       ▼                                                                     │
│  VALIDADOR ──► Autentica tarjeta (clave criptográfica SAM)                 │
│       │                                                                     │
│       ▼                                                                     │
│  ¿Tarjeta válida? ──► SÍ ──► Consulta saldo (local/cloud)                  │
│       │                           │                                       │
│       │                           ▼                                       │
│       │                   ¿Saldo suficiente? ──► SÍ ──► Descuenta           │
│       │                           │                    │                    │
│       │                           NO                   ▼                    │
│       │                           │              Genera criptograma          │
│       │                           │              (transacción firmada)      │
│       │                           │                                         │
│       ▼                           ▼                                         │
│  Rechazo                          Transmisión 4G ──► Cloud                 │
│                                      (TLS 1.3, certificado X.509)           │
│       │                                                                     │
│       ▼                                                                     │
│  CLOUD ──► Gateway ──► Microservicio Auth (OAuth2/JWT) ──► Valida token   │
│       │                                                                     │
│       ▼                                                                     │
│  Microservicio Transacción ──► Firma digital (HSM cloud)                   │
│                            ──► Registro inmutable (blockchain/ledger)      │
│                            ──► Actualización saldo                         │
│                                                                             │
│  EMV (tarjeta bancaria): ──► Contactless ──► Criptograma EMV                 │
│                          ──► Transmisión al adquirente (PSE)                │
│                          ──► Autorización bancaria                        │
│                          ──► Respuesta: APROBADO / RECHAZADO                │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.4.4 KPIs del SST

| KPI | Objetivo |
|-----|----------|
| Cumplimiento PCI DSS | Nivel 1 (si procesa tarjetas de crédito) |
| Cumplimiento ISO 27001 | Certificado activo |
| Cifrado de datos en tránsito | 100% TLS 1.3 |
| Cifrado de datos en reposo | AES-256 |
| Tiempo de respuesta de autenticación | < 500 ms |
| Incidentes de seguridad reportados | 0 críticos / año |

---

# 7. EQUIPAMIENTO A BORDO DE BUSES

## 7.1 Arquitectura de Equipamiento por Bus

Cada uno de los 34 buses del SETP Sincelejo lleva a bordo un conjunto integrado de dispositivos que conforman el "nodo ITS móvil". Todos los dispositivos se interconectan mediante una red local Ethernet/WiFi y comparten una conexión 4G/5G hacia el CCO y la nube.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│              DIAGRAMA DE EQUIPAMIENTO A BORDO (por bus)                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│   ┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐    │
│   │  CC-SRC-01      │     │  CC-SGCF-01     │     │  CC-SIU-01      │    │
│   │  VALIDADOR      │     │  GPS/GNSS       │     │  ROUTER WiFi    │    │
│   │  (Mifare/QR/EMV)│     │  + IoT          │     │  4G/5G          │    │
│   └────────┬────────┘     └────────┬────────┘     └────────┬────────┘    │
│            │                       │                       │              │
│            └───────────────────────┼───────────────────────┘              │
│                                    │                                      │
│                           ┌────────▼────────┐                            │
│                           │   RED LOCAL BUS   │                            │
│                           │  Ethernet/WiFi    │                            │
│                           └────────┬────────┘                            │
│                                    │                                      │
│       ┌────────────────────────────┼────────────────────────────┐        │
│       │                            │                            │        │
│       ▼                            ▼                            ▼        │
│  ┌─────────┐                 ┌─────────┐                 ┌─────────┐    │
│  │CC-SGCF-03│                │CC-SGCF-02│                │CC-SGCF-04│   │
│  │ CCTV    │                │ CONTEO  │                │  DVR    │   │
│  │ (2 cams)│                │ PASAJ.  │                │  SSD    │   │
│  └─────────┘                └─────────┘                └─────────┘   │
│                                                                             │
│       ┌─────────┐         ┌─────────┐         ┌─────────┐                   │
│       │CC-SGCF-05│        │CC-SST-01│        │CC-SRC-02│                  │
│       │ CONSOLA │        │ BOTÓN   │        │TORNIQUETE│                  │
│       │CONDUCTOR│        │ PÁNICO  │        │ELECTROMEC│                  │
│       └─────────┘        └─────────┘        └─────────┘                   │
│                                                                             │
│   Alimentación: 12V/24V DC con conversor desde alternador/bus eléctrico   │
│   Respaldo: Batería auxiliar 12V 20Ah (autonomía ≥ 2 horas)              │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 7.2 Inventario de Equipamiento por Bus (34 unidades)

| Código | Componente | Cantidad por bus | Total (34 buses) |
|--------|------------|-----------------|------------------|
| CC-SRC-01 | Validador/Procesador de transacciones | 2 (puerta delantera + trasera) | 68 |
| CC-SRC-02 | Torniquete electromecánico unidireccional | 2 | 68 |
| CC-SGCF-01 | Rastreador GPS/GNSS + módulo IoT | 1 | 34 |
| CC-SGCF-02 | Cámaras conteo pasajeros | 2 (por puerta) | 68 |
| CC-SGCF-03 | Cámaras videovigilancia CCTV | 2 (interior) | 68 |
| CC-SGCF-04 | Grabador DVR/NVR SSD ≥500GB | 1 | 34 |
| CC-SGCF-05 | Consola/tablet conductor rugerizada 7" | 1 | 34 |
| CC-SST-01 | Botón de pánico (conductor + pasajeros) | 2 | 68 |
| CC-SIU-01 | Router WiFi industrial 4G/5G | 1 | 34 |
| CC-COM-01 | Antena GPS/GNSS externa | 1 | 34 |
| CC-COM-02 | Cableado y accesorios (kit por bus) | 1 | 34 |

---

# 8. CENTRO DE CONTROL DE OPERACIONES (CCO)

## 8.1 Ubicación y Diseño General

**Ubicación:** Oficinas administrativas de Metro Sabanas S.A.S. en Sincelejo, Sucre.

El CCO constituye el núcleo neurálgico del sistema ITS. Es el espacio físico desde donde un equipo de operadores supervisa, controla y coordina toda la operación del SETP. El diseño del CCO sigue estándares de centros de control de transporte público, adaptados a la escala de 34 buses y 5 rutas.

## 8.2 Distribución Física del CCO

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    PLANTA DEL CCO — SETP SINCELEJO                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌────────────────────────────────────────────────────────────────────────┐│
│  │                           VIDEO WALL                                  ││
│  │  ┌────────┐  ┌────────┐  ┌────────┐  ┌────────┐                       ││
│  │  │ TV 55" │  │ TV 55" │  │ TV 55" │  │ TV 55" │                       ││
│  │  │ Mapa   │  │ Alertas│  │Recaudo │  │ CCTV   │                       ││
│  │  │Flota   │  │Activas │  │Tiempo R│  │Directo│                       ││
│  │  └────────┘  └────────┘  └────────┘  └────────┘                       ││
│  └────────────────────────────────────────────────────────────────────────┘│
│                                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐   │
│  │  Puesto 1   │  │  Puesto 2   │  │  Puesto 3   │  │  Puesto 4   │   │
│  │ Supervisor  │  │ Planeación  │  │ Conciliación│  │  Soporte    │   │
│  │   General   │  │  Rutas      │  │  Recaudo    │  │  Técnico    │   │
│  │  2×27" FHD  │  │  2×27" FHD  │  │  2×27" FHD  │  │  2×27" FHD  │   │
│  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘   │
│                                                                             │
│  ┌────────────────────────────────────────────────────────────────────────┐│
│  │  Puesto 5 — Inicialización de Tarjetas (2 PC + impresora térmica)     ││
│  └────────────────────────────────────────────────────────────────────────┘│
│                                                                             │
│  ┌────────┐  ┌─────────────────┐  ┌─────────────────┐                     │
│  │ RACK   │  │  Sala reuniones  │  │  Servicios      │                     │
│  │19" 42U │  │  (6 personas)    │  │  (baños, cocina)│                     │
│  │Switch  │  │                  │  │                 │                     │
│  │UPS 5KVA│  │                  │  │                 │                     │
│  │Servid.│  │                  │  │                 │                     │
│  └────────┘  └─────────────────┘  └─────────────────┘                     │
│                                                                             │
│  Acceso biométrico + CCTV 4 cámaras domo IP                                │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 8.3 Inventario de Componentes del CCO

| Código | Componente | Cantidad | Especificación Técnica |
|--------|------------|----------|------------------------|
| CC-CCO-01 | Televisor industrial 55" UHD | 4 | Resolución 3840×2160; brillo ≥ 500 cd/m²; 24/7; HDMI/DP; temperatura 0-40°C |
| CC-CCO-02 | Matriz de video controller | 1 | 4 salidas HDMI; 2×2 layout; scaling; bezel compensation; RS-232/LAN |
| CC-CCO-03 | Computador doble pantalla (planeación + conciliación) | 2 | CPU ≥ i7/Ryzen 7; RAM 32 GB; SSD 1 TB NVMe; 2 monitores 27" FHD; Windows 11 Pro / Ubuntu 22.04 |
| CC-CCO-04 | Computador inicialización tarjetas | 2 | CPU ≥ i5; RAM 16 GB; SSD 512 GB; lector/escritor Mifare; impresora térmica; Windows 11 Pro |
| CC-CCO-05 | Computador programación de rutas | 1 | CPU ≥ i7; RAM 32 GB; SSD 1 TB; 2 monitores 27"; software GIS (QGIS / ArcGIS) |
| CC-CCO-06 | Antena inicialización SAM | 4 | Frecuencia 13.56 MHz; ISO 14443A/B; Mifare Classic/Desfire; USB |
| CC-CCO-07 | UPS online 5 KVA | 1 | Online doble conversión; 5 KVA / 4.5 KW; autonomía ≥ 30 min; USB/RS-232 |
| CC-CCO-08 | Switch Gigabit administrable L3 | 1 | 24 puertos 10/100/1000; 4 SFP+; PoE+; VLAN; QoS; Spanning Tree; ACLs; SNMP; rack 19" |
| CC-CCO-09 | Rack 19" 42U | 1 | Gabinete de piso; puertas perforadas; ventilación; bandeja gestión cables; PDU |
| CC-CCO-10 | Puesto de trabajo ergonómico | 5 | Mesa ajustable altura; silla ergonómica; soporte dual monitor; iluminación LED |
| CC-CCO-11 | Cámara CCTV CCO | 4 | Domo IP 4MP; lente 2.8-12 mm; IR 30 m; H.265; PoE; montaje techo |
| CC-CCO-12 | Control acceso biométrico | 1 | Lector huella + tarjeta; capacidad ≥ 1000 usuarios; registro eventos; TCP/IP; cerradura electromagnética |

## 8.4 Software del CCO

| Sistema | Función | Tipo | Justificación |
|---------|---------|------|---------------|
| Plataforma SRC | Recaudo, clearing, compensación | SaaS con instancia dedicada | Complejidad de certificaciones de pago |
| Plataforma SGCF | GPS, control flota, alertas | SaaS con edge local | Dependencia crítica de conectividad; offline |
| Plataforma SIU | App móvil, web, predictor | SaaS + desarrollo custom | Frontend propio marca Metro Sabanas |
| Plataforma SST | Seguridad, SAM, HSM | HSM cloud | FIPS 140-2 Nivel 3 sin hardware físico |
| Business Intelligence | Dashboards, reportes | SaaS o self-hosted | Datasets manejables; open-source viable |
| NVR Central | Videovigilancia CCO + buses | On-premise o cloud | 30 días retención; acceso rápido |

## 8.5 Conectividad del CCO

| Enlace | Tecnología | Especificación |
|--------|------------|---------------|
| CCO → Cloud | Internet dedicado | 100 Mbps simétrico; SLA ≥ 99.5%; redundancia física |
| CCO → Buses | 4G/5G QoS | Plan corporativo; SIM dual; APN privado |
| CCO interno | Ethernet Gigabit | VLAN por subsistema; PoE; segmentación OT/IT |
| Respaldo | Radio VHF/PTT-LTE | Comunicación voz con conductores; respaldo ante falla celular |

---

# 9. FICHAS TÉCNICAS DE COMPONENTES DE CAMPO

Este capítulo presenta la especificación detallada de cada componente de campo (CC) del sistema ITS del SETP Sincelejo, siguiendo la metodología y estructura del APP Chía-Girardot. Cada ficha técnica incluye:

1. **Identificación**: Código, nombre, cantidad, subsistema asociado
2. **Descripción Funcional / Técnica**: Qué hace el componente, cómo se implementa, integraciones con otros subsistemas
3. **Justificación Estratégica**: Por qué se justifica la inversión, beneficios cuantificados, alineación con normativa
4. **Especificación Técnica (ET)**: Parámetros de hardware, software, conectividad, energía, ambientales
5. **Requerimientos Funcionales (RF)**: Qué debe hacer el componente
6. **Requisitos No Funcionales (RNF)**: Cómo debe hacerlo (rendimiento, disponibilidad, seguridad, ambientales)
7. **Indicadores Clave de Rendimiento (KPIs)**: Métricas de desempeño medibles

---

## 9.1 CC-SRC-01: Validador / Procesador de Transacciones

El Validador / Procesador de Transacciones es el componente de campo central del Sistema de Recaudo Centralizado (SRC). Instalado estratégicamente en las puertas de acceso de cada bus (puerta delantera y puerta trasera en configuración estándar), este dispositivo constituye la interfaz física entre el pasajero y el sistema de pagos del SETP Sincelejo.

El validador integra múltiples tecnologías de lectura en una única unidad robusta diseñada para operación continua en ambientes de transporte público. La lectura Mifare (ISO 14443A/B, tipos Classic y DESFire) habilita el uso de tarjetas prepago propias del sistema. La lectura de códigos QR (dinámicos y estáticos) permite pagos desde aplicaciones móviles y cupones digitales. La lectura EMV contactless (ISO 14443, Visa payWave, Mastercard Contactless) habilita pagos directos con tarjetas bancarias sin necesidad de recarga previa.

La unidad incluye un procesador integrado con sistema operativo embebido (Linux o Android industrial), capacidad de procesamiento local de transacciones, almacenamiento local de colas de transacciones en modo offline (SQLite o similar), conectividad Ethernet y WiFi para integración con la red del bus, y un modem 4G/5G opcional para comunicación directa. La pantalla a color de 7 pulgadas con interfaz táctil resistiva (operable con guantes) proporciona retroalimentación visual al pasajero: saldo disponible, tarifa descontada, confirmación de pago, mensajes de error (saldo insuficiente, tarjeta bloqueada).

El validador se integra con el subsistema de seguridad transaccional (SST) mediante un módulo SAM (Secure Access Module) embebido, que custodia las claves criptográficas para autenticación de tarjetas Mifare y generación de criptogramas EMV. Cada transacción es firmada digitalmente con el SAM antes de ser transmitida, garantizando la integridad y no repudio del dato.

La arquitectura de operación offline es crítica para el SETP Sincelejo, dado que la cobertura celular en algunas zonas de la ciudad puede ser irregular. El validador mantiene una lista blanca local con los últimos N días de saldos validados, permitiendo procesar pagos incluso sin conectividad. Al restaurar la comunicación, sincroniza la cola de transacciones pendientes con la nube, resolviendo conflictos de saldo mediante algoritmo de merge con prioridad a la transacción más reciente.

### Justificación Estratégica

La implementación de validadores multiprotocolo en cada bus es fundamental para la modernización del recaudo en el SETP Sincelejo. El sistema actual de recaudo en efectivo presenta múltiples problemas documentados en transporte público colombiano: pérdida por manejo de dinero en efectivo (estimada entre 15% y 30% de la recaudación total por fugas, errores de cambio y manejo informal), lentitud en el embarque (un pasajero pagando con billete pequeño toma 5-10 segundos vs. <300 ms con tarjeta), y ausencia total de trazabilidad operativa.

La experiencia de sistemas de transporte público con recaudo electrónico en Colombia (TransMilenio, MIO Cali, Metro de Medellín) demuestra que la tasa de recaudo efectiva aumenta entre 20% y 40% tras la implementación de validadores centralizados, principalmente por eliminación de fugas y mejor control de fraude. Para el SETP Sincelejo, con una demanda de 7.670 pasajeros/día y tarifa estimada de $2.800 COP, el recaudo diario potencial es de ~$21,5 millones COP. Una mejora del 25% en recaudo efectivo representa ~$5,4 millones COP diarios, o ~$1.970 millones COP anuales — cifra que justifica ampliamente la inversión en validadores.

Adicionalmente, el validador como punto de recolección de datos genera información valiosa para la planificación: horarios de mayor demanda por ruta, tiempos de embarque por parada, perfiles de uso por tipo de pasajero (adulto, estudiante, adulto mayor, PCD), y patrones de recarga. Esta información, históricamente inexistente en transporte público informal, habilita la optimización de frecuencias, el diseño de tarifas diferenciadas, y la planificación de expansiones futuras.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SRC-01 |
| **Nombre** | Validador / Procesador de Transacciones |
| **Subsistema** | SRC — Validación de Medios de Pago |
| **Cantidad** | 2 por bus (delantera + trasera) × 34 buses = 68 unidades |
| **Procesador** | ARM Cortex-A53 quad-core ≥ 1.5 GHz o equivalente |
| **RAM** | ≥ 2 GB LPDDR4 |
| **Almacenamiento** | ≥ 32 GB eMMC + ranura microSD |
| **Pantalla** | TFT LCD 7", resolución ≥ 1024×600, táctil resistiva, retroiluminación LED ajustable |
| **Lectores integrados** | Mifare Classic/Desfire (ISO 14443A/B); QR 1D/2D (Code 128, QR Code, Data Matrix); EMV contactless (ISO 14443, Visa payWave, Mastercard Contactless) |
| **SAM** | 4 ranuras SAM (Secure Access Module) ISO 7816; compatibles con Mifare SAM AV3 o equivalente |
| **Conectividad** | Ethernet 10/100 Mbps; WiFi 802.11 b/g/n; Bluetooth 4.2; opcional modem 4G LTE Cat.4 |
| **GPS** | Módulo GPS/GNSS multiconstelación (GPS, GLONASS, Galileo) integrado; precisión < 5 m CEP 95% |
| **Impresora** | Impresora térmica integrada 58 mm; velocidad ≥ 50 mm/s; cortador automático |
| **Puertos** | 2×USB 2.0; 1×RS-232; 1×Ethernet RJ-45; 1×SIM (4G) |
| **Alimentación** | 12V DC ± 10%; consumo ≤ 25 W en operación normal; ≤ 10 W standby |
| **Temperatura operación** | -10°C a +55°C |
| **Humedad** | 5% a 95% RH (sin condensación) |
| **Protección** | IP54 (frontal); IK08 (resistencia impacto) |
| **Certificaciones** | EMV Nivel 1 (hardware); CE; FCC; certificación eléctrica RETIE (Colombia) |
| **Dimensiones** | ≈ 220 × 180 × 120 mm (sin antenas) |
| **Peso** | ≤ 2.5 kg |
| **Montaje** | Pie de mesa o montaje en barra vertical; ángulo ajustable 15-45° |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SRC-01-01 | Leer tarjetas Mifare Classic y DESFire EV1/EV2/EV3 | Obligatorio |
| RF-SRC-01-02 | Leer códigos QR dinámicos (app móvil) y estáticos (cupones) | Obligatorio |
| RF-SRC-01-03 | Procesar pagos EMV contactless (Visa, Mastercard) | Deseable |
| RF-SRC-01-04 | Mostrar saldo actual y tarifa descontada en pantalla | Obligatorio |
| RF-SRC-01-05 | Imprimir ticket con código QR de transacción | Obligatorio |
| RF-SRC-01-06 | Operar en modo offline con lista blanca de saldos | Obligatorio |
| RF-SRC-01-07 | Sincronizar transacciones pendientes al restaurar conectividad | Obligatorio |
| RF-SRC-01-08 | Registrar timestamp, ubicación GPS, ID bus en cada transacción | Obligatorio |
| RF-SRC-01-09 | Validar tarjetas bloqueadas o listas negras | Obligatorio |
| RF-SRC-01-10 | Aplicar descuentos automáticos (adulto mayor, estudiante, PCD) | Obligatorio |
| RF-SRC-01-11 | Soportar tarifa zonal (si aplica en futuro) | Deseable |
| RF-SRC-01-12 | Emitir señales acústicas (beep) diferenciadas por resultado | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SRC-01-01 | Tiempo de respuesta de validación | < 300 ms (Mifare); < 500 ms (QR); < 2000 ms (EMV) |
| RNF-SRC-01-02 | Disponibilidad del validador | ≥ 99.5% (excluyendo mantenimiento programado) |
| RNF-SRC-01-03 | MTBF (Mean Time Between Failures) | ≥ 50.000 horas |
| RNF-SRC-01-04 | MTTR (Mean Time To Repair) | ≤ 2 horas (swap de unidad) |
| RNF-SRC-01-05 | Ciclos de lectura Mifare | ≥ 10.000.000 |
| RNF-SRC-01-06 | Cifrado de comunicaciones | TLS 1.3; certificados X.509 |
| RNF-SRC-01-07 | Almacenamiento offline | ≥ 10.000 transacciones en cola local |
| RNF-SRC-01-08 | Autonomía sin alimentación externa | ≥ 30 minutos (con batería auxiliar bus) |
| RNF-SRC-01-09 | Resistencia a vibración | IEC 60068-2-6; 5-500 Hz; 2 G |
| RNF-SRC-01-10 | Resistencia a polvo/salpicaduras | IP54 frontal; IK08 impacto |
| RNF-SRC-01-11 | Compatibilidad con retroiluminación solar | Visibilidad pantalla ≥ 500 cd/m² bajo luz directa |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad operativa | ≥ 99.5% | Tiempo de funcionamiento / tiempo total |
| Tiempo de validación Mifare | < 300 ms | Medición promedio en 1000 transacciones |
| Tasa de lecturas rechazadas | < 0.5% | Transacciones fallidas / total intentos |
| Capacidad de cola offline | ≥ 10.000 tx | Transacciones almacenadas sin conectividad |
| Tiempo de sincronización offline | < 5 min | Desde restauración de conectividad hasta sync completa |
| Precisión de timestamp | ± 1 segundo | Comparación con servidor NTP |
| Precisión de posición GPS en transacción | < 10 m | CEP 95% |

---

## 9.2 CC-SRC-02: Torniquete Electromecánico Unidireccional

El Torniquete Electromecánico Unidireccional es el componente de control de acceso físico al bus. Instalado junto al validador en cada puerta de acceso, permite el paso del pasajero únicamente tras la validación exitosa del pago. El torniquete opera mediante un mecanismo de brazo basculante o barrera oscilante accionado por motor paso a paso o servo motor DC brushless.

El control del torniquete está integrado electrónicamente con el validador: cuando el validador complète una transacción válida, envía una señal de liberación al controlador del torniquete por cableado directo (señal de contacto seco o comunicación serial RS-485/Modbus). El torniquete abre el paso por un tiempo configurable (tipicamente 3-5 segundos), permitiendo el paso de un pasajero. Sensores de proximidad infrarrojos o detectores de masa detectan el paso del pasajero y confirman el cierre seguro del mecanismo.

En caso de emergencia (activación del botón de pánico, orden del conductor, falla de alimentación), el torniquete puede liberarse automáticamente para permitir la evacuación rápida del bus. Esta función de "fail-safe" es crítica para la seguridad pasajera y está regulada por normas de evacuación de vehículos de transporte público.

### Justificación Estratégica

El torniquete es el componente que materializa el control de acceso basado en pago previo, eliminando la figura del cobrador a bordo y habilitando la operación sin personal de a bordo dedicado al recaudo. Sin un mecanismo físico de control de acceso, el sistema de recaudo electrónico sería fácilmente evadido: pasajeros podrían abordar sin pagar simplemente ignorando el validador.

La experiencia de sistemas BRT y metro en Colombia demuestra que la combinación validador + torniquete reduce la evasión a menos del 3%, comparado con 20-40% en sistemas sin control físico de acceso. Para el SETP Sincelejo, donde la cultura de pago en transporte informal es débil, el torniquete es un componente de alta prioridad para garantizar la viabilidad financiera del sistema.

Adicionalmente, el torniquete proporciona datos adicionales de control: sensores de paso permiten correlacionar transacciones con pasajeros físicos, detectando intentos de fraude (múltiples transacciones sin paso, o paso sin transacción que indica evasión o falla del validador).

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SRC-02 |
| **Nombre** | Torniquete Electromecánico Unidireccional |
| **Subsistema** | SRC — Control de Acceso Físico |
| **Cantidad** | 2 por bus (delantera + trasera) × 34 buses = 68 unidades |
| **Tipo** | Brazo basculante de acero inoxidable 304 o aluminio anodizado |
| **Mecanismo** | Motor paso a paso NEMA 23 o servo DC brushless; engranaje reductor ≥ 50:1 |
| **Ángulo de operación** | 0° (bloqueo) → 90° (liberación) en ≤ 0.5 segundos |
| **Ancho de paso** | ≥ 550 mm (accesible PMR) |
| **Control** | Controlador integrado con I/O digital; señal de liberación por contacto seco o RS-485/Modbus |
| **Sensores** | 2× sensores IR de proximidad (detección de pasajero); 1× sensor fin de carrera mecánico |
| **Seguridad** | Liberación automática ante falla de alimentación (fail-safe); liberación remota por conductor; liberación por botón de pánico |
| **Alimentación** | 24V DC; consumo ≤ 30 W en operación; ≤ 5 W standby |
| **Temperatura operación** | -10°C a +55°C |
| **Humedad** | 5% a 95% RH |
| **Protección** | IP53; acabado resistente a UV y corrosión atmosférica (Sincelejo, costa Caribe) |
| **Certificaciones** | CE; certificación mecánica y eléctrica RETIE (Colombia) |
| **Dimensiones** | ≈ 1200 × 300 × 1000 mm (ancho × profundidad × altura) |
| **Peso** | ≤ 25 kg |
| **Montaje** | Piso del bus; pernos de anclaje M10; amortiguadores de vibración |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SRC-02-01 | Liberar paso tras señal de validador (transacción exitosa) | Obligatorio |
| RF-SRC-02-02 | Detectar paso de pasajero y cerrar tras paso confirmado | Obligatorio |
| RF-SRC-02-03 | Liberación automática ante falla de alimentación (fail-safe) | Obligatorio |
| RF-SRC-02-04 | Liberación remota por conductor desde consola | Obligatorio |
| RF-SRC-02-05 | Liberación automática ante activación de botón de pánico | Obligatorio |
| RF-SRC-02-06 | Indicación visual (LED) de estado: rojo=bloqueado, verde=liberado | Obligatorio |
| RF-SRC-02-07 | Indicación acústica de cierre inminente (alerta sonora) | Deseable |
| RF-SRC-02-08 | Conteo de pasos independiente del validador | Deseable |
| RF-SRC-02-09 | Bloqueo de paso inverso (antiretorno) | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SRC-02-01 | Tiempo de respuesta (señal → liberación) | < 500 ms |
| RNF-SRC-02-02 | Tiempo de cierre tras paso detectado | < 3 segundos |
| RNF-SRC-02-03 | MTBF | ≥ 500.000 ciclos |
| RNF-SRC-02-04 | Fuerza de retención (resistencia a empuje) | ≥ 150 N |
| RNF-SRC-02-05 | Nivel sonoro | < 50 dB(A) en operación |
| RNF-SRC-02-06 | Resistencia a impacto (brazo) | ≥ 100 J |
| RNF-SRC-02-07 | Accesibilidad PMR (Personas con Movilidad Reducida) | Ancho ≥ 550 mm; altura brazo ≤ 900 mm |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad operativa | ≥ 99.0% | Tiempo funcionamiento / total |
| Tasa de falla mecánica | < 0.1% | Ciclos fallidos / total ciclos |
| Tiempo de respuesta | < 500 ms | Medición promedio |
| Coincidencia validador-torniquete | ≥ 98% | Transacciones con paso confirmado / total transacciones |

---

## 9.3 CC-SGCF-01: Rastreador GPS/GNSS + Módulo IoT

El Rastreador GPS/GNSS con Módulo IoT es el componente de campo fundamental del Sistema de Gestión y Control de Flota (SGCF). Instalado en la cabina de cada bus (típicamente bajo el tablero o en compartimento técnico), este dispositivo captura la posición geográfica del vehículo en tiempo real y la transmite al CCO mediante redes celulares 4G/5G.

El dispositivo integra un receptor GPS/GNSS multiconstelación (GPS, GLONASS, Galileo, BeiDou) con precisión submétrica en modo diferencial (si se habilita RTK o corrección SBAS/WAAS/EGNOS). Adicionalmente, incluye sensores inerciales (acelerómetro de 3 ejes, giroscopio) que permiten detectar eventos de conducción: aceleraciones bruscas, frenadas intensas, virajes agresivos, y vibración anómala.

El módulo IoT integra un procesador ARM, sistema operativo Linux embebido, interfaz Ethernet para conexión a la red del bus, interfaz CAN Bus para lectura de datos del vehículo (odómetro, velocidad, RPM, temperatura motor, nivel de combustible — cuando el bus lo permita mediante interfaz OBD-II o J1939), y salidas digitales para activación de alarmas o integración con otros sistemas.

La transmisión de datos se realiza mediante protocolo MQTT sobre TLS 1.3, con frecuencia configurable (tipicamente 1-3 segundos en operación normal, 10 segundos en ruta estable, inmediato ante evento de alerta). El almacenamiento local (flash ≥ 8 GB) permite retener datos durante períodos de pérdida de conectividad, con sincronización automática al restaurarse.

La geocerca es una función crítica: el operador del CCO define las rutas planificadas como polígonos geográficos. Si el bus sale del polígono por más de una distancia umbral (ej. 100 metros) o por más de un tiempo umbral (ej. 2 minutos), el sistema genera automáticamente una alerta de "fuera de ruta" que notifica al supervisor de la ruta y al conductor mediante la consola en cabina.

### Justificación Estratégica

El rastreo GPS/GNSS de la flota es la base de toda la inteligencia operativa del SGCF. Sin conocimiento de la posición de cada bus en tiempo real, es imposible: (1) Informar al usuario sobre tiempos de llegada; (2) Verificar que los operadores cumplan las rutas y frecuencias planificadas; (3) Detectar desviaciones o uso indebido de los buses; (4) Coordinar respuesta a incidentes; (5) Generar reportes regulatorios de kilómetros recorridos y tiempos de operación.

El valor del rastreo va más allá de la supervisión: los datos históricos de posición permiten analizar patrones de velocidad, identificar cuellos de botella en la red vial de Sincelejo, evaluar el cumplimiento de tiempos de ciclo por ruta, y fundamentar decisiones de ajuste de frecuencias o reconfiguración de rutas. En sistemas de transporte público donde la compensación a operadores se basa en kilómetros recorridos (como es típico en SETP con tarifa técnica + FEST), el GPS es la fuente de verdad para la liquidación — reemplazando los odómetros mecánicos manipulables o los registros manuales de los operadores.

La detección de eventos de conducción (frenadas bruscas, aceleraciones agresivas) habilita programas de coaching para conductores, reduciendo el desgaste mecánico de los buses (frenos, suspensión, transmisión) y mejorando la seguridad vial. Estudios en flotas comerciales demuestran reducciones del 15-25% en costos de mantenimiento y del 20-30% en accidentes tras la implementación de monitoreo de comportamiento de conducción.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SGCF-01 |
| **Nombre** | Rastreador GPS/GNSS + Módulo IoT |
| **Subsistema** | SGCF — Localización y Navegación |
| **Cantidad** | 1 por bus × 34 buses = 34 unidades |
| **Receptor GNSS** | Multiconstelación: GPS L1/L2, GLONASS L1/L2, Galileo E1/E5a, BeiDou B1/B2a; 72 canales; precisión < 5 m CEP 95% (standalone); < 2 m con SBAS; < 1 m con RTK |
| **Antena GNSS** | Activa externa; ganancia ≥ 28 dB; cable RG-174 3 m; conector SMA |
| **Procesador** | ARM Cortex-A7 dual-core ≥ 800 MHz |
| **RAM** | ≥ 512 MB DDR3 |
| **Almacenamiento** | ≥ 8 GB flash eMMC para logs y buffer offline |
| **Sensores inerciales** | Acelerómetro 3 ejes ± 4 g; giroscopio 3 ejes ± 250 °/s; opcional magnetómetro |
| **Interfaz vehículo** | CAN Bus (ISO 11898); J1939 (camiones/buses); OBD-II (ISO 15765-4) |
| **Conectividad** | Modem 4G LTE Cat.4 (LTE-FDD/LTE-TDD); 3G/2G fallback; SIM dual; SMS; data |
| **Protocolos** | MQTT sobre TLS 1.3; HTTP/HTTPS REST; NMEA 0183/2000; J1939; Modbus TCP/RTU |
| **Salidas digitales** | 2× DO (Digital Output) para alarmas; 1× buzzer integrado |
| **Entradas digitales** | 2× DI (Digital Input) para sensores externos; 1× entrada ignición |
| **Alimentación** | 12V/24V DC (compatible con buses diésel y eléctricos); protección contra transientes ISO 7637-2 pulso 5 |
| **Consumo** | ≤ 2 W standby; ≤ 5 W activo |
| **Temperatura operación** | -20°C a +70°C |
| **Humedad** | 5% a 95% RH |
| **Protección** | IP65; resistencia a vibración IEC 60068-2-6; a prueba de polvo y salpicaduras |
| **Certificaciones** | CE; FCC; PTCRB (certificación celular); Anatel (si aplica LATAM); RETIE |
| **Dimensiones** | ≈ 120 × 80 × 35 mm |
| **Peso** | ≤ 300 g |
| **Montaje** | Adhesivo industrial 3M VHB o tornillos M4; instalación en compartimento técnico |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SGCF-01-01 | Capturar posición GPS/GNSS cada 1-3 segundos | Obligatorio |
| RF-SGCF-01-02 | Transmitir posición en tiempo real al CCO vía 4G/MQTT | Obligatorio |
| RF-SGCF-01-03 | Almacenar posiciones localmente ante pérdida de conectividad | Obligatorio |
| RF-SGCF-01-04 | Sincronizar buffer offline al restaurar conectividad | Obligatorio |
| RF-SGCF-01-05 | Detectar eventos de conducción: exceso de velocidad, frenada brusca, aceleración agresiva | Obligatorio |
| RF-SGCF-01-06 | Verificar cumplimiento de ruta planificada (geocerca) | Obligatorio |
| RF-SGCF-01-07 | Verificar cumplimiento de frecuencia programada | Obligatorio |
| RF-SGCF-01-08 | Leer odómetro del vehículo por CAN Bus/OBD-II (si disponible) | Deseable |
| RF-SGCF-01-09 | Detectar encendido/apagado del motor (ignición) | Obligatorio |
| RF-SGCF-01-10 | Enviar alerta inmediata ante activación de botón de pánico | Obligatorio |
| RF-SGCF-01-11 | Soportar SIM dual de operadores diferentes (redundancia) | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SGCF-01-01 | Precisión de posición standalone | < 5 m CEP 95% |
| RNF-SGCF-01-02 | Precisión con SBAS/EGNOS | < 2 m CEP 95% |
| RNF-SGCF-01-03 | Latencia de transmisión | < 3 segundos desde captura hasta visualización en CCO |
| RNF-SGCF-01-04 | TTFF (Time To First Fix) en frío | < 60 segundos |
| RNF-SGCF-01-05 | TTFF en caliente | < 10 segundos |
| RNF-SGCF-01-06 | MTBF | ≥ 100.000 horas |
| RNF-SGCF-01-07 | Buffer offline | ≥ 72 horas de datos (posiciones 3-seg) |
| RNF-SGCF-01-08 | Consumo en standby | ≤ 2 W |
| RNF-SGCF-01-09 | Protección eléctrica | ISO 7637-2 pulso 5; sobre-voltaje hasta 36V |
| RNF-SGCF-01-10 | Temperatura operación | -20°C a +70°C |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad de transmisión | ≥ 99.5% | Tiempo con posiciones transmitidas / total |
| Precisión de posición | < 5 m | CEP 95% en muestreo diario |
| Latencia de transmisión | < 3 seg | Promedio en 1000 posiciones |
| Tiempo de fix inicial | < 30 seg (cálido) | Promedio en encendidos diarios |
| Detección de exceso de velocidad | < 10 seg | Desde evento hasta alerta en CCO |
| Falsos positivos de geocerca | < 2% | Alertas fuera de ruta confirmadas como válidas / total alertas |

---

## 9.4 CC-SGCF-02: Cámaras de Conteo de Pasajeros

Las Cámaras de Conteo de Pasajeros constituyen el componente de campo del subsistema de Cuantificación de Demanda del SGCF. Instaladas estratégicamente sobre cada puerta de acceso al bus (típicamente 2 cámaras por bus: puerta delantera y puerta trasera), capturan imágenes de video en tiempo real y aplican algoritmos de inteligencia artificial para detectar y contar el flujo bidireccional de personas que embarcan y desembarcan.

El sistema utiliza tecnología de visión artificial (computer vision) basada en redes neuronales convolucionales (CNN) o modelos de detección de objetos en tiempo real (YOLO, SSD, EfficientDet). Las cámaras capturan video a resolución suficiente para identificar siluetas humanas (típicamente 720p o 1080p), y el procesador embebido (EDGE AI) ejecuta el modelo de inferencia localmente, sin necesidad de transmitir video completo a la nube. Solo se transmiten los conteos agregados (ej. "+3 embarques, -2 desembarques en parada X") junto con metadatos de timestamp, ubicación GPS, y confianza del conteo.

La tecnología de conteo puede basarse en: (1) Detección de cabezas (head detection) mediante cámaras con ángulo cenital (desde arriba), que es el enfoque más robusto para entornos de alta densidad; (2) Detección de cuerpo completo con tracking temporal (DeepSORT, ByteTrack) para seguir individuos a través del campo de visión y determinar dirección de movimiento; o (3) Sensores térmicos o 3D (LiDAR de corto alcance) como complemento para mejorar precisión en condiciones de iluminación difícil o alta ocupación.

El conteo bidireccional es esencial para calcular la ocupación del bus en tiempo real: ocupación = Σ embarques − Σ desembarques desde inicio de ruta. Esta información se visualiza en el CCO, se presenta al conductor en la consola ("Ocupación actual: 28/35 pasajeros"), y se utiliza para ajustar dinámicamente la frecuencia de despacho: si múltiples buses de una misma ruta muestran alta ocupación (>80%), el CCO puede decidir enviar un bus adicional o reducir el intervalo entre buses.

La precisión del conteo se verifica periódicamente mediante muestreo manual: un observador en el bus cuenta físicamente los embarques/desembarques en una muestra de viajes, y los resultados se comparan con el conteo del sistema. Si la discrepancia excede el umbral aceptable (>3% sistemático), se ajustan los parámetros del modelo o se recalibra la cámara.

### Justificación Estratégica

El conteo preciso de pasajeros es un pilar fundamental para la viabilidad del modelo tarifa técnica + FEST. La compensación económica entre Metro Sabanas y los operadores de buses requiere conocer cuántos pasajeros transportó cada operador, cuántos kilómetros recorrió, y cuánto recaudó. Sin un sistema de conteo automatizado, estos datos dependen de registros manuales o declaraciones de los operadores — fuentes inherentemente imprecisas y susceptibles de fraude.

La experiencia internacional en transporte público moderno demuestra que los sistemas de conteo automatizado mejoran la precisión de la información de demanda en un orden de magnitud. Mientras los registros manuales tienen márgenes de error del 20-40%, los sistemas de visión artificial modernos alcanzan precisiones ≥ 97% en condiciones controladas. Esta precisión permite:

1. **Liquidación justa de compensación**: Cada operador recibe exactamente lo que le corresponde por pasajeros transportados y kilómetros recorridos.
2. **Planificación basada en datos reales**: Las frecuencias de ruta se ajustan según demanda medida, no suposiciones.
3. **Detección de fugas de recaudo**: Si el conteo de embarques difiere significativamente de las transacciones del validador, se activa investigación de posible evasión o falla del validador.
4. **Reporte regulatorio preciso**: SuperTransporte y MinTransporte reciben datos de demanda verificables, no estimaciones.

Adicionalmente, los datos históricos de ocupación por ruta, franja horaria, y día de la semana habilitan análisis de patrones de demanda que son invaluables para la planificación de expansiones futuras. ¿Cuál ruta tiene mayor crecimiento de demanda? ¿En qué horarios se presentan cuellos de botella? ¿Dónde se necesitan buses de mayor capacidad? Estas preguntas, antes respondidas por intuición, ahora pueden basarse en datos objetivos.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SGCF-02 |
| **Nombre** | Cámaras de Conteo de Pasajeros |
| **Subsistema** | SGCF — Conteo de Pasajeros |
| **Cantidad** | 2 por bus (puerta delantera + trasera) × 34 buses = 68 unidades |
| **Tipo de cámara** | Cámara IP con procesador EDGE AI integrado (SoC con NPU ≥ 2 TOPS) |
| **Sensor** | CMOS 1/2.8" o mayor; resolución ≥ 2 MP (1920×1080) |
| **Lente** | Lente fijo gran angular ≥ 2.8 mm (ángulo de visión ≥ 100° horizontal) o lente varifocal 2.8-12 mm |
| **Posición** | Montaje cenital (desde arriba) sobre puerta; altura 2.0-2.5 m del piso |
| **Procesador EDGE AI** | SoC con NPU (Neural Processing Unit) ≥ 2 TOPS; soporta inferencia en tiempo real de modelos de detección de objetos |
| **Algoritmo de conteo** | Detección de cabezas (head detection) o detección de cuerpo completo + tracking temporal (DeepSORT/ByteTrack) |
| **Conectividad** | Ethernet 10/100 Mbps; PoE (802.3af); WiFi opcional |
| **Salida de datos** | Conteos agregados por dirección (embarque/desembarque) en JSON/CSV; intervalo configurable 1-60 segundos; transmisión MQTT/HTTP |
| **Almacenamiento local** | ≥ 32 GB microSD para video de respaldo y logs de conteo |
| **Iluminación** | Funcionamiento con iluminación ambiental ≥ 5 lux; IR integrado para condiciones de baja luz (alcance ≥ 5 m) |
| **Temperatura operación** | -10°C a +50°C |
| **Humedad** | 5% a 95% RH |
| **Protección** | IP54; IK08 |
| **Certificaciones** | CE; FCC; RETIE |
| **Dimensiones** | ≈ 100 × 60 × 50 mm (sin montaje) |
| **Peso** | ≤ 300 g |
| **Montaje** | Soporte de techo; ángulo ajustable 0-45°; tornillos M4 |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SGCF-02-01 | Contar embarques por puerta en tiempo real | Obligatorio |
| RF-SGCF-02-02 | Contar desembarques por puerta en tiempo real | Obligatorio |
| RF-SGCF-02-03 | Diferenciar dirección de movimiento (entrada/salida) | Obligatorio |
| RF-SGCF-02-04 | Transmitir conteos agregados al CCO vía MQTT/HTTP | Obligatorio |
| RF-SGCF-02-05 | Operar en condiciones de iluminación variable (día, noche, artificial) | Obligatorio |
| RF-SGCF-02-06 | Almacenar video de respaldo localmente ante eventos de interés | Deseable |
| RF-SGCF-02-07 | Integrar timestamp y posición GPS en cada reporte de conteo | Obligatorio |
| RF-SGCF-02-08 | Detectar anomalías de conteo (diferencia >20% vs. transacciones) | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SGCF-02-01 | Precisión de conteo | ≥ 97% (en condiciones normales de densidad < 1 pax/m²/s) |
| RNF-SGCF-02-02 | Precisión en alta densidad | ≥ 90% (en condiciones de alta densidad > 2 pax/m²/s) |
| RNF-SGCF-02-03 | Latencia de conteo | < 2 segundos desde paso hasta reporte |
| RNF-SGCF-02-04 | Resolución mínima de persona | ≥ 40 píxeles de altura en imagen |
| RNF-SGCF-02-05 | Frame rate de procesamiento | ≥ 15 fps para inferencia en tiempo real |
| RNF-SGCF-02-06 | Consumo (PoE) | ≤ 6 W |
| RNF-SGCF-02-07 | Almacenamiento local video | ≥ 7 días de video continuo a 720p 10 fps |
| RNF-SGCF-02-08 | Fiabilidad del algoritmo | F1-score ≥ 0.95 en detección de personas |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Precisión de conteo bidireccional | ≥ 97% | Comparación vs. conteo manual en muestreo semanal |
| Latencia de reporte | < 2 seg | Promedio en operación continua |
| Disponibilidad del sistema | ≥ 99.0% | Tiempo funcionamiento / total |
| Precisión en alta densidad | ≥ 90% | Durante horas pico |
| Tasa de falsos positivos | < 3% | Detecciones no correspondientes a personas |

---

## 9.5 CC-SGCF-03: Cámaras de Videovigilancia CCTV a Bordo

Las Cámaras de Videovigilancia CCTV a Bordo constituyen el componente de campo del subsistema de Seguridad y Videovigilancia del SGCF. Instaladas en el interior de cada bus (típicamente 2 cámaras por bus: una en cabina apuntando hacia la zona de pasajeros, y otra en zona trasera apuntando hacia la puerta trasera), capturan video continuo de alta definición que sirve para: (1) Seguridad de pasajeros y conductor ante eventos de orden público o delincuencia; (2) Investigación post-incidente (accidentes, altercados, daños al bus); (3) Evidencia operativa para disputas de recaudo o reclamaciones; (4) Supervisión remota por el CCO en tiempo real ante alertas.

Las cámaras son del tipo domo o bullet IP, con resolución mínima 1080p (2 megapíxeles), compresión de video H.265 para optimizar ancho de banda y almacenamiento, visión nocturna mediante LED infrarrojo (IR) con alcance ≥ 10 metros, y ángulo de visión amplio (≥ 90° horizontal) para cubrir la mayor área posible del interior del bus. La lente es fija gran angular (2.8 mm típico) o varifocal motorizada para ajuste remoto.

Las cámaras se conectan mediante Ethernet (PoE 802.3af) al switch local del bus, y desde allí al grabador DVR/NVR (CC-SGCF-04) y al router WiFi/4G (CC-SIU-01). El CCO puede solicitar visualización en vivo de cualquier cámara, o extraer grabaciones históricas por rango de tiempo. Ante la activación del botón de pánico (CC-SST-01), el sistema marca automáticamente el segmento de video correspondiente como "evento de emergencia", impidiendo su sobrescritura por políticas de rotación de almacenamiento.

La videovigilancia en tiempo real desde el CCO requiere ancho de banda significativo: un stream H.265 a 1080p 15 fps consume aproximadamente 1-2 Mbps por cámara. Para 2 cámaras por bus y potencialmente visualización simultánea de múltiples buses, el CCO requiere un enlace de internet dedicado de alta capacidad (≥ 100 Mbps) con QoS para tráfico de video.

### Justificación Estratégica

La videovigilancia a bordo es un componente de seguridad crítico en transporte público urbano. Sincelejo, como otras ciudades colombianas, enfrenta desafíos de seguridad que afectan la percepción de los usuarios y la disposición a utilizar transporte público. La presencia visible de cámaras CCTV actúa como disuasivo para comportamientos delictivos o altercados, y proporciona evidencia irrefutable para investigaciones.

El valor de la videovigilancia trasciende la seguridad: es una herramienta operativa indispensable. Cuando un pasajero reclama que "pagó pero el validador no registró", el video permite verificar si el pasajero realmente acercó la tarjeta al validador. Cuando un conductor reporta un incidente, el video documenta la secuencia de eventos con precisión objetiva. Cuando una autoridad solicita información sobre un hecho ocurrido en un bus, el video es la fuente de verdad.

En el contexto del modelo FEST, donde la compensación a operadores depende de datos objetivos, la videovigilancia complementa los datos del validador y el conteo de pasajeros. Si un operador reclama que transportó más pasajeros de los registrados por el validador, el video permite verificar visualmente la ocupación real del bus en momentos específicos.

Adicionalmente, la videovigilancia en tiempo real desde el CCO permite respuesta inmediata ante emergencias: cuando se activa el botón de pánico, el operador del CCO puede ver qué está ocurriendo en el bus antes de despachar recursos de respuesta, optimizando la asignación de ambulancias, policía o grúas según la gravedad visual del incidente.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SGCF-03 |
| **Nombre** | Cámaras de Videovigilancia CCTV a Bordo |
| **Subsistema** | SGCF — Videovigilancia |
| **Cantidad** | 2 por bus (interior) × 34 buses = 68 unidades |
| **Tipo** | Cámara IP domo o bullet; montaje en techo/pared interior bus |
| **Sensor** | CMOS 1/2.8" STARVIS o equivalente; resolución ≥ 2 MP (1920×1080) |
| **Lente** | Fija gran angular 2.8 mm (ángulo ≥ 100° H) o varifocal motorizada 2.8-12 mm |
| **Compresión** | H.265/H.264; Main Profile; soporte Smart Codec (ROI) |
| **Frame rate** | 25/30 fps @ 1080p; configurable 15 fps para optimizar almacenamiento |
| **Visión nocturna** | LED IR integrado; alcance ≥ 10 m; ICR (IR Cut Filter) automático |
| **WDR** | ≥ 120 dB WDR (Wide Dynamic Range) para manejar contraste luz/sombra en interior bus |
| **Audio** | Micrófono integrado; captura audio sincronizado con video |
| **Conectividad** | Ethernet 10/100 Mbps; PoE 802.3af |
| **Almacenamiento** | Ranura microSD ≥ 128 GB para respaldo local ante falla del DVR |
| **Temperatura operación** | -10°C a +50°C |
| **Humedad** | 5% a 95% RH |
| **Protección** | IP54; IK08; resistente a vibración vehicular |
| **Certificaciones** | CE; FCC; RETIE |
| **Dimensiones** | ≈ Ø 100 × 80 mm (domo) o 80 × 60 × 150 mm (bullet) |
| **Peso** | ≤ 500 g |
| **Montaje** | Soporte de techo/pared; ángulo ajustable; tornillos autorroscantes; adhesivo 3M VHB opcional |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SGCF-03-01 | Capturar video continuo 24/7 en resolución 1080p | Obligatorio |
| RF-SGCF-03-02 | Comprimir video con H.265 para optimizar almacenamiento y ancho de banda | Obligatorio |
| RF-SGCF-03-03 | Transmitir stream en vivo al CCO bajo solicitud | Obligatorio |
| RF-SGCF-03-04 | Grabar audio sincronizado con video | Obligatorio |
| RF-SGCF-03-05 | Visión nocturna mediante IR en condiciones de baja iluminación | Obligatorio |
| RF-SGCF-03-06 | Almacenar video localmente en microSD como respaldo | Obligatorio |
| RF-SGCF-03-07 | Marcar segmentos de video ante eventos (botón pánico, alerta operador) | Obligatorio |
| RF-SGCF-03-08 | Soportar WDR para manejar contraste interior bus (ventanas/sombra) | Obligatorio |
| RF-SGCF-03-09 | Integrar timestamp y posición GPS en metadatos del video | Obligatorio |
| RF-SGCF-03-10 | Permitir extracción de video por rango de tiempo desde CCO | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SGCF-03-01 | Resolución de video | 1920×1080 @ 25 fps |
| RNF-SGCF-03-02 | Bitrate H.265 @ 1080p 15 fps | 1-2 Mbps por cámara |
| RNF-SGCF-03-03 | Latencia de stream en vivo | < 5 segundos |
| RNF-SGCF-03-04 | Alcance IR nocturno | ≥ 10 m |
| RNF-SGCF-03-05 | WDR | ≥ 120 dB |
| RNF-SGCF-03-06 | Consumo (PoE) | ≤ 6 W |
| RNF-SGCF-03-07 | MTBF | ≥ 100.000 horas |
| RNF-SGCF-03-08 | Resistencia a vibración | IEC 60068-2-6; 5-500 Hz; 2 G |
| RNF-SGCF-03-09 | Calidad de audio | Frecuencia 100 Hz - 16 kHz; SNR ≥ 50 dB |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad de grabación | ≥ 99.0% | Tiempo grabando / total |
| Calidad de video | ≥ 25 dB PSNR | Métrica objetiva de calidad |
| Latencia de stream | < 5 seg | Desde CCO hasta visualización |
| Tiempo de retención | ≥ 30 días | Capacidad del DVR/NVR |
| Tasa de falla de almacenamiento | < 0.5% | Eventos de pérdida de grabación |

---

## 9.6 CC-SGCF-04: Grabador DVR/NVR SSD

El Grabador DVR/NVR SSD es el componente de campo central de almacenamiento de video del SGCF. Instalado en un compartimento técnico seguro de cada bus (típicamente bajo asiento o en gabinete de equipos), este dispositivo recibe los streams de video de las cámaras CCTV (CC-SGCF-03) y del conteo de pasajeros (CC-SGCF-02), los comprime y almacena en discos de estado sólido (SSD), y gestiona la transmisión de video en vivo o grabado hacia el CCO bajo demanda.

A diferencia de los discos duros tradicionales (HDD), los SSD son la tecnología de elección para aplicaciones móviles por su mayor resistencia a vibraciones, temperatura, y golges — factores críticos en un bus urbano que experimenta aceleraciones, frenadas, baches, y vibración continua del motor. Los SSD basados en NAND flash (preferiblemente TLC o MLC industrial) no tienen partes móviles, eliminando el riesgo de falla mecánica por vibración.

El grabador soporta al menos 4 canales de video IP (cámaras), con resolución 1080p en cada canal y compresión H.265. La capacidad de almacenamiento debe ser suficiente para retener 30 días de video continuo de 2 cámaras a 1080p 15 fps con H.265. Un cálculo estimado: 2 cámaras × 1.5 Mbps × 3600 seg/hora × 24 horas × 30 días = ~777.600 segundos × 3 Mbps = ~2.916.000 Mb = ~365 GB
---

## 9.7 CC-SGCF-05: Consola/Tablet Conductor Rugerizada

La Consola/Tablet Conductor Rugerizada es el dispositivo de interfaz humana del conductor con el sistema ITS. Montada en el panel frontal del bus, proporciona al conductor: información de ruta y próxima parada; estado del validador y recaudo; alertas del sistema (exceso de velocidad, fuera de ruta, mensajes del CCO); y botón de pánico de emergencia.

La tablet es de grado industrial o militar (MIL-STD-810G), con resistencia a vibración, golpes, polvo, y salpicaduras de agua (IP65). La pantalla de 10-12 pulgadas es legible bajo luz solar directa (brillo ≥ 1000 nits), esencial para operación diurna. La interfaz táctil funciona con guantes, ya que los conductores pueden usar guantes de trabajo.

La conectividad incluye: WiFi para comunicación local con validadores y cámaras; 4G/5G para comunicación con el CCO; Bluetooth para headsets; y GPS integrado (redundante con el GPS del SGCF). La alimentación es 12V/24V DC del vehículo, con protección contra picos y transitorios.

### Justificación Estratégica

La tablet del conductor es el componente que humaniza el sistema ITS: traduce datos técnicos en información comprensible y accionable para el conductor. Sin esta interfaz, el conductor opera "a ciegas", sin saber si el validador está funcionando, si va fuera de ruta, o si el CCO le está enviando una instrucción.

La ruggedización es indispensable: un tablet de consumo (iPad, Galaxy Tab) fallaría en semanas por vibración, calor, polvo, y golpes accidentales. La legibilidad bajo luz solar es crítica: un conductor que no puede ver la pantalla por reflejos del sol puede perderse, omitir paradas, o no ver alertas de seguridad.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SGCF-05 |
| **Nombre** | Consola/Tablet Conductor Rugerizada |
| **Subsistema** | SGCF — Interfaz Humana del Conductor |
| **Cantidad** | 34 unidades (1 por bus) |
| **Pantalla** | 10-12 pulgadas; resolución ≥ 1920×1200; tecnología IPS o transflectiva; brillo ≥ 1000 nits (legible bajo sol directo); táctil capacitiva multi-touch; funciona con guantes; recubrimiento anti-reflejante |
| **CPU** | ARM octa-core ≥ 2.0 GHz o Intel Atom/Celeron ≥ 1.6 GHz |
| **RAM** | ≥ 4 GB LPDDR4 |
| **Almacenamiento** | ≥ 64 GB eMMC o SSD; ranura microSD ≥ 256 GB |
| **Sistema operativo** | Android 11+ (rugged) o Linux embebido |
| **Conectividad** | WiFi 802.11ac; Bluetooth 5.0; 4G LTE Cat 6 (dual-SIM opcional); GPS/GNSS integrado; NFC opcional |
| **Entradas/Salidas** | USB 3.0; microSD; audio 3.5 mm; puerto serie RS-232/RS-485; GPIO |
| **Alimentación** | 12V/24V DC vehicular (8-36V rango); protección contra picos ISO 7637-2; consumo ≤ 15 W |
| **Ruggedización** | IP65; MIL-STD-810G (golpe, vibración, caída 1.2 m); temperatura -20°C a +60°C; humedad 5-95% RH |
| **Montaje** | Soporte VESA o RAM Mount; amortiguación de vibración; ángulo ajustable |
| **Certificaciones** | CE; FCC; RETIE; MIL-STD-810G; IP65 |
| **Dimensiones** | ≈ 280 × 200 × 35 mm |
| **Peso** | ≤ 1.5 kg |
| **Accesorios** | Soporte de montaje; cable de alimentación 12V; cable USB OTG; manual de operación; stylus opcional |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SGCF-05-01 | Mostrar mapa de ruta con próxima parada y destino | Obligatorio |
| RF-SGCF-05-02 | Indicar estado del validador (online, transacciones pendientes, error) | Obligatorio |
| RF-SGCF-05-03 | Mostrar alertas del CCO y botón de confirmación de recepción | Obligatorio |
| RF-SGCF-05-04 | Registrar botón de pánico y transmitir alerta al CCO | Obligatorio |
| RF-SGCF-05-05 | Mostrar velocidad actual y alerta de exceso de velocidad | Obligatorio |
| RF-SGCF-05-06 | Indicar cuando el bus está fuera de ruta o fuera de geocerca | Obligatorio |
| RF-SGCF-05-07 | Mostrar mensajes de texto y voz del CCO | Obligatorio |
| RF-SGCF-05-08 | Operar con pantalla táctil usando guantes | Obligatorio |
| RF-SGCF-05-09 | Funcionar en modo offline y sincronizar al restaurar conectividad | Obligatorio |
| RF-SGCF-05-10 | Soportar cambio de turno de conductor (logout/login rápido) | Deseable |
| RF-SGCF-05-11 | Mostrar estadísticas de recaudo del turno | Deseable |
| RF-SGCF-05-12 | Soportar actualización de firmware OTA | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SGCF-05-01 | Tiempo de arranque | < 30 segundos |
| RNF-SGCF-05-02 | Latencia de actualización de pantalla | < 1 segundo |
| RNF-SGCF-05-03 | Brillo de pantalla | ≥ 1000 nits |
| RNF-SGCF-05-04 | MTBF | ≥ 50.000 horas |
| RNF-SGCF-05-05 | Consumo | ≤ 15 W |
| RNF-SGCF-05-06 | Temperatura operación | -20°C a +60°C |
| RNF-SGCF-05-07 | Protección | IP65; MIL-STD-810G |
| RNF-SGCF-05-08 | Legibilidad | Legible bajo luz solar directa |
| RNF-SGCF-05-09 | Tiempo de carga de mapa | < 5 segundos |
| RNF-SGCF-05-10 | Precisión de GPS integrado | < 5 m CEP |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad | ≥ 99.0% | Tiempo operativo / total |
| Tiempo de arranque | < 30 seg | Promedio en 10 encendidos |
| Fallas por vibración/golpe | 0 en 1 año | Incidentes reportados |
| Satisfacción del conductor | ≥ 3.5/5 | Encuesta mensual |
| Latencia de alerta CCO→tablet | < 3 seg | Promedio en 100 alertas |
| Actualizaciones OTA exitosas | ≥ 95% | Exitosas / intentos |

---

## 9.8 CC-SST-01: Botón de Pánico y Alertas

El Botón de Pánico y Alertas es el componente crítico de seguridad del SST. Consiste en: un botón de pánico físico en la cabina del conductor (accesible pero protegido contra activación accidental); un botón de pánico oculto en la zona de pasajeros (para uso de cobrador o pasajeros ante situaciones de riesgo); y sensores automáticos de alerta (aceleración brusca, frenada de emergencia, colisión detectada por acelerómetro).

La activación del botón de pánico genera una alerta de prioridad máxima que se transmite al CCO en < 10 segundos, incluyendo: identificación del bus; posición GPS exacta; timestamp; tipo de alerta (pánico manual, colisión, aceleración brusca); y estado de las cámaras (enlace para video en vivo). Simultáneamente, el sistema puede notificar automáticamente a autoridades (policía, bomberos) mediante integración con plataformas de emergencia locales.

Los sensores automáticos utilizan un acelerómetro triaxial de alta sensibilidad que detecta: desaceleración > 3g (frenada de emergencia); aceleración > 3g (colisión trasera o arranque brusco); y vibración anómala (vuelco o volcadura). Estos umbrales son configurables por el CCO según las características de cada ruta.

### Justificación Estratégica

La seguridad del pasajero y del conductor es la responsabilidad primordial del operador del SETP. En situaciones de robo, violencia, accidente, o emergencia médica, cada segundo cuenta. El botón de pánico proporciona un canal de comunicación de emergencia que es: instantáneo (no requiere llamada telefónica ni explicación verbal); silencioso (no alerta al agresor); geolocalizado (el CCO sabe exactamente dónde está el bus); y multimedia (incluye video en vivo de las cámaras).

La normatividad colombiana (Resolución 20203040034065 de MinTransporte) establece que los sistemas ITS deben incluir mecanismos de respuesta a emergencias. El botón de pánico cumple este requisito y va más allá al incluir sensores automáticos que detectan colisiones incluso cuando el conductor está incapacitado y no puede presionar el botón manualmente.

La inversión en botones de pánico y sensores de emergencia es relativamente modesta comparada con el valor de una vida humana o con los costos legales y reputacionales de un incidente mal manejado. Un sistema que permite respuesta rápida ante emergencias salva vidas, reduce daños, y demuestra compromiso con la seguridad de la comunidad.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SST-01 |
| **Nombre** | Botón de Pánico y Alertas |
| **Subsistema** | SST — Seguridad y Respuesta a Emergencias |
| **Cantidad** | 68 botones (2 por bus: conductor + pasajeros) + 34 unidades de sensor/acelerómetro |
| **Botón de pánico** | Pulsador momentáneo con retención; LED de confirmación; protección contra activación accidental (cubierta o doble pulsación); retroiluminación para visibilidad nocturna; conexión cableada al gateway de comunicaciones |
| **Sensor/acelerómetro** | Acelerómetro triaxial MEMS; rango ± 16g; resolución ≥ 12 bits; detección de: colisión (impacto > 3g), frenada de emergencia (desaceleración > 3g), vuelco (orientación anómala > 45°); tasa de muestreo ≥ 100 Hz |
| **Unidad de control** | Microcontrolador ARM Cortex-M; procesamiento local de umbrales; filtrado de ruido; algoritmo de detección de eventos; memoria buffer para 60 segundos de datos pre-evento; conexión CAN Bus o Ethernet al gateway |
| **Alertas** | Pánico manual (conductor); pánico manual (pasajeros); colisión detectada; frenada de emergencia; vuelco; falla médica del conductor (detección por inactividad prolongada + botón) |
| **Transmisión** | Prioridad máxima en la red de comunicaciones; latencia < 10 segundos al CCO; reintentos automáticos hasta confirmación; almacenamiento local si sin conectividad |
| **Notificación** | Audio-visual en CCO; notificación push a operadores; integración con plataforma de emergencias locales (SIATA, policía); email/SMS a directivos |
| **Indicación local** | LED rojo intermitente en bus (alerta activa); buzzer opcional (configurable por política); pantalla del conductor muestra confirmación de alerta enviada |
| **Alimentación** | 12V/24V DC vehicular; consumo ≤ 2 W (botón + sensor); protección contra picos ISO 7637-2 |
| **Temperatura operación** | -20°C a +60°C |
| **Humedad** | 5% a 95% RH |
| **Protección** | IP54 (botón); IP65 (sensor si exterior); IK08 (resistencia a impacto) |
| **Certificaciones** | CE; FCC; RETIE; ISO 26262 (si aplica a grado automotriz) |
| **Dimensiones (botón)** | ≈ 40 × 40 × 20 mm |
| **Peso (botón)** | ≤ 50 g |
| **Dimensiones (sensor)** | ≈ 50 × 50 × 20 mm |
| **Peso (sensor)** | ≤ 100 g |
| **Accesorios** | Cable de conexión 2 m; conector impermeable; manual de instalación; calcomanía de instrucciones; prueba de funcionamiento |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SST-01-01 | Activar alerta de pánico manual desde cabina del conductor | Obligatorio |
| RF-SST-01-02 | Activar alerta de pánico manual desde zona de pasajeros | Obligatorio |
| RF-SST-01-03 | Detectar colisión automáticamente (acelerómetro > 3g) | Obligatorio |
| RF-SST-01-04 | Detectar frenada de emergencia automáticamente | Obligatorio |
| RF-SST-01-05 | Transmitir alerta al CCO en < 10 segundos | Obligatorio |
| RF-SST-01-06 | Incluir posición GPS, identidad del bus, timestamp, y tipo de alerta | Obligatorio |
| RF-SST-01-07 | Activar video en vivo de cámaras del bus ante alerta | Obligatorio |
| RF-SST-01-08 | Notificar a autoridades de emergencia locales | Obligatorio |
| RF-SST-01-09 | Almacenar datos pre-evento (60 segundos antes) | Obligatorio |
| RF-SST-01-10 | Permitir cancelación de falsa alarma desde CCO o tablet del conductor | Obligatorio |
| RF-SST-01-11 | Operar ante falla de conectividad (almacenar y retransmitir) | Obligatorio |
| RF-SST-01-12 | Proteger contra activación accidental (cubierta, doble pulsación) | Obligatorio |
| RF-SST-01-13 | Soportar detección de vuelco (orientación anómala) | Deseable |
| RF-SST-01-14 | Soportar detección de falla médica del conductor | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SST-01-01 | Latencia de transmisión de alerta | < 10 segundos |
| RNF-SST-01-02 | Tasa de falsas alarmas | < 0.1% por mes |
| RNF-SST-01-03 | Precisión de detección de colisión | ≥ 95% (validación con dataset de choques) |
| RNF-SST-01-04 | Tiempo de respuesta del CCO | < 2 minutos (respuesta humana) |
| RNF-SST-01-05 | MTBF del botón | ≥ 100.000 ciclos de pulsación |
| RNF-SST-01-06 | MTBF del sensor | ≥ 100.000 horas |
| RNF-SST-01-07 | Consumo | ≤ 2 W |
| RNF-SST-01-08 | Temperatura operación | -20°C a +60°C |
| RNF-SST-01-09 | Precisión de GPS en alerta | < 5 m CEP |
| RNF-SST-01-10 | Retención de datos pre-evento | ≥ 60 segundos |
| RNF-SST-01-11 | Tiempo de cancelación de falsa alarma | < 30 segundos |
| RNF-SST-01-12 | Prioridad de red para alertas | Máxima (sobre cualquier otro tráfico) |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Tiempo de transmisión de alerta | < 10 seg | Promedio en 100 pruebas |
| Tasa de falsas alarmas | < 0.1%/mes | Alarmas falsas / total buses / mes |
| Tiempo de respuesta del CCO | < 2 min | Desde alerta hasta acción humana |
| Cobertura de video en alerta | 100% | Alertas con video disponible / total |
| Disponibilidad del sistema | ≥ 99.5% | Tiempo operativo / total |
| Satisfacción de conductores | ≥ 4.0/5 | Encuesta de confianza en sistema |
| Incidentes con respuesta exitosa | ≥ 90% | Incidentes bien manejados / total |


---

## 9.9 CC-SIU-01: Router WiFi 4G/5G con Portal Cautivo

El Router WiFi 4G/5G con Portal Cautivo es el componente central del SIU que proporciona conectividad a internet para los pasajeros y servicios de valor agregado. Instalado en cada bus, este dispositivo: crea una red WiFi local para pasajeros; proporciona acceso a internet mediante conexión 4G/5G; presenta un portal cautivo con información del sistema (rutas, horarios, tarifas); y recolecta datos anónimos de uso para análisis de demanda.

El router es de grado industrial, diseñado para operación móvil, con soporte para bandas LTE de Colombia (B2, B4, B28), CA (Carrier Aggregation) para mayor throughput, y antenas externas de alto rendimiento montadas en el techo del bus. El portal cautivo es una página web que se muestra automáticamente al conectarse al WiFi, con: mapa de rutas y paradas; horarios en tiempo real; tarifas y medios de pago aceptados; encuestas de satisfacción; y publicidad local (comercios cercanos a la ruta, eventos de la ciudad).

La recolección de datos anónimos incluye: número de dispositivos conectados por tramo de ruta (indicador de carga del bus); duración promedio de sesión (tiempo de viaje); y patrones de conexión por franja horaria (demanda por hora). Estos datos, agregados y anonimizados, son valiosos para la planeación operativa y para comercialización con anunciantes locales.

### Justificación Estratégica

La conectividad WiFi en el bus ya no es un lujo: es una expectativa de los usuarios, especialmente millennials y generación Z que ven el transporte público como tiempo productivo (trabajo, estudio, entretenimiento). Un bus con WiFi atractivo retiene usuarios y atrae nuevos, especialmente en segmentos de ingreso medio-alto que valoran la productividad del tiempo de viaje.

El portal cautivo es una plataforma de comunicación con el usuario que va más allá de la información de ruta: permite encuestas de satisfacción en tiempo real, publicidad contextual (un usuario en la ruta La Vega-Argelia ve anuncios de comercios en ese corredor), y gamificación (puntos por uso frecuente). La información recolectada es invaluable para el operador: sabe qué rutas están más cargadas, a qué horas, y puede ajustar frecuencias en consecuencia.

La arquitectura de red del SIU también es fundamental para la operación del sistema ITS: los validadores, tablet del conductor, y cámaras se conectan a través de este router, compartiendo la conexión 4G/5G hacia el CCO. La segmentación de VLAN permite que el tráfico operativo (recaudo, GPS, pánico) tenga prioridad sobre el tráfico de pasajeros (WiFi), garantizando que un bus lleno de usuarios viendo videos no afecte la transmisión de alertas de emergencia.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-SIU-01 |
| **Nombre** | Router WiFi 4G/5G con Portal Cautivo |
| **Subsistema** | SIU — Sistema de Información al Usuario |
| **Cantidad** | 34 unidades (1 por bus) |
| **Tipo** | Router industrial 4G/5G móvil; grado automotriz |
| **Conectividad celular** | 4G LTE Cat 6 o superior; 5G NR (si disponible en Sincelejo); dual-SIM (fallback entre operadores); bandas LATAM: B2 (1900 MHz), B4 (AWS), B28 (700 MHz); CA (Carrier Aggregation); throughput ≥ 150 Mbps DL / 50 Mbps UL (4G); ≥ 500 Mbps DL / 100 Mbps UL (5G) |
| **WiFi** | 802.11ac/ax (WiFi 5/6); dual band 2.4 GHz + 5 GHz; 2×2 MIMO; MU-MIMO; ≥ 64 clientes simultáneos; SSID configurable; portal cautivo integrado |
| **Antenas** | 4× antenas celulares externas (MIMO 4×4); 2× antenas WiFi externas; montaje magnético o fijo en techo del bus; cables coaxiales de baja pérdida |
| **Segmentación** | VLANs: VLAN 10 (operativo: validadores, tablet, GPS, cámaras); VLAN 20 (pasajeros: WiFi internet); VLAN 30 (mantenimiento: acceso técnico); QoS: VLAN 10 con prioridad máxima |
| **Portal cautivo** | Servidor web embebido; página de bienvenida personalizable; autenticación por SMS, email, o redes sociales (opcional); límite de tiempo/sesión; términos de uso; recolección de datos anonimizados |
| **Firewall** | Stateful firewall; NAT; port forwarding; DMZ; filtrado de MAC; filtrado de contenido (opcional) |
| **VPN** | Cliente VPN (IPsec, OpenVPN, WireGuard) para túnel seguro hacia CCO |
| **GPS** | GPS/GNSS integrado (redundante con SGCF); geolocalización del bus para portal |
| **Puertos Ethernet** | ≥ 4 puertos Gigabit Ethernet (para validadores, tablet, cámaras, DVR) |
| **Puertos USB** | ≥ 2 puertos USB 3.0 (para almacenamiento, modem backup) |
| **Alimentación** | 12V/24V DC vehicular (8-36V rango); protección contra picos ISO 7637-2; consumo ≤ 20 W (typical); ≤ 30 W (peak con carga WiFi máxima) |
| **Ruggedización** | IP54 o superior; temperatura -20°C a +60°C; vibración MIL-STD-810G; montaje en rack DIN o superficie |
| **Gestión** | Interfaz web; SSH; SNMP; API REST; actualización de firmware OTA; monitoreo de uso, señal, temperatura |
| **Temperatura operación** | -20°C a +60°C |
| **Humedad** | 5% a 95% RH |
| **Certificaciones** | CE; FCC; RETIE; PTCRB (certificación celular); GCF |
| **Dimensiones** | ≈ 150 × 100 × 40 mm (compacto) o 200 × 120 × 50 mm (con antenas internas) |
| **Peso** | ≤ 500 g (sin antenas) |
| **Accesorios** | 4× antenas celulares; 2× antenas WiFi; cable de alimentación 12V; cable Ethernet 2 m (4 unidades); manual; kit de montaje en techo |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-SIU-01-01 | Proporcionar WiFi para pasajeros con portal cautivo | Obligatorio |
| RF-SIU-01-02 | Conectar a internet mediante 4G/5G con dual-SIM | Obligatorio |
| RF-SIU-01-03 | Segmentar red en VLANs (operativo, pasajeros, mantenimiento) | Obligatorio |
| RF-SIU-01-04 | Aplicar QoS para priorizar tráfico operativo | Obligatorio |
| RF-SIU-01-05 | Mostrar información de rutas y horarios en portal | Obligatorio |
| RF-SIU-01-06 | Recolectar datos anonimizados de uso (dispositivos, duración, patrones) | Obligatorio |
| RF-SIU-01-07 | Soportar ≥ 30 clientes WiFi simultáneos | Obligatorio |
| RF-SIU-01-08 | Establecer VPN segura hacia CCO | Obligatorio |
| RF-SIU-01-09 | Soportar portal cautivo con autenticación opcional | Deseable |
| RF-SIU-01-10 | Soportar encuestas de satisfacción en portal | Deseable |
| RF-SIU-01-11 | Soportar publicidad local en portal | Deseable |
| RF-SIU-01-12 | Operar con actualización de firmware OTA | Obligatorio |
| RF-SIU-01-13 | Proveer throughput ≥ 50 Mbps efectivos para pasajeros | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-SIU-01-01 | Throughput 4G | ≥ 150 Mbps DL / 50 Mbps UL |
| RNF-SIU-01-02 | Throughput 5G | ≥ 500 Mbps DL / 100 Mbps UL |
| RNF-SIU-01-03 | Latencia 4G | < 50 ms |
| RNF-SIU-01-04 | Clientes WiFi simultáneos | ≥ 30 |
| RNF-SIU-01-05 | MTBF | ≥ 50.000 horas |
| RNF-SIU-01-06 | Consumo typical | ≤ 20 W |
| RNF-SIU-01-07 | Consumo peak | ≤ 30 W |
| RNF-SIU-01-08 | Temperatura operación | -20°C a +60°C |
| RNF-SIU-01-09 | Tiempo de conexión celular | < 30 segundos desde arranque |
| RNF-SIU-01-10 | Tiempo de failover dual-SIM | < 10 segundos |
| RNF-SIU-01-11 | Cobertura WiFi interior del bus | ≥ 95% del área de pasajeros |
| RNF-SIU-01-12 | Throughput efectivo por cliente | ≥ 2 Mbps |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad de WiFi | ≥ 98% | Tiempo operativo / total |
| Satisfacción de pasajeros (WiFi) | ≥ 3.5/5 | Encuesta en portal o app |
| Clientes conectados promedio | ≥ 10 por bus | Métrica de uso |
| Throughput efectivo | ≥ 2 Mbps/cliente | Medición en campo |
| Dispositivos detectados por tramo | Datos anonimizados | Análisis de demanda |
| Fallas de conectividad 4G | < 1% | Tiempo sin conexión / total |
| Tiempo de failover SIM | < 10 seg | Pruebas de campo |
| Uso del portal cautivo | ≥ 50% | Conexiones con portal visto / total |

---

## 9.10 CC-COM-01: Radio VHF/UHF (Respaldo)

La Radio VHF/UHF es el sistema de comunicación de voz de respaldo entre el CCO y los conductores. Opera independientemente de la red celular 4G/5G, proporcionando un canal de comunicación confiable cuando: la red celular está congestionada o fuera de cobertura; hay falla del router SIU; o se requiere comunicación inmediata sin dependencia de infraestructura de terceros.

El sistema consiste en: una radio base en el CCO (estación fija de 25-50 W); radios móviles en cada bus (25-50 W, montaje en panel); y una red de repetidoras si la geografía de Sincelejo lo requiere (para cobertura en zonas bajas o detrás de edificios). La frecuencia de operación se asigna mediante licencia otorgada por la ANE (Agencia Nacional del Espectro) o la autoridad local correspondiente.

La radio VHF/UHF proporciona comunicación push-to-talk (PTT): el conductor presiona un botón en el micrófono o en el volante, habla, y su voz se transmite inmediatamente a todos los operadores del CCO y a otros conductores en el mismo canal. Es comunicación half-duplex: solo una persona habla a la vez, pero es instantánea y no requiere marcar números ni esperar conexión.

### Justificación Estratégica

La comunicación de voz entre CCO y conductor es esencial para la operación segura y eficiente del SETP. El CCO necesita informar al conductor sobre: cambios de ruta por obras o eventos; desvíos de emergencia; instrucciones ante contingencias (bus averiado, accidente, clima); y coordinación de frecuencias ("acelere, tiene 3 minutos de retraso"). El conductor necesita informar al CCO sobre: incidentes en ruta; fallas mecánicas; solicitud de apoyo; y confirmación de instrucciones.

Si toda esta comunicación depende únicamente de la red celular 4G/5G, el sistema es vulnerable a: fallas de torres celulares; congestión de red en horas pico; fallas del router SIU; cortes de energía en infraestructura de operadores; y bloqueos de tráfico VoIP por políticas de operadores. La radio VHF/UHF es una tecnología madura, robusta, y operada por el propio sistema de transporte, sin dependencia de terceros.

En Colombia, múltiples sistemas de transporte público (TransMilenio, MIO, TransCaribe) utilizan radio VHF/UHF como canal principal o de respaldo de comunicación. La experiencia demuestra que en emergencias (terremotos, inundaciones, disturbios), cuando la red celular colapsa, la radio VHF/UHF sigue operando porque es infraestructura independiente y de menor densidad.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-COM-01 |
| **Nombre** | Radio VHF/UHF (Respaldo) |
| **Subsistema** | COM — Comunicaciones de Respaldo |
| **Cantidad** | 34 radios móviles (1 por bus) + 5 radios base/portátiles (CCO) + 1 estación base fija |
| **Banda** | VHF (136-174 MHz) o UHF (400-470 MHz); según licencia y disponibilidad de espectro en Sincelejo |
| **Potencia** | Radio móvil: 25-50 W; radio base: 25-50 W; radio portátil: 4-5 W |
| **Modulación** | FM analógica (FM) o digital (DMR, P25, NXDN); DMR recomendado por eficiencia espectral y funcionalidades digitales |
| **Canales** | ≥ 16 canales programables; 1 canal principal operativo; 1 canal de emergencia; canales por ruta o zona |
| **Funciones** | PTT (push-to-talk); scan de canales; selcall (llamada selectiva a bus específico); emergencia (alerta de pánico vía radio); GPS integrado (algunos modelos DMR); mensajes de texto cortos (SMS vía radio); cifrado opcional (básico) |
| **Audio** | Audio claro; cancelación de ruido; VOX (operación manos libres); micrófono externo; altavoz externo |
| **Conectividad** | Antena externa en bus (montaje en techo o espejo); conector SMA; cable coaxial de baja pérdida |
| **Alimentación** | 12V/24V DC vehicular (radio móvil); 110-240V AC (radio base); consumo ≤ 10 W (radio móvil en RX); ≤ 50 W (radio móvil en TX 50W) |
| **Ruggedización** | MIL-STD-810G; IP54; temperatura -20°C a +60°C; vibración y golpe automotriz |
| **Licencia** | Licencia de uso de espectro radioeléctrico ante ANE o autoridad local; frecuencia asignada; coordinación con otros usuarios del espectro en Sincelejo |
| **Temperatura operación** | -20°C a +60°C |
| **Humedad** | 5% a 95% RH |
| **Certificaciones** | CE; FCC; RETIE; certificación de radio homologada en Colombia (CRC, ANE) |
| **Dimensiones (radio móvil)** | ≈ 160 × 50 × 180 mm |
| **Peso (radio móvil)** | ≤ 1.5 kg |
| **Dimensiones (radio base)** | ≈ 300 × 250 × 100 mm |
| **Peso (radio base)** | ≤ 3 kg |
| **Accesorios** | Antena móvil; cable coaxial 5 m; micrófono/PTT; soporte de montaje; fuente de poder base; manual de programación; software de programación de canales |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-COM-01-01 | Proporcionar comunicación de voz PTT entre CCO y todos los buses | Obligatorio |
| RF-COM-01-02 | Proporcionar comunicación de voz PTT entre buses (misma ruta) | Deseable |
| RF-COM-01-03 | Soportar llamada selectiva a bus específico (selcall) | Obligatorio |
| RF-COM-01-04 | Soportar canal de emergencia independiente | Obligatorio |
| RF-COM-01-05 | Operar independientemente de red celular | Obligatorio |
| RF-COM-01-06 | Proveer cobertura en toda el área de operación del SETP | Obligatorio |
| RF-COM-01-07 | Soportar GPS integrado (para ubicación vía radio) | Deseable |
| RF-COM-01-08 | Soportar mensajes de texto cortos (SMS vía radio) | Deseable |
| RF-COM-01-09 | Soportar cifrado básico de comunicaciones | Deseable |
| RF-COM-01-10 | Operar con calidad de audio clara (SINAD ≥ 40 dB) | Obligatorio |
| RF-COM-01-11 | Soportar cancelación de ruido de motor y ambiente | Obligatorio |
| RF-COM-01-12 | Funcionar como respaldo ante falla total de comunicaciones digitales | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-COM-01-01 | Potencia de transmisión | 25-50 W (móvil); 25-50 W (base) |
| RNF-COM-01-02 | Sensibilidad de receptor | ≤ 0.25 μV (12 dB SINAD) |
| RNF-COM-01-03 | Cobertura en área urbana | ≥ 15 km radio desde base (depende de terreno) |
| RNF-COM-01-04 | Calidad de audio | SINAD ≥ 40 dB |
| RNF-COM-01-05 | MTBF | ≥ 50.000 horas |
| RNF-COM-01-06 | Consumo RX | ≤ 10 W |
| RNF-COM-01-07 | Consumo TX | ≤ 50 W (50W) |
| RNF-COM-01-08 | Temperatura operación | -20°C a +60°C |
| RNF-COM-01-09 | Tiempo de arranque | < 2 segundos |
| RNF-COM-01-10 | Canales programables | ≥ 16 |
| RNF-COM-01-11 | Precisión de GPS (si aplica) | < 10 m CEP |
| RNF-COM-01-12 | Tiempo de conmutación de canal | < 500 ms |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Cobertura del área de operación | 100% | % del área con señal ≥ -95 dBm |
| Calidad de audio | ≥ 4.0/5 | Encuesta de conductores |
| Disponibilidad del sistema | ≥ 99.5% | Tiempo operativo / total |
| Tiempo de respuesta PTT | < 1 seg | Desde presionar PTT hasta audio en receptor |
| Fallas de radio | < 1% | Fallas / total buses / mes |
| Uso del canal de emergencia | Según necesidad | Eventos de emergencia / mes |
| Satisfacción de conductores | ≥ 4.0/5 | Encuesta de confianza en comunicaciones |

---

## 9.11 CC-COM-02: Gateway de Comunicaciones Bus-CCO

El Gateway de Comunicaciones Bus-CCO es el concentrador de datos de cada bus que gestiona, prioriza, y transmite toda la información del bus hacia el CCO y viceversa. Actúa como el "router central" del bus, recibiendo datos de: validadores (transacciones); GPS (posiciones); cámaras (video); tablet del conductor (estado, alertas); botón de pánico (emergencias); conteo de pasajeros (carga); y router SIU (uso WiFi).

El gateway es un dispositivo de computación de borde (edge computing) con capacidad de procesamiento local: filtra y agrega datos (envía posición cada 3 segundos, pero transacciones inmediatamente); almacena datos cuando no hay conectividad (buffer de ≥ 1 GB); y ejecuta reglas locales (si botón de pánico, inmediatamente video en vivo con máxima prioridad; si fuera de ruta, alerta al conductor y CCO).

La conectividad del gateway hacia el CCO utiliza el canal 4G/5G del router SIU, pero con priorización inteligente: el tráfico de emergencia (pánico, colisión) tiene prioridad absoluta; el tráfico operativo (recaudo, GPS) tiene alta prioridad; el tráfico de video tiene prioridad media (con calidad adaptable al ancho de banda disponible); y el tráfico de WiFi de pasajeros tiene prioridad baja.

### Justificación Estratégica

Sin un gateway de comunicaciones inteligente, cada dispositivo del bus intentaría conectarse independientemente al CCO, generando: saturación del ancho de banda celular; latencia impredecible; pérdida de datos por contención; y complejidad de gestión de conexiones. El gateway centraliza y optimiza todas las comunicaciones, actuando como un "traffic cop" que garantiza que los datos críticos lleguen primero.

La capacidad de edge computing es particularmente valiosa para decisiones que no pueden esperar la latencia de ida y vuelta al CCO: detección de fuera de ruta (comparación local de posición con geocerca); detección de exceso de velocidad (comparación local con límite de ruta); y respuesta a botón de pánico (activación local de cámaras y transmisión prioritaria). Estas decisiones locales mejoran el tiempo de respuesta y reducen la dependencia de conectividad constante.

El buffer de almacenamiento local es esencial para la resiliencia: si un bus pierde conectividad durante 30 minutos (túnel, zona rural, falla de torre), el gateway almacena todas las transacciones, posiciones, y eventos, y los transmite en lote cuando se restaura la conexión. Sin este buffer, el operador perdería visibilidad de la flota y el recaudo de ese período.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-COM-02 |
| **Nombre** | Gateway de Comunicaciones Bus-CCO |
| **Subsistema** | COM — Concentrador de Comunicaciones |
| **Cantidad** | 34 unidades (1 por bus) |
| **Tipo** | Gateway/edge computer industrial; grado automotriz; Linux embebido o RTOS |
| **CPU** | ARM quad-core ≥ 1.5 GHz o Intel Atom/Celeron ≥ 1.6 GHz |
| **RAM** | ≥ 2 GB DDR4 |
| **Almacenamiento** | ≥ 32 GB eMMC + ranura microSD ≥ 256 GB (buffer de datos); SSD opcional |
| **Conectividad local** | 4× Ethernet Gigabit (para validadores, tablet, cámaras, router SIU); 2× USB 3.0; 1× CAN Bus; 1× RS-232/RS-485; GPIO |
| **Conectividad WAN** | Vía router SIU (4G/5G); interfaz Ethernet al router; VPN IPsec/WireGuard hacia CCO |
| **Procesamiento edge** | Motor de reglas configurable; detección de eventos (geocercas, umbrales de velocidad); agregación de datos; filtrado de tráfico; QoS local |
| **Buffer de datos** | ≥ 1 GB de buffer circular; almacena transacciones, posiciones, eventos; transmisión en lote al restaurar conectividad; priorización de buffer (emergencias primero) |
| **Protocolos** | MQTT (publicación de eventos); HTTP/REST (APIs); WebSocket (video); FTP/SFTP (transferencia de archivos); NTP (sincronización de tiempo) |
| **Seguridad** | Firewall local; TLS 1.3 para todas las comunicaciones; autenticación de dispositivo con certificados; firmado de mensajes; anti-replay |
| **Alimentación** | 12V/24V DC vehicular (8-36V rango); protección contra picos ISO 7637-2; consumo ≤ 10 W |
| **Ruggedización** | IP54; MIL-STD-810G (vibración, golpe); temperatura -20°C a +60°C; montaje en gabinete técnico del bus |
| **Temperatura operación** | -20°C a +60°C |
| **Humedad** | 5% a 95% RH |
| **Certificaciones** | CE; FCC; RETIE; E-Mark (si aplica automotriz) |
| **Dimensiones** | ≈ 150 × 100 × 40 mm (compacto) |
| **Peso** | ≤ 500 g |
| **Accesorios** | Cable Ethernet 2 m (4 unidades); cable de alimentación 12V; manual de configuración; software de gestión remota; certificados de seguridad pre-instalados |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-COM-02-01 | Concentrar datos de todos los dispositivos del bus | Obligatorio |
| RF-COM-02-02 | Transmitir datos al CCO con priorización de tráfico | Obligatorio |
| RF-COM-02-03 | Almacenar datos localmente ante pérdida de conectividad | Obligatorio |
| RF-COM-02-04 | Sincronizar datos almacenados al restaurar conectividad | Obligatorio |
| RF-COM-02-05 | Ejecutar reglas de edge (geocercas, velocidad, alertas) | Obligatorio |
| RF-COM-02-06 | Priorizar tráfico de emergencia sobre todo otro tráfico | Obligatorio |
| RF-COM-02-07 | Soportar MQTT, REST, WebSocket, FTP | Obligatorio |
| RF-COM-02-08 | Establecer VPN segura hacia CCO | Obligatorio |
| RF-COM-02-09 | Autenticar todos los dispositivos del bus | Obligatorio |
| RF-COM-02-10 | Registrar auditoría de todas las comunicaciones | Obligatorio |
| RF-COM-02-11 | Soportar actualización de firmware OTA | Obligatorio |
| RF-COM-02-12 | Proporcionar QoS local entre dispositivos del bus | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-COM-02-01 | Latencia de transmisión de datos prioritarios | < 3 segundos |
| RNF-COM-02-02 | Capacidad de buffer | ≥ 1 GB |
| RNF-COM-02-03 | Tiempo de sincronización de buffer | < 5 minutos para 1 GB |
| RNF-COM-02-04 | MTBF | ≥ 50.000 horas |
| RNF-COM-02-05 | Consumo | ≤ 10 W |
| RNF-COM-02-06 | Temperatura operación | -20°C a +60°C |
| RNF-COM-02-07 | Throughput de agregación | ≥ 100 Mbps (local) |
| RNF-COM-02-08 | Precisión de reloj | Sincronizado con NTP (ms) |
| RNF-COM-02-09 | Tiempo de arranque | < 60 segundos |
| RNF-COM-02-10 | Priorización de emergencias | Máxima latencia < 5 segundos |
| RNF-COM-02-11 | Cifrado de comunicaciones | TLS 1.3 (100% del tráfico WAN) |
| RNF-COM-02-12 | Autenticación de dispositivos | Certificados X.509 |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad | ≥ 99.0% | Tiempo operativo / total |
| Latencia de datos prioritarios | < 3 seg | Promedio en 1000 eventos |
| Tasa de pérdida de datos | < 0.1% | Datos no transmitidos / total |
| Tiempo de sincronización post-corte | < 5 min | Para buffer lleno |
| Eventos de edge procesados | 100% | Geocercas, velocidad, alertas |
| Actualizaciones OTA exitosas | ≥ 95% | Exitosas / intentos |
| Satisfacción de operación | ≥ 4.0/5 | Encuesta de operadores del CCO |


---

## 9.12 CC-CCO-01: Video Wall 2×2 (4 pantallas 55")

El Video Wall 2×2 es el componente central de visualización del CCO. Consiste en 4 pantallas de 55 pulgadas montadas en configuración 2×2 (2 filas, 2 columnas), controladas por un controlador de video wall que permite mostrar: mapa de flota en tiempo real (posición de los 34 buses); estado de alertas y emergencias; video en vivo de cámaras (especialmente ante botón de pánico); y dashboards de recaudo y operación.

Cada pantalla es de tecnología LED o LCD profesional, diseñada para operación 24/7, con brillo alto (≥ 500 cd/m²) para visibilidad en ambientes con luz mixta (iluminación del CCO + luz diurna por ventanas). Los biseles (marcos) entre pantallas son ultra delgados (≤ 3.5 mm) para minimizar la interrupción visual entre paneles.

El controlador de video wall permite múltiples modos de visualización: modo 1 (una imagen grande distribuida en las 4 pantallas); modo 2 (4 imágenes independientes, una por pantalla); y modo 3 (combinaciones mixtas, como 2×1 o 1×2). La señal de entrada puede provenir de: computadoras del CCO (vía HDMI/DisplayPort); NVR de videovigilancia (vía HDMI); o fuentes externas (vía Ethernet/HDBaseT).

### Justificación Estratégica

El video wall es el centro neurálgico de la supervisión visual del SETP. Un operador del CCO puede, de un vistazo, saber: dónde está cada bus (mapa con iconos de vehículos); cuál bus tiene una alerta activa (parpadeo rojo); si hay un botón de pánico activado (pantalla completa con video en vivo); y si el recaudo está fluyendo normalmente (gráficos de transacciones por minuto). Esta conciencia situacional (situational awareness) es imposible de lograr con monitores individuales dispersos.

La configuración 2×2 de 55" proporciona un área de visualización total de aproximadamente 110" diagonal (≈ 2.8 metros), suficiente para que 5 operadores en el CCO puedan ver la información desde sus puestos sin necesidad de acercarse. En situaciones de crisis (botón de pánico, colisión, desvío masivo), el video wall se convierte en el punto focal de coordinación de respuesta, donde el supervisor dirige la atención de todo el equipo.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-01 |
| **Nombre** | Video Wall 2×2 (4 pantallas 55") |
| **Subsistema** | CCO — Visualización Central |
| **Cantidad** | 4 pantallas + 1 controlador |
| **Pantallas** | LCD/LED profesional 55"; resolución 1920×1080 (FHD) cada una; brillo ≥ 500 cd/m²; contraste ≥ 3000:1; tiempo de respuesta ≤ 8 ms; ángulo de visión ≥ 178°; biseles ultra delgados ≤ 3.5 mm; vida útil ≥ 60.000 horas; diseñadas para operación 24/7 |
| **Controlador** | Controlador de video wall con: 4 salidas HDMI/DisplayPort (una por pantalla); 4 entradas HDMI/DisplayPort/DVI/VGA; entrada Ethernet para streaming IP; soporte de layouts 1×1, 2×2, 1×2, 2×1, PIP; control remoto; interfaz web; RS-232 para integración |
| **Montaje** | Soporte de pared fijo o soporte de suelo con ruedas; ángulo ajustable; gestión de cables integrada; montaje VESA 400×400 mm |
| **Señales** | Mapa de flota (HTML5/WebGL); video NVR (RTSP/ONVIF); dashboards (Power BI/Tableau/Grafana); alertas (software personalizado); TV pública (opcional) |
| **Alimentación** | 100-240V AC; consumo ≤ 150 W por pantalla (≤ 600 W total); conexión a UPS central 5 KVA |
| **Temperatura operación** | 0°C a +40°C |
| **Humedad** | 20% a 80% RH |
| **Certificaciones** | CE; FCC; Energy Star; RETIE |
| **Dimensiones (pantalla)** | ≈ 1210 × 680 × 100 mm (ancho × alto × profundidad con soporte) |
| **Dimensiones (video wall 2×2)** | ≈ 2430 × 1370 mm (ancho × alto, con biseles) |
| **Peso (pantalla)** | ≤ 25 kg cada una |
| **Peso (video wall total)** | ≤ 120 kg (incluye soporte) |
| **Accesorios** | Cable HDMI 2.0 3 m (8 unidades); cable de red CAT6 3 m; control remoto; manual de usuario; software de configuración de layouts |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-01-01 | Mostrar mapa de flota en tiempo real en modo 2×2 | Obligatorio |
| RF-CCO-01-02 | Mostrar 4 fuentes independientes (una por pantalla) | Obligatorio |
| RF-CCO-01-03 | Mostrar video en vivo ante alerta de pánico en pantalla completa | Obligatorio |
| RF-CCO-01-04 | Cambiar layouts remotamente desde estación de supervisor | Obligatorio |
| RF-CCO-01-05 | Soportar señales HDMI, DisplayPort, DVI, VGA | Obligatorio |
| RF-CCO-01-06 | Soportar streaming IP (RTSP, ONVIF) | Obligatorio |
| RF-CCO-01-07 | Operar 24/7 sin degradación de brillo | Obligatorio |
| RF-CCO-01-08 | Ser visible desde cualquier puesto del CCO | Obligatorio |
| RF-CCO-01-09 | Soportar PIP (picture-in-picture) | Deseable |
| RF-CCO-01-10 | Soportar rotación automática de layouts programada | Deseable |
| RF-CCO-01-11 | Integrar con sistema de alertas (cambio automático ante evento) | Obligatorio |
| RF-CCO-01-12 | Soportar control remoto e interfaz web | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-01-01 | Brillo | ≥ 500 cd/m² |
| RNF-CCO-01-02 | Contraste | ≥ 3000:1 |
| RNF-CCO-01-03 | Tiempo de respuesta | ≤ 8 ms |
| RNF-CCO-01-04 | Ángulo de visión | ≥ 178° horizontal / vertical |
| RNF-CCO-01-05 | Biseles | ≤ 3.5 mm |
| RNF-CCO-01-06 | Vida útil | ≥ 60.000 horas |
| RNF-CCO-01-07 | MTBF | ≥ 60.000 horas |
| RNF-CCO-01-08 | Consumo por pantalla | ≤ 150 W |
| RNF-CCO-01-09 | Temperatura operación | 0°C a +40°C |
| RNF-CCO-01-10 | Tiempo de conmutación de layout | < 3 segundos |
| RNF-CCO-01-11 | Resolución total (2×2) | 3840×2160 (4K UHD) |
| RNF-CCO-01-12 | Latencia de video | < 500 ms desde fuente hasta pantalla |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad | ≥ 99.0% | Tiempo operativo / total |
| Tiempo de conmutación de layout | < 3 seg | Promedio en 10 cambios |
| Fallas de pantalla | < 1 por año | Incidencias reportadas |
| Satisfacción de operadores | ≥ 4.0/5 | Encuesta mensual |
| Tiempo de respuesta a alerta | < 5 seg | Desde evento hasta video en pantalla |
| Brillo uniformidad | ≥ 90% | Medición con luxómetro en 9 puntos |
| Temperatura de operación | < 40°C | Sensores internos |

---

## 9.13 CC-CCO-02: Estación de Trabajo Supervisor (Triple Pantalla)

La Estación de Trabajo Supervisor es el puesto de mando del CCO. Equipada con tres monitores de 27 pulgadas, permite al supervisor de operaciones tener una visión panorámica del sistema: un monitor para el mapa de flota en tiempo real; otro para video wall de cámaras y alertas; y el tercero para dashboards de recaudo, KPIs, y herramientas de administración.

La computadora es de gama alta (Intel Core i7/i9 o AMD Ryzen 7/9), 32 GB de RAM, SSD NVMe de 1 TB, y tarjeta gráfica dedicada (NVIDIA GTX/RTX o AMD Radeon) para soportar múltiples monitores y aplicaciones gráficas intensivas (GIS, video, dashboards 3D). El sistema operativo es Windows 11 Pro o Ubuntu 22.04 LTS, según la preferencia del operador y compatibilidad con software de proveedores.

El software de supervisión incluye: cliente del SGCF (mapa con posiciones, geocercas, rutas); cliente del SRC (dashboard de recaudo, transacciones, alertas de fraude); NVR client (visualización de cámaras); herramientas de comunicación (radio, VoIP, mensajes a conductores); y herramientas de gestión (reportes, configuración, usuarios).

### Justificación Estratégica

El supervisor del CCO es el "capitán" del sistema ITS: toma decisiones en tiempo real que afectan a cientos o miles de pasajeros. Necesita una estación de trabajo que le proporcione: contexto completo (toda la información relevante sin cambiar de ventana); rapidez (acceso instantáneo a cualquier dato o herramienta); y confiabilidad (hardware que no se congela ni ralentiza ante múltiples aplicaciones).

Tres monitores son el estándar de la industria para centros de control de transporte público: el monitor izquierdo muestra el mapa de flota (contexto espacial); el monitor central muestra el video wall o la aplicación principal en la que se está trabajando; y el monitor derecho muestra dashboards de recaudo, KPIs, y herramientas de comunicación. Esta configuración reduce el "context switching" (cambio de atención entre ventanas) en un 40%, mejorando la eficiencia y reduciendo errores por distracción.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-02 |
| **Nombre** | Estación de Trabajo Supervisor (Triple Pantalla) |
| **Subsistema** | CCO — Puesto de Mando |
| **Cantidad** | 1 unidad |
| **Computador** | CPU: Intel Core i7-12700/i9-12900 o AMD Ryzen 7 5800X/9 5900X; RAM: 32 GB DDR4-3200; SSD: 1 TB NVMe PCIe 4.0; GPU: NVIDIA GTX 1660 / RTX 3060 o AMD RX 6600 (soporta 3 monitores); Ethernet: Gigabit; WiFi: 802.11ax; Bluetooth: 5.2 |
| **Monitores** | 3× LCD IPS 27"; resolución 1920×1080 (FHD) o 2560×1440 (QHD); brillo ≥ 300 cd/m²; contraste ≥ 1000:1; ángulo de visión ≥ 178°; tiempo de respuesta ≤ 5 ms; montaje VESA 100×100 mm; soporte ajustable en altura, inclinación, rotación |
| **Sistema operativo** | Windows 11 Pro (64-bit) o Ubuntu 22.04 LTS |
| **Software base** | Navegador (Chrome/Firefox); suite ofimática; cliente VPN; software GIS (QGIS/ArcGIS); NVR client (VMS); herramientas de monitoreo (Zabbix/Prometheus); cliente de correo; antivirus/EDR |
| **Periféricos** | Teclado mecánico ergonómico; mouse óptico de alta precisión; webcam 1080p; auriculares con micrófono cancelación de ruido; altavoces (opcional) |
| **Seguridad** | BitLocker (Windows) o LUKS (Linux); autenticación con contraseña + PIN + TPM; bloqueo automático después de 5 minutos de inactividad; EDR (Endpoint Detection and Response) |
| **Alimentación** | 100-240V AC; fuente de poder ≥ 650 W (80 Plus Bronze); UPS individual ≥ 1000 VA (opcional) o conexión a UPS central 5 KVA |
| **Temperatura operación** | 0°C a +35°C |
| **Humedad** | 20% a 80% RH |
| **Certificaciones** | CE; FCC; Energy Star; RETIE |
| **Dimensiones (computador)** | Tower o SFF; ≈ 200 × 400 × 400 mm |
| **Peso (computador)** | ≤ 10 kg |
| **Accesorios** | Cable DisplayPort/HDMI 2 m (3 unidades); cable de red CAT6 2 m; tapete de mouse; manual de usuario; licencias de software |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-02-01 | Ejecutar mapa de flota en tiempo real con fluidez | Obligatorio |
| RF-CCO-02-02 | Visualizar ≥ 4 cámaras simultáneamente | Obligatorio |
| RF-CCO-02-03 | Ejecutar dashboards de recaudo y KPIs | Obligatorio |
| RF-CCO-02-04 | Comunicarse con conductores (radio, VoIP, mensajes) | Obligatorio |
| RF-CCO-02-05 | Generar reportes y exportar datos | Obligatorio |
| RF-CCO-02-06 | Administrar usuarios, roles, y permisos | Obligatorio |
| RF-CCO-02-07 | Configurar geocercas, rutas, y frecuencias | Obligatorio |
| RF-CCO-02-08 | Visualizar alertas y gestionar respuesta a emergencias | Obligatorio |
| RF-CCO-02-09 | Conectarse a VPN corporativa y proveedores SaaS | Obligatorio |
| RF-CCO-02-10 | Ejecutar videollamadas con calidad HD | Deseable |
| RF-CCO-02-11 | Soportar múltiples sesiones de usuario simultáneas | Deseable |
| RF-CCO-02-12 | Cifrar disco completo y usar MFA | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-02-01 | Tiempo de arranque | < 30 segundos desde frío |
| RNF-CCO-02-02 | Tiempo de apertura de aplicación GIS | < 10 segundos |
| RNF-CCO-02-03 | RAM disponible para multitarea | ≥ 16 GB libres con todas las apps abiertas |
| RNF-CCO-02-04 | Espacio en disco | ≥ 500 GB libres para datos y logs |
| RNF-CCO-02-05 | MTBF | ≥ 50.000 horas |
| RNF-CCO-02-06 | Consumo | ≤ 250 W (typical); ≤ 400 W (peak) |
| RNF-CCO-02-07 | Nivel sonoro | < 35 dB(A) en idle |
| RNF-CCO-02-08 | Temperatura operación | 0°C a +35°C |
| RNF-CCO-02-09 | Resolución de monitores | 1920×1080 @ 60 Hz cada uno (o 2560×1440) |
| RNF-CCO-02-10 | Ángulo de visión de monitores | ≥ 178° horizontal / vertical |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Tiempo de arranque | < 30 seg | Promedio en 10 encendidos |
| Tiempo de apertura GIS | < 10 seg | Promedio en 10 aperturas |
| Tiempo de respuesta con 10 apps abiertas | < 2 seg | Latencia al cambiar de ventana |
| Satisfacción del supervisor | ≥ 4.0/5 | Encuesta mensual de usabilidad |
| Fallas de hardware | < 1 por año | Incidencias reportadas |
| Tiempo de reparación | < 4 horas | Swap de unidad por repuesto |


---

## 9.14 CC-CCO-03: Estación de Trabajo Doble Pantalla (Planeación + Conciliación)

La Estación de Trabajo Doble Pantalla es el puesto de operación del CCO dedicado a la planeación de rutas, programación de frecuencias, y conciliación de recaudo. Cada estación consta de una computadora de alto rendimiento con dos monitores de 27 pulgadas Full HD, configurados para permitir la multitarea eficiente: en un monitor el operador puede visualizar el mapa de flota y herramientas GIS, mientras en el otro maneja el dashboard de recaudo y herramientas de conciliación.

La computadora está configurada con un procesador de gama alta (Intel Core i7 o AMD Ryzen 7), 32 GB de RAM para manejar múltiples aplicaciones simultáneamente (navegador con múltiples pestañas, GIS, hojas de cálculo, dashboards), y un disco de estado sólido NVMe de 1 TB para arranque rápido y acceso instantáneo a datos. El sistema operativo puede ser Windows 11 Pro (para compatibilidad con software de proveedores) o Ubuntu 22.04 LTS (para robustez y menor costo de licenciamiento).

Los dos monitores de 27" con resolución 1920×1080 (Full HD) y panel IPS proporcionan ángulo de visión amplio y colores precisos, esenciales para la visualización de mapas y gráficos. El soporte de montaje dual permite ajustar la altura, inclinación y rotación de cada monitor independientemente, adaptándose a la ergonomía de cada operador.

### Justificación Estratégica

La estación de planeación + conciliación es el puesto de trabajo más demandante del CCO en términos de recursos computacionales. El operador de planeación utiliza software GIS (QGIS o ArcGIS) para diseñar y modificar rutas, definir paradas, calcular distancias y tiempos de ciclo, y generar itinerarios. Este software GIS requiere procesamiento gráfico significativo y memoria RAM considerable. Simultáneamente, el operador de conciliación maneja hojas de cálculo con miles de transacciones de recaudo, ejecuta consultas complejas en bases de datos, y genera reportes para SuperTransporte y MinTransporte.

La dualidad de monitores permite que un solo operador (o dos operadores en turnos) gestione tanto la planeación operativa como la conciliación financiera sin necesidad de cambiar constantemente de ventana o aplicación. Esto mejora la productividad y reduce errores por distracción o context switching. La inversión en hardware de gama alta para este puesto se amortiza rápidamente mediante la eficiencia operativa y la capacidad de procesar grandes volúmenes de datos sin lentitud.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-03 |
| **Nombre** | Estación de Trabajo Doble Pantalla (Planeación + Conciliación) |
| **Subsistema** | CCO — Puestos de Trabajo |
| **Cantidad** | 2 unidades |
| **Computador** | CPU: Intel Core i7-12700 o AMD Ryzen 7 5800X; RAM: 32 GB DDR4-3200; SSD: 1 TB NVMe PCIe 4.0; GPU: Integrada Intel UHD / AMD Radeon (para GIS básico) o dedicada NVIDIA GTX 1650 (para GIS avanzado); Ethernet: Gigabit; WiFi: 802.11ax; Bluetooth: 5.2 |
| **Monitores** | 2× LCD IPS 27"; resolución 1920×1080 (FHD); brillo ≥ 250 cd/m²; contraste ≥ 1000:1; ángulo de visión ≥ 178°; tiempo de respuesta ≤ 5 ms; montaje VESA 100×100 mm; soporte ajustable en altura, inclinación, rotación |
| **Sistema operativo** | Windows 11 Pro (64-bit) o Ubuntu 22.04 LTS |
| **Software base** | Navegador (Chrome/Firefox); suite ofimática (LibreOffice o Microsoft Office); cliente de correo; software GIS (QGIS gratuito o ArcGIS licenciado); cliente VPN; antivirus/EDR |
| **Periféricos** | Teclado ergonómico; mouse óptico de precisión; webcam 1080p (para videollamadas); auriculares con micrófono (para comunicación con conductores) |
| **Seguridad** | BitLocker (Windows) o LUKS (Linux) para cifrado de disco; autenticación con contraseña + PIN; bloqueo automático después de 5 minutos de inactividad |
| **Alimentación** | 100-240V AC; fuente de poder ≥ 500 W (80 Plus Bronze); UPS individual ≥ 600 VA (opcional) o conexión a UPS central 5 KVA |
| **Temperatura operación** | 0°C a +35°C |
| **Humedad** | 20% a 80% RH |
| **Certificaciones** | CE; FCC; Energy Star; RETIE |
| **Dimensiones (computador)** | Tower o SFF; ≈ 180 × 360 × 380 mm (SFF) |
| **Peso (computador)** | ≤ 8 kg (SFF) |
| **Accesorios** | Cable DisplayPort/HDMI 2 m (2 unidades); cable de red CAT6 2 m; tapete de mouse; manual de usuario; licencias de software |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-03-01 | Ejecutar software GIS (QGIS/ArcGIS) con fluidez | Obligatorio |
| RF-CCO-03-02 | Manejar hojas de cálculo con >10.000 filas sin lentitud | Obligatorio |
| RF-CCO-03-03 | Visualizar múltiples dashboards simultáneamente en 2 monitores | Obligatorio |
| RF-CCO-03-04 | Conectarse a VPN corporativa y proveedores SaaS | Obligatorio |
| RF-CCO-03-05 | Ejecutar videollamadas con calidad HD | Obligatorio |
| RF-CCO-03-06 | Cifrar disco completo para protección de datos | Obligatorio |
| RF-CCO-03-07 | Operar 12+ horas diarias sin degradación de rendimiento | Obligatorio |
| RF-CCO-03-08 | Soportar conexiones múltiples a bases de datos (PostgreSQL, MySQL) | Obligatorio |
| RF-CCO-03-09 | Imprimir reportes en impresora de red del CCO | Deseable |
| RF-CCO-03-10 | Conectar lector/escritor Mifare para pruebas de tarjetas | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-03-01 | Tiempo de arranque | < 30 segundos desde frío |
| RNF-CCO-03-02 | Tiempo de apertura de software GIS | < 15 segundos |
| RNF-CCO-03-03 | RAM disponible para multitarea | ≥ 16 GB libres con todas las aplicaciones abiertas |
| RNF-CCO-03-04 | Espacio en disco | ≥ 500 GB libres para datos y logs |
| RNF-CCO-03-05 | MTBF | ≥ 50.000 horas |
| RNF-CCO-03-06 | Consumo | ≤ 200 W (typical); ≤ 300 W (peak) |
| RNF-CCO-03-07 | Nivel sonoro | < 35 dB(A) en idle |
| RNF-CCO-03-08 | Temperatura operación | 0°C a +35°C |
| RNF-CCO-03-09 | Resolución de monitores | 1920×1080 @ 60 Hz cada uno |
| RNF-CCO-03-10 | Ángulo de visión de monitores | ≥ 178° horizontal / vertical |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Tiempo de arranque | < 30 seg | Promedio en 10 encendidos |
| Tiempo de apertura GIS | < 15 seg | Promedio en 10 aperturas |
| Tiempo de respuesta con 10 apps abiertas | < 2 seg | Latencia al cambiar de ventana |
| Satisfacción del operador | ≥ 4.0/5 | Encuesta mensual de usabilidad |
| Fallas de hardware | < 1 por año | Incidencias reportadas |
| Tiempo de reparación | < 4 horas | Swap de unidad por repuesto |


---

## 9.15 CC-CCO-04: Estación de Inicialización de Tarjetas

La Estación de Inicialización de Tarjetas es el puesto de trabajo del CCO dedicado a la emisión, personalización, recarga, y gestión de tarjetas Mifare del sistema de recaudo. Cada estación consta de una computadora de gama media, un lector/escritor de tarjetas Mifare con antena SAM, y una impresora térmica para emitir tickets y comprobantes de recarga.

La computadora ejecuta el software de gestión de tarjetas, que permite: crear nuevas tarjetas con saldo inicial; recargar tarjetas existentes (efectivo, transferencia, PSE); bloquear tarjetas reportadas como perdidas o robadas; consultar saldo y historial de transacciones; emitir tarjetas de cortesía (adulto mayor, estudiante, PCD); y generar reportes de tarjetas activas, bloqueadas, y recargas del día.

El lector/escritor Mifare es un dispositivo de escritorio conectado por USB, compatible con tarjetas Mifare Classic 1K/4K y DESFire EV1/EV2/EV3. La antena SAM (Secure Access Module) integrada en el lector permite operaciones criptográficas seguras: autenticación de tarjeta, lectura/escritura de saldo en sectores protegidos, y generación de criptogramas. La impresora térmica de 58 mm imprime comprobantes de recarga con código QR, ID de transacción, fecha/hora, monto, y saldo final.

### Justificación Estratégica

La inicialización de tarjetas es un proceso crítico de operación diaria del SETP. Cada nuevo usuario del sistema requiere una tarjeta física, y cada recarga (ya sea en efectivo en un punto de venta, por transferencia bancaria, o por PSE en línea) debe reflejarse inmediatamente en el saldo de la tarjeta. La estación de inicialización es el punto de contacto físico donde los usuarios adquieren y mantienen sus medios de pago.

La inversión en estaciones dedicadas de inicialización (2 unidades para redundancia y capacidad) garantiza que el proceso de emisión y recarga no se detenga ante falla de una estación. La impresora térmica proporciona comprobantes físicos que son valiosos para la confianza del usuario: un pasajero que recarga $50.000 COP quiere un papel que confirme la transacción, especialmente en las primeras semanas de operación cuando la confianza en el sistema electrónico aún se está construyendo.

La gestión de tarjetas también es un pilar de seguridad: tarjetas perdidas o robadas deben bloquearse inmediatamente para evitar uso fraudulento. La estación de inicialización permite bloquear tarjetas en tiempo real, propagando la lista negra a todos los validadores de la flota en menos de 5 minutos. Sin esta capacidad, el sistema sería vulnerable a fraude con tarjetas reportadas.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-04 |
| **Nombre** | Estación de Inicialización de Tarjetas |
| **Subsistema** | CCO — Gestión de Medios de Pago |
| **Cantidad** | 2 unidades |
| **Computador** | CPU: Intel Core i5-12400 o AMD Ryzen 5 5600; RAM: 16 GB DDR4-3200; SSD: 512 GB NVMe; Ethernet: Gigabit; WiFi: 802.11ax; USB: 4× USB 3.0 |
| **Monitor** | 1× LCD IPS 24"; resolución 1920×1080 (FHD); brillo ≥ 250 cd/m²; ángulo de visión ≥ 178° |
| **Sistema operativo** | Windows 11 Pro (64-bit) o Ubuntu 22.04 LTS |
| **Lector/escritor Mifare** | Dispositivo USB; frecuencia 13.56 MHz; ISO 14443A/B; Mifare Classic 1K/4K; Mifare DESFire EV1/EV2/EV3; 4 ranuras SAM; velocidad de lectura/escritura ≥ 10 cm |
| **Antena SAM** | Integrada en lector/escritor; ISO 7816; compatible con Mifare SAM AV3; almacenamiento seguro de claves criptográficas |
| **Impresora térmica** | Impresora térmica de recibos 58 mm; velocidad ≥ 80 mm/s; resolución 203 dpi; cortador automático; conexión USB o Ethernet; alimentación 100-240V AC |
| **Software** | Aplicación de gestión de tarjetas; integración con SRC (API REST); base de datos local de tarjetas; módulo de reportes |
| **Periféricos** | Teclado; mouse; webcam 1080p; cajón de dinero (opcional, para recargas en efectivo) |
| **Seguridad** | BitLocker/LUKS; autenticación de usuario; registro de auditoría de todas las operaciones de tarjeta; cámara de seguridad enfocada al puesto |
| **Alimentación** | 100-240V AC; fuente de poder ≥ 300 W; conexión a UPS central 5 KVA |
| **Temperatura operación** | 0°C a +35°C |
| **Humedad** | 20% a 80% RH |
| **Certificaciones** | CE; FCC; RETIE; EMV (si procesa tarjetas bancarias) |
| **Dimensiones** | Escritorio estándar; computador SFF ≈ 180 × 360 × 380 mm |
| **Peso** | ≤ 10 kg (incluye computador, monitor, impresora) |
| **Accesorios** | Cable USB 2 m; cable de red CAT6 2 m; rollos de papel térmico 58 mm (10 unidades); manual de operación; tarjetas Mifare de prueba (10 unidades) |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-04-01 | Emitir nuevas tarjetas Mifare con saldo inicial | Obligatorio |
| RF-CCO-04-02 | Recargar tarjetas existentes (efectivo, transferencia, PSE) | Obligatorio |
| RF-CCO-04-03 | Bloquear tarjetas reportadas como perdidas o robadas | Obligatorio |
| RF-CCO-04-04 | Consultar saldo y historial de transacciones por tarjeta | Obligatorio |
| RF-CCO-04-05 | Emitir tarjetas de cortesía (adulto mayor, estudiante, PCD) | Obligatorio |
| RF-CCO-04-06 | Imprimir comprobante de recarga con código QR | Obligatorio |
| RF-CCO-04-07 | Sincronizar lista negra con todos los validadores de la flota | Obligatorio |
| RF-CCO-04-08 | Generar reportes diarios de tarjetas emitidas, recargas, bloqueos | Obligatorio |
| RF-CCO-04-09 | Soportar lectura/escritura de Mifare Classic y DESFire | Obligatorio |
| RF-CCO-04-10 | Operar con SAM para autenticación criptográfica segura | Obligatorio |
| RF-CCO-04-11 | Registrar auditoría de todas las operaciones (usuario, timestamp, acción) | Obligatorio |
| RF-CCO-04-12 | Soportar recarga en línea (integración PSE) | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-04-01 | Tiempo de emisión de tarjeta nueva | < 1 minuto |
| RNF-CCO-04-02 | Tiempo de recarga | < 30 segundos |
| RNF-CCO-04-03 | Tiempo de bloqueo y propagación | < 5 minutos a toda la flota |
| RNF-CCO-04-04 | Tiempo de impresión de comprobante | < 5 segundos |
| RNF-CCO-04-05 | MTBF | ≥ 50.000 horas |
| RNF-CCO-04-06 | Disponibilidad | ≥ 99.0% (excluyendo mantenimiento) |
| RNF-CCO-04-07 | Consumo | ≤ 200 W (incluye computador, monitor, impresora) |
| RNF-CCO-04-08 | Temperatura operación | 0°C a +35°C |
| RNF-CCO-04-09 | Precisión de impresión térmica | 203 dpi; texto legible; QR escaneable |
| RNF-CCO-04-10 | Capacidad de rollo térmico | ≥ 20 m de papel continuo |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Tiempo de emisión de tarjeta | < 1 min | Promedio en 100 emisiones |
| Tiempo de recarga | < 30 seg | Promedio en 100 recargas |
| Tiempo de propagación de bloqueo | < 5 min | Desde bloqueo en CCO hasta validador |
| Satisfacción del usuario | ≥ 4.0/5 | Encuesta en punto de recarga |
| Fallas de impresora | < 1% | Recargas con falla de impresión / total |
| Tarjetas emitidas por día | ≥ 50 | Capacidad operativa por estación |

---

## 9.16 CC-CCO-05: Estación de Programación de Rutas (GIS)

La Estación de Programación de Rutas es el puesto de trabajo especializado del CCO dedicado al diseño, análisis, optimización, y mantenimiento de las rutas del SETP. Esta estación está configurada con hardware de alto rendimiento y software GIS (Sistema de Información Geográfica) profesional para manejar grandes volúmenes de datos espaciales, realizar análisis de red, simular escenarios de tráfico, y generar itinerarios optimizados.

La computadora está configurada con procesador de gama alta, 32 GB de RAM, y disco SSD de 1 TB. Los dos monitores de 27" permiten visualizar simultáneamente el mapa de la ciudad con las rutas, los paneles de análisis de datos, y las herramientas de programación de frecuencias. El software GIS puede ser QGIS (open-source, gratuito, con amplia comunidad de soporte) o ArcGIS de Esri (licenciado, con funcionalidades avanzadas de análisis y modelado).

El operador de programación de rutas utiliza esta estación para: diseñar nuevas rutas o modificar existentes; calcular distancias, tiempos de ciclo, y velocidades promedio por segmento; definir paradas y sus coordenadas geográficas; programar frecuencias por franja horaria; simular el impacto de desvíos por obras o eventos; analizar la cobertura del sistema (qué zonas de la ciudad quedan sin servicio); y generar los archivos de ruta que se cargan en el sistema SGCF para geocercas y validación de cumplimiento.

### Justificación Estratégica

La programación de rutas es una función estratégica del CCO que va más allá de la operación diaria: define la estructura del servicio que los ciudadanos experimentan. Una ruta mal diseñada (con giros imposibles, segmentos congestionados, o paradas muy separadas) genera insatisfacción de usuarios, incumplimiento de frecuencias, y desgaste mecánico innecesario de los buses. Una ruta bien diseñada (con trazados eficientes, paradas accesibles, y frecuencias adecuadas a la demanda) maximiza la satisfacción del usuario, la eficiencia operativa, y la vida útil de los vehículos.

El software GIS permite análisis de red que son imposibles de realizar manualmente: identificar el camino más corto entre dos puntos respetando sentidos de calle y giros permitidos; calcular áreas de cobertura a 400 metros de cada parada (estándar de accesibilidad peatonal); simular el impacto de cerrar una calle por obras en las rutas que la utilizan; y analizar la demanda potencial de una nueva ruta basándose en densidad poblacional, centros de empleo, y equipamientos públicos.

La inversión en una estación de programación de rutas con software GIS profesional es fundamental para la evolución del SETP. Las 5 rutas actuales pueden expandirse a 10 o más en el futuro, y las frecuencias pueden ajustarse según crecimiento de demanda. Sin capacidad de análisis geoespacial, estas decisiones se toman por intuición, con resultados subóptimos. Con GIS, cada decisión de ruta está fundamentada en datos objetivos de distancia, tiempo, demanda, y cobertura.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-05 |
| **Nombre** | Estación de Programación de Rutas (GIS) |
| **Subsistema** | CCO — Planeación Estratégica de Rutas |
| **Cantidad** | 1 unidad |
| **Computador** | CPU: Intel Core i7-12700 o AMD Ryzen 7 5800X; RAM: 32 GB DDR4-3200; SSD: 1 TB NVMe PCIe 4.0; GPU: NVIDIA GTX 1650 o superior (aceleración GPU para GIS); Ethernet: Gigabit; WiFi: 802.11ax |
| **Monitores** | 2× LCD IPS 27"; resolución 1920×1080 (FHD); brillo ≥ 250 cd/m²; ángulo de visión ≥ 178°; soporte ajustable en altura, inclinación, rotación |
| **Sistema operativo** | Windows 11 Pro (64-bit) o Ubuntu 22.04 LTS |
| **Software GIS** | QGIS 3.28+ (open-source, gratuito) o ArcGIS Pro 3.0+ (licenciado); con extensiones de análisis de red, geocodificación, y cartografía |
| **Software complementario** | Navegador; suite ofimática; Python/R para análisis de datos; PostGIS (extensión espacial de PostgreSQL) para almacenamiento de datos geográficos |
| **Datos espaciales** | Mapa base de Sincelejo (OpenStreetMap o cartografía oficial IGAC); capas de rutas actuales; capas de paradas; capas de densidad poblacional; capas de equipamientos públicos; capas de tráfico histórico |
| **Periféricos** | Teclado ergonómico; mouse óptico de precisión; webcam 1080p; auriculares con micrófono; tablet gráfica (opcional, para anotaciones en mapas) |
| **Seguridad** | BitLocker/LUKS; autenticación; backup automático de proyectos GIS a NAS o cloud; control de versiones de archivos de ruta |
| **Alimentación** | 100-240V AC; fuente de poder ≥ 500 W; conexión a UPS central 5 KVA |
| **Temperatura operación** | 0°C a +35°C |
| **Humedad** | 20% a 80% RH |
| **Certificaciones** | CE; FCC; Energy Star; RETIE |
| **Dimensiones** | Escritorio estándar; computador SFF o tower ≈ 200 × 400 × 400 mm |
| **Peso** | ≤ 12 kg (incluye computador, 2 monitores) |
| **Accesorios** | Cable DisplayPort/HDMI 2 m (2 unidades); cable de red CAT6 2 m; manual de GIS; licencias de software; datos espaciales de Sincelejo |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-05-01 | Diseñar y modificar rutas sobre mapa base de Sincelejo | Obligatorio |
| RF-CCO-05-02 | Calcular distancias, tiempos de ciclo, y velocidades promedio por segmento | Obligatorio |
| RF-CCO-05-03 | Definir y geocodificar paradas (coordenadas lat/lon) | Obligatorio |
| RF-CCO-05-04 | Programar frecuencias por franja horaria y día de la semana | Obligatorio |
| RF-CCO-05-05 | Simular desvíos por obras, eventos, o emergencias | Obligatorio |
| RF-CCO-05-06 | Analizar cobertura del sistema (áreas sin servicio a 400 m) | Obligatorio |
| RF-CCO-05-07 | Generar archivos de ruta para carga en SGCF (geocercas) | Obligatorio |
| RF-CCO-05-08 | Importar/exportar datos en formatos estándar (GeoJSON, Shapefile, KML, GPX) | Obligatorio |
| RF-CCO-05-09 | Realizar análisis de red (camino más corto, áreas de influencia) | Deseable |
| RF-CCO-05-10 | Integrar datos de demanda (conteo de pasajeros) para optimización de frecuencias | Deseable |
| RF-CCO-05-11 | Generar mapas de calidad de servicio (velocidad comercial, tiempo de espera) | Deseable |
| RF-CCO-05-12 | Mantener historial de versiones de rutas (control de cambios) | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-05-01 | Tiempo de arranque | < 30 segundos |
| RNF-CCO-05-02 | Tiempo de apertura de proyecto GIS | < 20 segundos |
| RNF-CCO-05-03 | Tiempo de cálculo de ruta | < 10 segundos para ruta de 10 km |
| RNF-CCO-05-04 | RAM disponible | ≥ 16 GB libres con GIS abierto |
| RNF-CCO-05-05 | Resolución de monitores | 1920×1080 @ 60 Hz cada uno |
| RNF-CCO-05-06 | Precisión de geocodificación | < 5 metros |
| RNF-CCO-05-07 | MTBF | ≥ 50.000 horas |
| RNF-CCO-05-08 | Consumo | ≤ 250 W (typical); ≤ 350 W (peak) |
| RNF-CCO-05-09 | Temperatura operación | 0°C a +35°C |
| RNF-CCO-05-10 | Almacenamiento de proyectos | ≥ 100 GB disponibles para datos GIS |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Tiempo de diseño de nueva ruta | < 2 horas | Desde requerimiento hasta archivo generado |
| Tiempo de cálculo de ruta | < 10 seg | Para ruta de 10 km con 20 paradas |
| Precisión de geocodificación | < 5 m | Comparación con GPS de referencia |
| Satisfacción de planeador | ≥ 4.0/5 | Encuesta mensual |
| Fallas de hardware | < 1 por año | Incidencias reportadas |
| Tiempo de respaldo de proyectos | < 5 min | Backup diario automático |


---

## 9.17 CC-CCO-06: Antena de Inicialización SAM

La Antena de Inicialización SAM es el componente de seguridad criptográfica que custodia las claves de acceso a las tarjetas Mifare del sistema. Instalada en cada estación de inicialización de tarjetas (CC-CCO-04), esta antena con módulo SAM permite realizar operaciones de autenticación, lectura, y escritura segura en las tarjetas de recaudo.

El SAM (Secure Access Module) es un chip criptográfico seguro que almacena las claves maestras del sistema de tarjetas. Cuando una tarjeta nueva se emite, el SAM autentica la tarjeta con un desafío-respuesta criptográfica, verifica que la tarjeta sea genuina (no clonada), y escribe el saldo inicial en sectores protegidos. Cuando una tarjeta se recarga, el SAM autentica la tarjeta, verifica la integridad de los datos almacenados (checksum), y actualiza el saldo de forma atómica (evitando inconsistencias ante interrupciones).

La antena SAM opera a la frecuencia estándar de 13.56 MHz (ISO 14443A/B), con un alcance de lectura/escritura de 0-10 cm. La conexión al computador de inicialización se realiza mediante USB, con drivers y SDK proporcionados por el fabricante. El SAM es físicamente extraíble, permitiendo la rotación de claves maestras en caso de compromiso de seguridad: si se sospecha que las claves han sido filtradas, el SAM puede reemplazarse por uno nuevo con claves regeneradas, y todas las tarjetas pueden re-emisionarse con las nuevas claves.

### Justificación Estratégica

La seguridad del sistema de tarjetas es fundamental para la viabilidad financiera del SETP. Si un atacante logra clonar tarjetas o manipular saldos, el sistema de recaudo se vuelve inseguro y la confianza de los usuarios se destruye. El SAM es el componente que garantiza que solo tarjetas auténticas y no manipuladas sean aceptadas por los validadores.

La experiencia de sistemas de transporte público en Colombia y Latinoamérica demuestra que los ataques a sistemas de tarjetas sin SAM son relativamente comunes: lectores de tarjetas clonadas, escritura de saldos arbitrarios, y replicación de tarjetas de cortesía. Un sistema con SAM bien implementado (con claves diversificadas por tarjeta, autenticación mutua, y criptogramas de transacción) es prácticamente invulnerable a estos ataques básicos.

La capacidad de rotación de claves mediante reemplazo de SAM es un mecanismo de recuperación ante desastres de seguridad: si las claves maestras se comprometen (por filtración interna, robo de dispositivo, o ingeniería inversa), el sistema puede regenerar claves y emitir nuevos SAMs sin necesidad de reemplazar toda la infraestructura de validadores. Solo las tarjetas de los usuarios necesitan re-emisionarse, lo cual es manejable en una flota de 34 buses.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-06 |
| **Nombre** | Antena de Inicialización SAM |
| **Subsistema** | CCO — Seguridad de Medios de Pago; SST — Criptografía |
| **Cantidad** | 4 unidades (2 por estación de inicialización) |
| **Tipo** | Lector/escritor Mifare con SAM integrado; formato escritorio USB |
| **Frecuencia** | 13.56 MHz; ISO 14443A/B |
| **Tarjetas soportadas** | Mifare Classic 1K/4K; Mifare DESFire EV1/EV2/EV3; NFC Forum Type 1-4 |
| **SAM** | 4 ranuras SAM ISO 7816; compatible con Mifare SAM AV3; soporta AES-128, DES, 3DES; capacidad de almacenamiento de claves ≥ 32 entradas |
| **Alcance** | 0-10 cm (depende de la tarjeta y la antena) |
| **Velocidad** | Lectura/escritura ≥ 106 kbps (Mifare Classic); ≥ 848 kbps (DESFire) |
| **Conectividad** | USB 2.0 Full Speed; drivers para Windows, Linux, macOS; SDK para desarrollo (.NET, Java, C++, Python) |
| **Indicación** | LED de estado: verde=lectura OK, rojo=error, azul=SAM activo |
| **Seguridad física** | Carcasa ABS resistente; cable USB blindado; soporte antideslizante |
| **Alimentación** | 5V DC vía USB; consumo ≤ 500 mA |
| **Temperatura operación** | 0°C a +50°C |
| **Humedad** | 10% a 90% RH |
| **Certificaciones** | CE; FCC; RETIE; EMV CoM (if applicable) |
| **Dimensiones** | ≈ 100 × 80 × 25 mm |
| **Peso** | ≤ 200 g |
| **Accesorios** | Cable USB 1.5 m; manual de programación; SDK y ejemplos de código; tarjetas de prueba (10 unidades); tarjeta de configuración SAM |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-06-01 | Autenticar tarjetas Mifare con desafío-respuesta criptográfica | Obligatorio |
| RF-CCO-06-02 | Leer y escribir saldo en sectores protegidos de tarjetas | Obligatorio |
| RF-CCO-06-03 | Verificar autenticidad de tarjeta (anti-clonación) | Obligatorio |
| RF-CCO-06-04 | Soportar diversificación de claves por tarjeta | Obligatorio |
| RF-CCO-06-05 | Generar criptogramas de transacción (integridad y no repudio) | Obligatorio |
| RF-CCO-06-06 | Permitir rotación de claves maestras mediante reemplazo de SAM | Obligatorio |
| RF-CCO-06-07 | Soportar Mifare Classic y DESFire | Obligatorio |
| RF-CCO-06-08 | Operar con 4 SAMs simultáneos (para múltiples aplicaciones o redundancia) | Obligatorio |
| RF-CCO-06-09 | Registrar auditoría de todas las operaciones criptográficas | Obligatorio |
| RF-CCO-06-10 | Soportar actualización de firmware del SAM | Deseable |
| RF-CCO-06-11 | Proporcionar SDK para integración con software de gestión de tarjetas | Obligatorio |
| RF-CCO-06-12 | Emitir alerta ante intento de autenticación fallida repetida | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-06-01 | Tiempo de autenticación | < 200 ms |
| RNF-CCO-06-02 | Tiempo de lectura/escritura de saldo | < 300 ms |
| RNF-CCO-06-03 | MTBF | ≥ 100.000 horas |
| RNF-CCO-06-04 | Consumo | ≤ 500 mA @ 5V |
| RNF-CCO-06-05 | Alcance de lectura | 0-10 cm |
| RNF-CCO-06-06 | Temperatura operación | 0°C a +50°C |
| RNF-CCO-06-07 | Tiempo de vida del SAM | ≥ 10 años (ciclos de escritura limitados por diseño) |
| RNF-CCO-06-08 | Resistencia a manipulación física | Tamper-evident; destrucción de claves ante apertura no autorizada |
| RNF-CCO-06-09 | Cumplimiento criptográfico | FIPS 140-2 Nivel 2 (SAM) o equivalente |
| RNF-CCO-06-10 | Velocidad de comunicación USB | USB 2.0 Full Speed (12 Mbps) |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Tiempo de autenticación | < 200 ms | Promedio en 1000 autenticaciones |
| Tasa de autenticaciones fallidas | < 0.1% | Fallidas / total intentos |
| Tiempo de lectura/escritura | < 300 ms | Promedio en 1000 operaciones |
| Disponibilidad | ≥ 99.5% | Tiempo operativo / total |
| Incidentes de seguridad (clonación, manipulación) | 0 | Incidentes confirmados por año |
| Tiempo de rotación de claves | < 1 día | Desde decisión hasta nueva clave activa |


---

## 9.18 CC-CCO-07: UPS Online 5 KVA

El UPS (Uninterruptible Power Supply) Online de 5 KVA es el sistema de respaldo de energía eléctrica del CCO. Proporciona alimentación ininterrumpida a todos los equipos críticos del centro de control (computadoras, video wall, switch de red, servidores locales) ante fallas de la red eléctrica comercial, fluctuaciones de voltaje, o transientes.

A diferencia de los UPS de tipo línea interactiva o standby, el UPS online de doble conversión proporciona una alimentación completamente aislada de la red comercial: la corriente AC de entrada se convierte a DC, carga las baterías, y luego se convierte nuevamente a AC de salida con onda sinusoidal pura. Esto elimina cualquier ruido, fluctuación, o transientes de la red comercial, proporcionando una energía "limpia" y estable a los equipos sensibles del CCO.

El UPS de 5 KVA / 4.5 KW proporciona suficiente potencia para alimentar todas las estaciones de trabajo (5 puestos × 200 W = 1000 W), el video wall (4 TVs × 150 W = 600 W), el switch de red (50 W), el controlador de video wall (100 W), el NVR (100 W), y servidores locales (500 W), totalizando aproximadamente 2350 W. Con una carga del 50%, el UPS puede proporcionar autonomía de ≥ 30 minutos.

### Justificación Estratégica

El CCO es el cerebro operativo del SETP: sin CCO, no hay supervisión de flota, no hay control de recaudo, no hay respuesta a emergencias. Una falla de energía eléctrica que deje el CCO sin operación por más de unos minutos puede causar: pérdida de visibilidad de la flota (buses operando "a ciegas"); interrupción del recaudo en tiempo real; imposibilidad de responder a botones de pánico; y pérdida de datos no guardados en las estaciones de trabajo.

El UPS online de doble conversión es la tecnología de elección para centros de control críticos porque: (1) proporciona aislamiento total de la red comercial; (2) la transición a batería es instantánea (0 ms); (3) la onda sinusoidal pura de salida es compatible con fuentes de poder activas (PFC) de computadoras modernas; (4) la capacidad de 5 KVA permite expansión futura sin reemplazo del UPS.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-07 |
| **Nombre** | UPS Online 5 KVA |
| **Subsistema** | CCO — Energía de Respaldo |
| **Cantidad** | 1 unidad |
| **Tipo** | UPS online de doble conversión (double conversion) |
| **Potencia aparente** | 5 KVA |
| **Potencia activa** | 4.5 KW (factor de potencia 0.9) |
| **Entrada** | 110-240V AC monofásico; frecuencia 50/60 Hz auto-sensing; rango de voltaje de entrada ± 20% sin uso de batería |
| **Salida** | 110-240V AC monofásico; onda sinusoidal pura; THD < 3%; regulación de voltaje ± 1% |
| **Batería** | Baterías selladas de plomo-ácido (VRLA) o litio-ferrofosfato (LiFePO4); voltaje 48V o 192V DC; autonomía ≥ 30 minutos al 50% de carga |
| **Autonomía** | ≥ 30 minutos al 50% de carga; ≥ 15 minutos al 100% de carga |
| **Tiempo de transferencia** | 0 ms (online double conversion) |
| **Eficiencia** | ≥ 90% en modo normal; ≥ 95% en modo eco (si soporta) |
| **Protección** | Sobrecarga, cortocircuito, sobretensión, subtensión, frecuencia fuera de rango; bypass estático automático; protección térmica |
| **Indicación** | Pantalla LCD con: voltaje entrada/salida, frecuencia, carga %, batería %, tiempo restante, modo de operación, alarmas |
| **Comunicación** | Puerto USB; RS-232; slot para tarjeta SNMP (opcional); software de gestión y monitoreo; notificación por email/SMS de eventos |
| **Temperatura operación** | 0°C a +40°C |
| **Humedad** | 0% a 95% RH (sin condensación) |
| **Protección** | IP20; gabinete metálico con ventilación forzada; rack 19" 6U o torre independiente |
| **Certificaciones** | CE; UL; RETIE; ISO 9001; IEC 62040-1; IEC 62040-2 |
| **Dimensiones** | Rack 19" 6U: ≈ 265 × 430 × 600 mm; o torre: ≈ 400 × 200 × 500 mm |
| **Peso** | ≤ 60 kg (incluye baterías) |
| **Accesorios** | Cable de entrada AC; cable de distribución AC; software de gestión; manual de usuario; baterías de repuesto (opcional); tarjeta SNMP (opcional); kit de rack 19" |
| **Mantenimiento** | Baterías reemplazables en campo; vida útil VRLA ≥ 3-5 años; LiFePO4 ≥ 10 años; prueba automática de baterías periódica |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-07-01 | Proporcionar alimentación ininterrumpida ante falla de red comercial | Obligatorio |
| RF-CCO-07-02 | Aislar equipos de fluctuaciones y transientes de la red | Obligatorio |
| RF-CCO-07-03 | Proporcionar autonomía ≥ 30 minutos al 50% de carga | Obligatorio |
| RF-CCO-07-04 | Regulación de voltaje de salida ± 1% independiente de entrada | Obligatorio |
| RF-CCO-07-05 | Generar onda sinusoidal pura (THD < 3%) | Obligatorio |
| RF-CCO-07-06 | Proporcionar bypass estático automático ante falla interna del UPS | Obligatorio |
| RF-CCO-07-07 | Monitorear estado y enviar alertas (email/SMS) | Obligatorio |
| RF-CCO-07-08 | Soportar apagado ordenado de servidores y estaciones de trabajo | Obligatorio |
| RF-CCO-07-09 | Permitir prueba de baterías sin interrumpir alimentación | Obligatorio |
| RF-CCO-07-10 | Soportar expansión de autonomía con baterías adicionales | Deseable |
| RF-CCO-07-11 | Operar en modo eco para mejorar eficiencia en cargas bajas | Deseable |
| RF-CCO-07-12 | Integrar con sistema de monitoreo del CCO (SNMP, API) | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-07-01 | Tiempo de transferencia | 0 ms (double conversion) |
| RNF-CCO-07-02 | Eficiencia en modo normal | ≥ 90% |
| RNF-CCO-07-03 | THD de salida | < 3% |
| RNF-CCO-07-04 | Regulación de voltaje | ± 1% |
| RNF-CCO-07-05 | Autonomía al 50% carga | ≥ 30 minutos |
| RNF-CCO-07-06 | Autonomía al 100% carga | ≥ 15 minutos |
| RNF-CCO-07-07 | MTBF | ≥ 100.000 horas |
| RNF-CCO-07-08 | Vida útil de baterías VRLA | ≥ 3-5 años |
| RNF-CCO-07-09 | Vida útil de baterías LiFePO4 | ≥ 10 años |
| RNF-CCO-07-10 | Tiempo de recarga de baterías | < 4 horas al 90% |
| RNF-CCO-07-11 | Nivel sonoro | < 55 dB(A) a 1 m |
| RNF-CCO-07-12 | Temperatura operación | 0°C a +40°C |
| RNF-CCO-07-13 | Capacidad de carga | ≥ 4.5 KW activos |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad del UPS | ≥ 99.9% | Tiempo operativo / total |
| Tiempo de autonomía en falla | ≥ 30 min @ 50% carga | Prueba mensual de descarga |
| Eficiencia energética | ≥ 90% | Medición de entrada vs. salida |
| THD de salida | < 3% | Medición con analizador de potencia |
| Temperatura de baterías | < 35°C | Sensores internos |
| Tiempo de respuesta a falla de red | 0 ms | Monitoreo continuo |
| Eventos de falla de batería | 0 no planificados | Incidencias reportadas |
| Satisfacción de operación | 100% | Sin interrupciones perceptibles por usuarios |


---

## 9.19 CC-CCO-08: Switch Gigabit Administrable Capa 3

El Switch Gigabit Administrable Capa 3 es el componente central de red del CCO. Interconecta todas las estaciones de trabajo, el video wall, los servidores, el NVR, y proporciona conectividad hacia el router/firewall de borde y la conexión a internet dedicada.

A diferencia de un switch no administrable (plug-and-play), el switch administrable Capa 3 permite: configuración de VLANs (Virtual LANs) para segmentar la red en zonas de seguridad (red de operadores, red de administración, red de CCTV, red de invitados); aplicación de QoS (Quality of Service) para priorizar tráfico crítico (botones de pánico, recaudo) sobre tráfico menos prioritario (WiFi de invitados, actualizaciones); implementación de ACLs (Access Control Lists) para restringir qué dispositivos pueden comunicarse entre sí; spanning tree para prevención de bucles de red; y monitoreo SNMP para gestión centralizada.

La capacidad de PoE+ (Power over Ethernet Plus) en 24 puertos permite alimentar directamente dispositivos PoE del CCO (cámaras CCTV, access points WiFi, paneles de video wall con PoE) sin necesidad de fuentes de poder individuales. Esto simplifica la instalación, reduce el cableado de alimentación, y facilita la gestión centralizada de energía.

### Justificación Estratégica

La red del CCO es la infraestructura de comunicación que permite que todos los sistemas ITS funcionen de manera integrada. Un switch no administrable sería insuficiente porque: (1) no permite segmentación de red, exponiendo todos los dispositivos a un mismo dominio de broadcast (ineficiente e inseguro); (2) no permite priorización de tráfico, lo que significa que un stream de CCTV puede saturar el ancho de banda y retrasar alertas de botón de pánico; (3) no permite control de acceso, permitiendo que cualquier dispositivo conectado acceda a cualquier otro; (4) no permite diagnóstico, dificultando la identificación de fallas de red.

El switch Capa 3 es especialmente valioso para la segmentación de red: la red de operadores (estaciones de trabajo, video wall) puede estar en una VLAN; la red de CCTV (cámaras, NVR) en otra; la red de servidores (bases de datos, APIs) en otra; y la red de invitados (WiFi para visitantes) en otra. El firewall entre VLANs puede restringir que las cámaras CCTV (potencialmente vulnerables) accedan a las bases de datos de recaudo, o que la red de invitados acceda a cualquier sistema interno.

La capacidad de 4 puertos SFP+ (10 Gbps) proporciona enlaces de alta velocidad hacia el core de la red o hacia el servidor de almacenamiento (NAS/SAN), permitiendo transferencias rápidas de grandes volúmenes de datos (backups de video, sincronización de bases de datos). La conectividad 10G es una inversión a futuro que garantiza que la red del CCO no sea un cuello de botella si el sistema crece en los próximos años.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-08 |
| **Nombre** | Switch Gigabit Administrable Capa 3 |
| **Subsistema** | CCO — Infraestructura de Red |
| **Cantidad** | 1 unidad |
| **Tipo** | Switch administrable Layer 3; rack 19" |
| **Puertos Ethernet** | 24 puertos RJ-45 10/100/1000 Mbps (Gigabit); auto-MDI/MDIX; auto-negociación |
| **Puertos SFP+** | 4 puertos SFP+ 10 Gbps (para uplink o fibra) |
| **PoE** | 24 puertos PoE+ (802.3at) hasta 30 W por puerto; potencia total PoE ≥ 370 W; soporte PoE (802.3af) y PoE+ (802.3at) |
| **Capacidad de switching** | ≥ 128 Gbps (non-blocking) |
| **Capacidad de forwarding** | ≥ 95 Mpps (millones de paquetes por segundo) |
| **VLAN** | 802.1Q; VLAN tagging; VLAN por puerto; VLAN trunking; soporte para ≥ 4094 VLANs; protocolo GVRP (opcional) |
| **Routing** | Routing estático; RIPv2; OSPF básico; VRRP/HSRP (redundancia de gateway); inter-VLAN routing (Capa 3) |
| **QoS** | Clasificación por puerto, VLAN, DSCP, 802.1p; colas de prioridad (≥ 8 queues); policing y shaping; WRR, SP, WFQ |
| **ACLs** | ACLs basadas en MAC, IP, puerto, protocolo; ACLs por VLAN; soporte IPv4 e IPv6 |
| **Seguridad** | 802.1X (autenticación de puerto); RADIUS; TACACS+; port security (MAC binding); DHCP snooping; dynamic ARP inspection; IP source guard; storm control; loopback detection |
| **Spanning Tree** | STP, RSTP, MSTP; BPDU guard; root guard; loop guard |
| **Monitoreo** | SNMP v1/v2c/v3; RMON (grupos 1, 2, 3, 9); syslog; sFlow/NetFlow (opcional); CLI (SSH/Telnet); interfaz web (HTTP/HTTPS) |
| **Alimentación** | 100-240V AC; doble fuente de poder (redundante) opcional; consumo ≤ 50 W (sin PoE); ≤ 450 W (con PoE máximo) |
| **Temperatura operación** | 0°C a +45°C |
| **Humedad** | 10% a 90% RH |
| **Protección** | IP20; rack 19" 1U; ventilación frontal-trasera; ventiladores redundantes (si aplica) |
| **Certificaciones** | CE; FCC; RETIE; IEEE 802.3 (todos los estándares relevantes); RoHS |
| **Dimensiones** | Rack 19" 1U; ≈ 44 × 440 × 330 mm (alto × ancho × profundidad) |
| **Peso** | ≤ 5 kg |
| **Accesorios** | Cable de alimentación AC; kit de rack 19" (rieles); cable de consola RJ-45 a USB; manual de configuración; software de gestión (opcional) |
| **Garantía** | ≥ 3 años de garantía del fabricante; soporte técnico 24/7 (opcional) |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-08-01 | Interconectar todas las estaciones de trabajo del CCO | Obligatorio |
| RF-CCO-08-02 | Conectar video wall, NVR, servidores, y router de borde | Obligatorio |
| RF-CCO-08-03 | Segmentar red en VLANs (operadores, CCTV, servidores, invitados) | Obligatorio |
| RF-CCO-08-04 | Implementar inter-VLAN routing con ACLs de seguridad | Obligatorio |
| RF-CCO-08-05 | Aplicar QoS para priorizar tráfico de emergencia y recaudo | Obligatorio |
| RF-CCO-08-06 | Alimentar dispositivos PoE (cámaras, APs) directamente | Obligatorio |
| RF-CCO-08-07 | Prevenir bucles de red con Spanning Tree | Obligatorio |
| RF-CCO-08-08 | Monitorear tráfico y estado por SNMP/syslog | Obligatorio |
| RF-CCO-08-09 | Soportar autenticación 802.1X en puertos de acceso | Obligatorio |
| RF-CCO-08-10 | Proporcionar uplink 10G para expansión futura | Deseable |
| RF-CCO-08-11 | Soportar IPv6 para futura migración | Deseable |
| RF-CCO-08-12 | Operar con doble fuente de poder para redundancia | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-08-01 | Capacidad de switching | ≥ 128 Gbps non-blocking |
| RNF-CCO-08-02 | Forwarding rate | ≥ 95 Mpps |
| RNF-CCO-08-03 | Latencia de switching | < 10 μs |
| RNF-CCO-08-04 | PoE total disponible | ≥ 370 W |
| RNF-CCO-08-05 | PoE por puerto | ≥ 30 W (802.3at) |
| RNF-CCO-08-06 | MTBF | ≥ 200.000 horas |
| RNF-CCO-08-07 | Consumo (sin PoE) | ≤ 50 W |
| RNF-CCO-08-08 | Consumo (con PoE máximo) | ≤ 450 W |
| RNF-CCO-08-09 | Temperatura operación | 0°C a +45°C |
| RNF-CCO-08-10 | Nivel sonoro | < 40 dB(A) a 1 m |
| RNF-CCO-08-11 | VLANs soportadas | ≥ 4094 |
| RNF-CCO-08-12 | ACLs soportadas | ≥ 1000 entradas |
| RNF-CCO-08-13 | Tiempo de conmutación STP | < 2 segundos (RSTP) |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad | ≥ 99.9% | Tiempo operativo / total |
| Utilización de CPU | < 50% | Promedio en horas pico |
| Utilización de memoria | < 70% | Promedio en horas pico |
| Tráfico total por puerto | < 80% de capacidad | Monitoreo continuo |
| Errores de CRC/paquetes | < 0.001% | Errores / total paquetes |
| Tiempo de respuesta SNMP | < 500 ms | Consulta de estado |
| Eventos de seguridad (acceso no autorizado) | 0 | Incidentes reportados |
| Fallas de PoE | < 0.1% | Dispositivos PoE sin alimentación / total |


---

## 9.20 CC-CCO-09: Rack 19" 42U

El Rack 19" 42U es el gabinete de suelo que aloja y organiza los equipos de red, servidores, y sistemas de energía del CCO. Proporciona una estructura física estandarizada para montar equipos en formato rack, facilitando la organización, ventilación, cableado, y mantenimiento de la infraestructura tecnológica.

El rack de 42 unidades de rack (42U) es una altura estándar de data center que proporciona suficiente espacio para: el switch de red (1U), el controlador de video wall (1-2U), el NVR (1-2U), servidores locales (1-4U), el UPS (6U), regletas de distribución de energía (PDU) (1-2U), y espacio libre para expansión futura. La profundidad del rack (≥ 800 mm) debe acomodar servidores de profundidad estándar y proporcionar espacio para gestión de cables en la parte trasera.

El rack incluye: puertas delanteras y traseras (perforadas o con malla para ventilación); paneles laterales removibles; ruedas para movilidad; sistema de gestión de cables vertical y horizontal; bandejas de ventilación; y puntos de aterrizaje eléctrico. La construcción de acero laminado en frío con acabado en pintura electrostática proporciona rigidez y durabilidad.

### Justificación Estratégica

El rack es el "esqueleto" de la infraestructura del CCO: sin un rack adecuado, los equipos de red y servidores se instalan en superficies dispersas, acumulan polvo, sufren de sobrecalentamiento por falta de flujo de aire organizado, y el cableado se convierte en un caos imposible de mantener. La organización en rack facilita: (1) la ventilación controlada (flujo de aire frontal-trasero, posiblemente con ventiladores de rack); (2) la gestión de cables (bandejas y anillos organizan los cables de red y energía); (3) la seguridad física (puertas con cerradura previenen acceso no autorizado); (4) la mantenibilidad (equipos deslizables en rieles permiten extracción para reparación sin desconectar cables); (5) la estética profesional (un CCO ordenado transmite confianza a visitantes y auditores).

La elección de 42U (altura completa de data center) puede parecer excesiva para un CCO de 34 buses, pero proporciona espacio de expansión para futuros servidores, sistemas de almacenamiento, o equipos de telecomunicaciones adicionales. Es más económico instalar un rack grande desde el principio que reemplazar un rack pequeño en el futuro. Adicionalmente, el espacio libre en el rack puede utilizarse para instalar un sistema de monitoreo ambiental (sensores de temperatura, humedad, humo) y un sistema de supresión de incendios (extintor de gas limpio, si aplica).

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-09 |
| **Nombre** | Rack 19" 42U |
| **Subsistema** | CCO — Infraestructura Física |
| **Cantidad** | 1 unidad |
| **Tipo** | Gabinete de suelo (floor-standing rack); 19" estándar |
| **Altura** | 42 U (1 U = 44.45 mm); altura total ≈ 2050-2100 mm |
| **Ancho** | 600 mm (estándar) o 800 mm (para cableado lateral generoso) |
| **Profundidad** | ≥ 800 mm (para servidores de profundidad estándar y gestión de cables trasera) |
| **Carga máxima** | ≥ 800 kg (estática); ≥ 600 kg (dinámica con ruedas) |
| **Material** | Acero laminado en frío (SPCC); espesor ≥ 1.2 mm; acabado en pintura electrostática gris o negra |
| **Puertas** | Puerta delantera: vidrio templado o acero perforado con cerradura; puerta trasera: acero perforado con cerradura; ambas removibles |
| **Paneles laterales** | Removibles; con cerradura o tornillos rápidos; para acceso lateral al cableado |
| **Ruedas** | 4 ruedas giratorias con freno; capacidad ≥ 800 kg; ruedas de poliuretano para piso técnico o estándar |
| **Gestión de cables** | 2× canaletas verticales con tapas (lateral izquierdo y derecho); anillos de gestión de cables horizontales (≥ 4 unidades); bandejas de pasacables (≥ 2 unidades) |
| **Ventilación** | Techo con ventiladores de extracción (opcional, 2-4 unidades); fondo con entrada de aire; flujo de aire frontal-trasero |
| **Aterrizaje** | Barra de aterrizaje (ground bar) en parte posterior; conexión a sistema de puesta a tierra del edificio (≤ 5 Ω) |
| **PDU (Power Distribution Unit)** | 2× PDU verticales de 16-20 tomas cada una; con interruptor de circuito; protección contra sobrecorriente; montaje en 0U (en canaleta vertical) |
| **Accesorios** | 2× bandejas fijas (1U o 2U) para equipos no rackables; 2× juegos de rieles deslizables (para servidores); kit de tornillos y tuercas enjauladas (50 unidades); nivel de burbuja |
| **Temperatura operación** | 0°C a +40°C (ambiente del CCO) |
| **Humedad** | 10% a 80% RH |
| **Certificaciones** | CE; RETIE; EIA-310-D (estándar de rack 19") |
| **Dimensiones** | ≈ 600/800 × 2050 × 800/1000 mm (ancho × alto × profundidad) |
| **Peso** | ≤ 100 kg (vacío) |
| **Accesorios opcionales** | Panel en blanco (1U, 2U) para tapar espacios vacíos; bandeja de teclado y mouse (1U); cajón de herramientas (2U); sensor de temperatura/humedad; ventiladores de rack; lámpara LED interior |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-09-01 | Alojar switch, controlador de video wall, NVR, servidores, UPS | Obligatorio |
| RF-CCO-09-02 | Proporcionar gestión organizada de cables de red y energía | Obligatorio |
| RF-CCO-09-03 | Permitir ventilación frontal-trasera para equipos | Obligatorio |
| RF-CCO-09-04 | Incluir cerraduras en puertas y paneles para seguridad física | Obligatorio |
| RF-CCO-09-05 | Soportar carga de todos los equipos montados (≥ 500 kg) | Obligatorio |
| RF-CCO-09-06 | Incluir PDU para distribución de energía a equipos | Obligatorio |
| RF-CCO-09-07 | Proporcionar punto de aterrizaje eléctrico | Obligatorio |
| RF-CCO-09-08 | Permitir acceso fácil para mantenimiento (puertas/paneles removibles) | Obligatorio |
| RF-CCO-09-09 | Incluir ruedas para movilidad dentro del CCO | Deseable |
| RF-CCO-09-10 | Proporcionar espacio para expansión futura (≥ 20% libre) | Obligatorio |
| RF-CCO-09-11 | Soportar accesorios de bandejas, rieles, y cajones | Deseable |
| RF-CCO-09-12 | Ser compatible con estándar 19" EIA-310-D | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-09-01 | Carga máxima | ≥ 800 kg estática |
| RNF-CCO-09-02 | Carga dinámica (con ruedas) | ≥ 600 kg |
| RNF-CCO-09-03 | Espesor de acero | ≥ 1.2 mm |
| RNF-CCO-09-04 | Temperatura ambiente soportada | 0°C a +40°C |
| RNF-CCO-09-05 | Resistencia a corrosión | Acabado epoxi/pintura electrostática; resistente a humedad |
| RNF-CCO-09-06 | Tiempo de montaje de equipos | < 2 horas para configuración inicial |
| RNF-CCO-09-07 | Tiempo de acceso para mantenimiento | < 5 minutos (remover panel/puerta) |
| RNF-CCO-09-08 | Nivel de ruido (ventiladores adicionales) | < 45 dB(A) si se instalan ventiladores |
| RNF-CCO-09-09 | Dimensiones estándar | EIA-310-D; 19" de ancho interno |
| RNF-CCO-09-10 | Profundidad útil | ≥ 800 mm (entre rieles frontales y traseros) |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Temperatura interior del rack | < 35°C | Sensores en entrada y salida de aire |
| Temperatura de equipos críticos | < 40°C | Sensores en switch, NVR, servidores |
| Organización de cables | ≥ 4.0/5 | Auditoría visual trimestral |
| Seguridad física | 100% | Cerraduras funcionando; acceso controlado |
| Capacidad de expansión | ≥ 20% U libre | Monitoreo mensual |
| Estabilidad mecánica | Sin vibración | Inspección visual |
| Satisfacción de técnicos | ≥ 4.0/5 | Encuesta de facilidad de mantenimiento |


---

## 9.21 CC-CCO-10: Puesto de Trabajo Ergonómico

El Puesto de Trabajo Ergonómico es el mobiliario donde el operador del CCO pasa 8-12 horas diarias supervisando el sistema ITS. Incluye una mesa ajustable en altura (sentado/de pie), una silla ergonómica con soporte lumbar ajustable, y un soporte dual para monitores que permite posicionar las pantallas a la altura y distancia óptima para la visión.

La mesa ajustable en altura (standing desk) permite al operador alternar entre postura sentada y de pie a lo largo del turno, reduciendo la fatiga muscular y mejorando la circulación. El ajuste puede ser manual (manivela) o eléctrico (motor silencioso con memoria de posiciones). El soporte dual para monitores VESA monta dos pantallas de 27" en brazos articulados que permiten ajustar la altura, inclinación, rotación, y distancia de cada monitor independientemente.

La silla ergonómica incluye: respaldo con soporte lumbar ajustable; apoyabrazos ajustables en altura y ángulo; asiento con profundidad ajustable; reclinación con tensión ajustable; y base de 5 ruedas con gas lift para ajuste de altura. El tapizado de tela mesh respirable reduce la acumulación de calor en climas cálidos como Sincelejo.

La iluminación LED de escritorio proporciona luz direccional ajustable en intensidad y temperatura de color (cálida/fría), reduciendo el deslumbramiento de las pantallas y la fatiga visual. El cableado de la iluminación se integra con la gestión de cables de la mesa para mantener el área de trabajo ordenada.

### Justificación Estratégica

La ergonomía del puesto de trabajo es un factor crítico de productividad y salud ocupacional que a menudo se subestima en proyectos tecnológicos. Los operadores del CCO pasan largas horas frente a múltiples pantallas, en turnos rotativos que incluyen noches y fines de semana. Un puesto de trabajo mal diseñado causa: fatiga visual (monitores mal posicionados); dolor de cuello y espalda (silla sin soporte lumbar, mesa a altura incorrecta); síndrome del túnel carpiano (teclado y mouse mal posicionados); y fatiga general (postura estática prolongada).

Estudios de ergonomía laboral demuestran que la inversión en mobiliario ergonómico reduce la ausentismo por enfermedad en un 20-30% y mejora la productividad en un 10-15%. Para un CCO con 5 operadores en turnos rotativos, la mejora en productividad y reducción de ausentismo se traduce en una operación más confiable y personal más saludable y motivado.

La mesa ajustable en altura es particularmente valiosa en el contexto del CCO: durante una contingencia (botón de pánico activado), el operador puede ponerse de pie para tener mayor movilidad y acceso a múltiples pantallas y controles. Durante la operación normal, puede alternar entre sentado y de pie para mantenerse alerta. La capacidad de trabajar de pie también facilita la comunicación con colegas que se acercan al puesto.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-10 |
| **Nombre** | Puesto de Trabajo Ergonómico |
| **Subsistema** | CCO — Mobiliario y Ergonomía |
| **Cantidad** | 5 unidades (1 por puesto de operador) |
| **Mesa** | Mesa ajustable en altura; superficie ≥ 1200 × 700 mm; ajuste de altura 650-1250 mm (sentado a de pie); mecanismo eléctrico dual motor (silencioso, < 50 dB); velocidad de ajuste ≥ 25 mm/s; carga ≥ 100 kg; memoria de 3-4 posiciones; cableado organizado con canal inferior; material: tablero melaminado o MDF de alta densidad; cantos redondeados; acabado resistente a rayones y manchas |
| **Silla** | Silla ergonómica de oficina; respaldo alto con soporte lumbar ajustable; asiento con profundidad ajustable; apoyabrazos 4D (ajustables en altura, anchura, profundidad, ángulo); reclinación sincronizada con tensión ajustable; base de aluminio pulido con 5 ruedas de poliuretano; gas lift clase 4; tapizado mesh respirable (espalda) y tela acolchada (asiento); capacidad de carga ≥ 120 kg; certificación ergonómica BIFMA X5.1 |
| **Soporte dual monitores** | Brazo articulado dual VESA; soporta 2 monitores 27"; capacidad por brazo ≥ 9 kg; ajuste de altura, inclinación (± 90°), rotación (± 180°), ángulo (± 45°); montaje en mesa mediante abrazadera o pasante; gestión de cables integrada en brazos; mecanismo de contrapeso o resorte a gas para movimiento suave |
| **Iluminación** | Lámpara LED de escritorio; brazo articulado; intensidad ajustable (≥ 500 lux a 40 cm); temperatura de color ajustable (2700K-6500K); bajo consumo (≤ 10 W); sin parpadeo (flicker-free); sin deslumbramiento (UGR < 19); montaje en mesa o integrado en soporte de monitores |
| **Accesorios** | Tapete de mouse ergonómico; reposamuñecas para teclado; organizador de cables para escritorio; bandeja para CPU bajo mesa (opcional) |
| **Temperatura operación** | 0°C a +40°C (ambiente del CCO) |
| **Certificaciones** | Mesa: certificación eléctrica RETIE (si motorizado); CE. Silla: BIFMA X5.1; certificación ergonómica. Soporte: certificación de carga |
| **Dimensiones (mesa)** | 1200 × 700 × 650-1250 mm (ancho × profundidad × altura ajustable) |
| **Peso (mesa)** | ≤ 40 kg |
| **Dimensiones (silla)** | Asiento: 500 × 500 mm; respaldo: 500 × 600 mm; altura ajustable: 450-550 mm |
| **Peso (silla)** | ≤ 20 kg |
| **Garantía** | Mesa: ≥ 5 años (mecanismo y motor); Silla: ≥ 5 años (estructura), ≥ 2 años (tapizado); Soporte: ≥ 3 años |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-10-01 | Soportar 2 monitores de 27" en posición ergonómica | Obligatorio |
| RF-CCO-10-02 | Permitir ajuste de altura de mesa (sentado/de pie) | Obligatorio |
| RF-CCO-10-03 | Proporcionar soporte lumbar ajustable en silla | Obligatorio |
| RF-CCO-10-04 | Permitir ajuste de altura de asiento y apoyabrazos | Obligatorio |
| RF-CCO-10-05 | Proporcionar iluminación ajustable sin deslumbramiento | Obligatorio |
| RF-CCO-10-06 | Organizar cables de periféricos (teclado, mouse, iluminación) | Obligatorio |
| RF-CCO-10-07 | Soportar carga de computador, monitores, y periféricos (≥ 100 kg) | Obligatorio |
| RF-CCO-10-08 | Permitir rotación e inclinación independiente de cada monitor | Obligatorio |
| RF-CCO-10-09 | Ser operable en silencio (motores, mecanismos) | Obligatorio |
| RF-CCO-10-10 | Facilitar limpieza y mantenimiento (superficies resistentes) | Deseable |
| RF-CCO-10-11 | Soportar accesorios ergonómicos adicionales (reposapiés, cojines) | Deseable |
| RF-CCO-10-12 | Cumplir con normas de ergonomía laboral (BIFMA, ISO 9241) | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-10-01 | Rango de ajuste de altura de mesa | 650-1250 mm |
| RNF-CCO-10-02 | Velocidad de ajuste de altura | ≥ 25 mm/s |
| RNF-CCO-10-03 | Nivel sonoro de motores | < 50 dB(A) |
| RNF-CCO-10-04 | Carga máxima de mesa | ≥ 100 kg |
| RNF-CCO-10-05 | Carga máxima de silla | ≥ 120 kg |
| RNF-CCO-10-06 | Capacidad de soporte por brazo | ≥ 9 kg |
| RNF-CCO-10-07 | Intensidad de iluminación | ≥ 500 lux a 40 cm |
| RNF-CCO-10-08 | UGR (índice de deslumbramiento) | < 19 |
| RNF-CCO-10-09 | Temperatura de color ajustable | 2700K-6500K |
| RNF-CCO-10-10 | Tiempo de vida de LEDs | ≥ 50.000 horas |
| RNF-CCO-10-11 | Resistencia de tablero de mesa | ≥ 1000 g en test de caída de bola |
| RNF-CCO-10-12 | Estabilidad de mesa en altura máxima | Sin vibración con escritura/typing |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Satisfacción ergonómica del operador | ≥ 4.0/5 | Encuesta mensual (escala 1-5) |
| Ausentismo por molestias musculoesqueléticas | < 2% | Días de incapacidad / días laborables |
| Nivel de ruido de mesa eléctrica | < 50 dB(A) | Medición con sonómetro |
| Fallas mecánicas de mesa/silla | 0 en 2 años | Incidencias reportadas |
| Capacidad de carga verificada | ≥ 100 kg | Prueba de carga estática |
| Tiempo de ajuste de altura | < 10 seg | De sentado a de pie (o viceversa) |
| Estabilidad de monitores | Sin vibración | Observación visual durante operación |


---

## 9.22 CC-CCO-11: Cámaras CCTV del CCO

Las Cámaras CCTV del CCO son el componente de seguridad física que monitorea el interior del Centro de Control de Operaciones. Instaladas estratégicamente (4 unidades típicamente: entrada, área de operadores, área de servidores/rack, y zona de video wall), proporcionan vigilancia continua del espacio para: prevención de acceso no autorizado; documentación de incidentes; control de procedimientos; y seguridad del personal.

Las cámaras son del tipo domo IP de 4 megapíxeles, con lente varifocal motorizada (2.8-12 mm) que permite ajustar el ángulo de visión remotamente. La compresión H.265 optimiza el ancho de banda y almacenamiento. La visión nocturna mediante LED infrarrojo (IR) con alcance ≥ 30 metros permite vigilancia en condiciones de baja iluminación (durante la noche o si se apagan las luces principales). El soporte PoE (Power over Ethernet) simplifica la instalación al transmitir energía y datos por el mismo cable Ethernet.

Las cámaras se conectan al NVR (Network Video Recorder) del CCO o al switch PoE, y se integran con el sistema de videovigilancia general del SETP. El acceso remoto desde dispositivos autorizados permite al gerente de operaciones o al director de seguridad visualizar el CCO desde fuera de las instalaciones.

### Justificación Estratégica

El CCO alberga información crítica y sensible: datos de recaudo en tiempo real, posiciones de toda la flota, video de incidentes, y sistemas de control de acceso. Es un objetivo potencial para sabotaje, espionaje industrial, o robo de información. La videovigilancia interna del CCO es una capa de seguridad que: (1) disuade el acceso no autorizado (personal no autorizado sabe que está siendo grabado); (2) documenta cualquier incidente (robo de equipos, manipulación de sistemas, violación de procedimientos); (3) permite auditoría remota (los gerentes pueden verificar que los operadores cumplen procedimientos); (4) protege al personal (evidencia ante cualquier situación de riesgo para los operadores).

Adicionalmente, las cámaras del CCO son útiles para la gestión operativa: el supervisor puede verificar desde su oficina si el CCO está operando con el personal completo, si los operadores están atentos a sus pantallas, o si hay alguna situación que requiera su intervención. Durante auditorías de seguridad o certificaciones (ISO 27001, PCI DSS), las cámaras demuestran que el CCO tiene control de acceso físico y vigilancia adecuada.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-11 |
| **Nombre** | Cámaras CCTV del CCO |
| **Subsistema** | CCO — Seguridad Física / Videovigilancia |
| **Cantidad** | 4 unidades |
| **Tipo** | Cámara IP domo; montaje en techo (interior) |
| **Sensor** | CMOS 1/3" o 1/2.8"; resolución ≥ 4 MP (2688×1520); soporte WDR ≥ 120 dB |
| **Lente** | Varifocal motorizada 2.8-12 mm; ángulo de visión ajustable 100°-30°; autoenfoque; zoom óptico 4× |
| **Compresión** | H.265+/H.265/H.264; soporte Smart Codec; ROI (Region of Interest) |
| **Frame rate** | 25/30 fps @ 4MP; configurable 15 fps para optimizar almacenamiento |
| **Visión nocturna** | LED IR integrado; alcance ≥ 30 m; ICR automático; sensibilidad mínima ≤ 0.01 lux (color) / 0 lux (IR) |
| **Audio** | Micrófono integrado; entrada/salida de audio para altavoz externo; compresión G.711 |
| **Conectividad** | Ethernet 10/100 Mbps; PoE 802.3af; ONVIF Profile S/G compatible |
| **Almacenamiento** | Ranura microSD ≥ 256 GB para respaldo local ante falla de NVR |
| **Inteligencia** | Detección de movimiento; detección de intrusión (línea virtual, área); detección de escena cambiada; detección de audio anómalo |
| **Temperatura operación** | -10°C a +50°C |
| **Humedad** | 10% a 90% RH |
| **Protección** | IP67 (aunque sea interior, protección contra polvo y humedad); IK10 (resistencia a impacto/vandalismo) |
| **Certificaciones** | CE; FCC; ONVIF; RETIE |
| **Dimensiones** | ≈ Ø 120 × 100 mm (domo) |
| **Peso** | ≤ 600 g |
| **Montaje** | Soporte de techo; ángulo ajustable; montaje en superficie o empotrado; PoE |
| **Accesorios** | Cable Ethernet CAT6 5 m (4 unidades); caja de conexiones (si aplica); manual de instalación; software de configuración |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-11-01 | Capturar video continuo 24/7 del interior del CCO | Obligatorio |
| RF-CCO-11-02 | Transmitir video al NVR del CCO | Obligatorio |
| RF-CCO-11-03 | Permitir visualización remota autorizada | Obligatorio |
| RF-CCO-11-04 | Operar en condiciones de baja iluminación (IR) | Obligatorio |
| RF-CCO-11-05 | Detectar movimiento y generar alertas | Obligatorio |
| RF-CCO-11-06 | Grabar audio sincronizado con video | Obligatorio |
| RF-CCO-11-07 | Almacenar video localmente en microSD como respaldo | Obligatorio |
| RF-CCO-11-08 | Soportar ajuste remoto de lente (zoom, enfoque) | Deseable |
| RF-CCO-11-09 | Integrar con sistema de control de acceso (grabar al abrir puerta) | Deseable |
| RF-CCO-11-10 | Emitir alerta ante detección de intrusión fuera de horario | Obligatorio |
| RF-CCO-11-11 | Soportar PoE para simplificar instalación | Obligatorio |
| RF-CCO-11-12 | Ser compatible con ONVIF para integración con NVR | Obligatorio |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-11-01 | Resolución de video | 2688×1520 @ 25 fps |
| RNF-CCO-11-02 | Bitrate H.265 @ 4MP 15 fps | 2-4 Mbps |
| RNF-CCO-11-03 | Alcance IR nocturno | ≥ 30 m |
| RNF-CCO-11-04 | WDR | ≥ 120 dB |
| RNF-CCO-11-05 | Latencia de stream | < 3 segundos |
| RNF-CCO-11-06 | Consumo (PoE) | ≤ 6 W |
| RNF-CCO-11-07 | MTBF | ≥ 100.000 horas |
| RNF-CCO-11-08 | Temperatura operación | -10°C a +50°C |
| RNF-CCO-11-09 | Calidad de audio | Frecuencia 100 Hz - 16 kHz; SNR ≥ 50 dB |
| RNF-CCO-11-10 | Precisión de detección de movimiento | < 5 falsas alarmas por día |
| RNF-CCO-11-11 | Tiempo de retención local | ≥ 7 días en microSD |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Disponibilidad de grabación | ≥ 99.0% | Tiempo grabando / total |
| Calidad de video | ≥ 25 dB PSNR | Métrica objetiva de calidad |
| Latencia de stream | < 3 seg | Desde CCO hasta visualización remota |
| Falsas alarmas de movimiento | < 5 por día | Alertas no justificadas |
| Cobertura del CCO | 100% | Área visible por al menos una cámara |
| Tiempo de retención NVR | ≥ 30 días | Capacidad de almacenamiento |
| Satisfacción de seguridad | ≥ 4.0/5 | Encuesta de percepción de seguridad |


---

## 9.23 CC-CCO-12: Control de Acceso Biométrico

El Control de Acceso Biométrico es el componente de seguridad física que regula el ingreso al CCO. Instalado en la puerta principal de acceso al centro de control, permite el ingreso únicamente a personal autorizado mediante verificación de huella dactilar y/o tarjeta de proximidad. El sistema registra cada evento de acceso (timestamp, identidad, resultado) en una base de datos de auditoría.

El lector biométrico integra un sensor de huella dactilar (óptico o capacitivo) con resolución ≥ 500 DPI, capaz de capturar y comparar huellas en < 1 segundo con una tasa de falsos aceptados (FAR) < 0.001% y tasa de falsos rechazados (FRR) < 1%. Adicionalmente, incluye un lector de tarjetas de proximidad (Mifare o EM) como método alternativo de autenticación (en caso de lesión en dedos, o para visitantes temporales con tarjetas de acceso).

El sistema de control de acceso incluye: una unidad de control electrónico que almacena la base de datos de usuarios (≥ 1000 usuarios), reglas de acceso (horarios, días, zonas), y el registro de eventos; una cerradura electromagnética (maglock) o eléctrica de solenoide en la puerta; un botón de salida (exit button) en el interior; y un sensor de puerta abierta para detectar puertas forzadas o dejadas abiertas.

La conectividad TCP/IP permite integrar el control de acceso con el sistema de seguridad del CCO: registros de acceso pueden consultarse desde el NVR, alertas de acceso no autorizado pueden generar notificaciones, y el sistema puede sincronizarse con el directorio de empleados de Metro Sabanas. La interfaz web permite administrar usuarios, horarios de acceso, y generar reportes de asistencia/presencia.

### Justificación Estratégica

El CCO es una zona de seguridad restringida: no cualquier empleado de Metro Sabanas puede ingresar, y mucho menos personal externo. El control de acceso biométrico garantiza que solo el personal autorizado (operadores, supervisores, técnicos de mantenimiento, directivos) pueda ingresar al CCO. Las tarjetas de proximidad pueden ser prestadas, robadas, o clonadas; las huellas dactilares no pueden transferirse de persona a persona (salvo en escenarios de espionaje de alta sofisticación, improbables en este contexto).

El registro de auditoría de accesos es valioso para múltiples propósitos: investigación de incidentes (quién estaba en el CCO cuando ocurrió un evento); control de horarios de personal (quién ingresó y a qué hora); cumplimiento normativo (ISO 27001 requiere control de acceso físico con registro); y prevención (el solo conocimiento de que los accesos están registrados disuade comportamientos inadecuados).

La integración con el sistema de videovigilancia permite correlacionar eventos de acceso con video: cuando alguien presenta su huella en la puerta, la cámara de la entrada graba automáticamente un segmento de 10 segundos, permitiendo verificar que la persona que ingresó coincide con la identidad biométrica registrada. Esta correlación de datos biométricos + video + timestamp proporciona una cadena de evidencia robusta ante auditorías o investigaciones.

### Especificación Técnica (ET)

| Parámetro | Especificación |
|-----------|---------------|
| **Código** | CC-CCO-12 |
| **Nombre** | Control de Acceso Biométrico |
| **Subsistema** | CCO — Seguridad Física / Control de Acceso |
| **Cantidad** | 1 sistema (lector + controlador + cerradura + accesorios) |
| **Lector biométrico** | Sensor de huella dactilar óptico o capacitivo; resolución ≥ 500 DPI; área de escaneo ≥ 15×15 mm; tecnología de detección de vida (anti-spoofing: detecta huellas de silicona, papel, o fotos); tiempo de identificación < 1 segundo; capacidad ≥ 1000 huellas; FAR (False Acceptance Rate) < 0.001%; FRR (False Rejection Rate) < 1% |
| **Lector de tarjeta** | Proximidad 13.56 MHz (Mifare) o 125 kHz (EM); capacidad ≥ 1000 tarjetas; lectura < 300 ms |
| **Controlador** | Unidad de control electrónico; capacidad ≥ 1000 usuarios; ≥ 1000 eventos de registro; reglas de acceso por horario, día, zona; conectividad TCP/IP; protocolo Wiegand 26/34; salida de relé para cerradura; entrada para sensor de puerta; entrada para botón de salida; salida para alarma |
| **Cerradura** | Cerradura electromagnética (maglock) de 280 kg (600 lbs) de fuerza de retención; o cerradura eléctrica de solenoide con fail-secure (permanece cerrada sin energía) o fail-safe (se abre sin energía); alimentación 12V/24V DC; LED de estado |
| **Botón de salida** | Pulsador de salida no-touch (sensor IR) o pulsador mecánico; montaje en pared interior; iluminación LED; conexión al controlador |
| **Sensor de puerta** | Sensor magnético de puerta (reed switch); detecta puerta abierta/cerrada; alarma si puerta permanece abierta > 30 segundos |
| **Fuente de poder** | Fuente de 12V/24V DC; 3A; con protección contra sobrecarga; batería de respaldo opcional (autonomía ≥ 4 horas) |
| **Conectividad** | TCP/IP (Ethernet); RS-485 para expansión a múltiples puertas; Wiegand; USB para configuración inicial |
| **Software** | Software de gestión de acceso (Windows); interfaz web; API REST; integración con Active Directory (opcional); reportes de asistencia, accesos, alarmas |
| **Temperatura operación** | -10°C a +50°C (lector exterior); 0°C a +50°C (controlador interior) |
| **Humedad** | 10% a 90% RH |
| **Protección** | IP65 (lector exterior); IP20 (controlador interior); IK08 (lector) |
| **Certificaciones** | CE; FCC; RETIE; certificación biométrica FBI PIV / FAP 20 (opcional) |
| **Dimensiones (lector)** | ≈ 80 × 50 × 30 mm |
| **Peso (lector)** | ≤ 200 g |
| **Dimensiones (controlador)** | ≈ 150 × 100 × 40 mm |
| **Peso (controlador)** | ≤ 500 g |
| **Accesorios** | Cable Ethernet 5 m; cable de control 10 m; fuente de poder; tornillos de montaje; manual de instalación; software de gestión; 10 tarjetas de proximidad de prueba |
| **Garantía** | ≥ 2 años |

### Requerimientos Funcionales (RF)

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-CCO-12-01 | Permitir acceso mediante huella dactilar | Obligatorio |
| RF-CCO-12-02 | Permitir acceso mediante tarjeta de proximidad (alternativa) | Obligatorio |
| RF-CCO-12-03 | Denegar acceso a usuarios no autorizados | Obligatorio |
| RF-CCO-12-04 | Registrar todos los eventos de acceso con timestamp e identidad | Obligatorio |
| RF-CCO-12-05 | Soportar reglas de acceso por horario y día | Obligatorio |
| RF-CCO-12-06 | Detectar puerta forzada o dejada abierta | Obligatorio |
| RF-CCO-12-07 | Emitir alarma ante acceso no autorizado | Obligatorio |
| RF-CCO-12-08 | Permitir salida mediante botón interior (no requiere autenticación) | Obligatorio |
| RF-CCO-12-09 | Administrar usuarios y permisos desde interfaz web/software | Obligatorio |
| RF-CCO-12-10 | Generar reportes de asistencia y accesos | Obligatorio |
| RF-CCO-12-11 | Integrar con sistema de videovigilancia (correlación evento-video) | Deseable |
| RF-CCO-12-12 | Soportar respaldo de batería para operación ante falla de energía | Deseable |
| RF-CCO-12-13 | Detectar intentos de spoofing (huellas falsas) | Obligatorio |
| RF-CCO-12-14 | Soportar capacidad ≥ 1000 usuarios | Obligatorio |
| RF-CCO-12-15 | Exportar registros en formatos estándar (CSV, Excel) | Deseable |

### Requisitos No Funcionales (RNF)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-CCO-12-01 | Tiempo de identificación biométrica | < 1 segundo |
| RNF-CCO-12-02 | FAR (False Acceptance Rate) | < 0.001% |
| RNF-CCO-12-03 | FRR (False Rejection Rate) | < 1% |
| RNF-CCO-12-04 | Capacidad de usuarios | ≥ 1000 |
| RNF-CCO-12-05 | Capacidad de registro de eventos | ≥ 1000 |
| RNF-CCO-12-06 | Fuerza de retención de cerradura | ≥ 280 kg (maglock) |
| RNF-CCO-12-07 | Tiempo de apertura de cerradura | < 1 segundo |
| RNF-CCO-12-08 | MTBF | ≥ 100.000 horas |
| RNF-CCO-12-09 | Consumo de lector | ≤ 2 W |
| RNF-CCO-12-10 | Consumo de controlador | ≤ 5 W |
| RNF-CCO-12-11 | Consumo de cerradura | ≤ 10 W (activa); 0 W (standby maglock) |
| RNF-CCO-12-12 | Temperatura operación lector | -10°C a +50°C |
| RNF-CCO-12-13 | Tiempo de respaldo de batería | ≥ 4 horas (opcional) |
| RNF-CCO-12-14 | Precisión de detección de spoofing | ≥ 99% (detección de huellas falsas) |

### Indicadores Clave de Rendimiento (KPIs)

| KPI | Objetivo | Medición |
|-----|----------|----------|
| Tiempo de identificación | < 1 seg | Promedio en 1000 autenticaciones |
| Falsas aceptaciones | 0 | Incidentes de acceso no autorizado |
| Falsos rechazos | < 1% | Usuarios legítimos rechazados / total intentos |
| Tiempo de apertura de puerta | < 2 seg | Desde autenticación hasta puerta abierta |
| Eventos de puerta forzada | 0 | Incidentes por año |
| Disponibilidad del sistema | ≥ 99.5% | Tiempo operativo / total |
| Cobertura de usuarios registrados | 100% | % de personal del CCO registrado |
| Tiempo de respuesta a alarma | < 5 seg | Desde evento hasta notificación |
| Satisfacción de usuarios | ≥ 4.0/5 | Encuesta de facilidad de uso |
| Incidentes de spoofing detectados | 0 | Intentos de fraude biométrico exitosos |


---

# 10. CONECTIVIDAD Y RED DE TELECOMUNICACIONES

## 10.1 Arquitectura de Red

La red de telecomunicaciones del SETP Sincelejo es la infraestructura que conecta todos los componentes del sistema ITS: buses, CCO, nube, autoridades, y usuarios. Se diseña con una arquitectura de tres niveles: red de acceso (buses), red de transporte (CCO-cloud), y red de servicio (aplicaciones y usuarios).

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         NUBE (AWS / AZURE / GCP)                            │
│  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐                      │
│  │  SRC    │  │  SGCF   │  │   SIU   │  │   SST   │                      │
│  │ (SaaS)  │  │ (SaaS)  │  │ (SaaS)  │  │ (HSM)   │                      │
│  └────┬────┘  └────┬────┘  └────┬────┘  └────┬────┘                      │
│       │            │            │            │                            │
│       └────────────┴────────────┴────────────┘                            │
│                    │                                                        │
│              FIREWALL + VPN                                               │
│                    │                                                        │
└────────────────────┼────────────────────────────────────────────────────────┘
                     │ Internet dedicado 100 Mbps
                     │
┌────────────────────┼────────────────────────────────────────────────────────┐
│  CCO               │                                                        │
│  ┌─────────────────┼─────────────────┐                                    │
│  │   Router/Firewall UTM (NGFW)        │                                    │
│  │  • VPN IPsec/WireGuard hacia nube    │                                    │
│  │  • Segmentación VLAN                 │                                    │
│  │  • IDS/IPS                           │                                    │
│  │  • QoS                               │                                    │
│  └─────────────────┼─────────────────┘                                    │
│                    │                                                        │
│  ┌─────────────────┼─────────────────┐                                    │
│  │   Switch L3 (VLANs, ACLs, QoS)      │                                    │
│  └─────────────────┼─────────────────┘                                    │
│                    │                                                        │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐           │
│  │Puesto 1 │ │Puesto 2 │ │Puesto 3 │ │Puesto 4 │ │Puesto 5 │           │
│  │Superv.  │ │Planeac. │ │Concil.  │ │Soporte  │ │Inicial. │           │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘           │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
                     │ 4G/5G QoS (red celular)
                     │
              ┌──────┴──────┐
              │   34 BUSES   │
              │ • Router 4G  │
              │ • WiFi       │
              │ • Ethernet   │
              └─────────────┘
```

## 10.2 Red de Acceso: Buses

### 10.2.1 Tecnología de Conectividad

| Tecnología | Uso | Especificación |
|------------|-----|---------------|
| **4G LTE** | Conectividad principal WAN | Plan corporativo QoS; dual-SIM; bandas LATAM; throughput ≥ 50 Mbps DL / 10 Mbps UL |
| **5G NR** | Futura evolución (opcional) | Si está disponible en Sincelejo; throughput ≥ 200 Mbps DL / 50 Mbps UL |
| **WiFi 5/6** | Red local del bus + pasajeros | 802.11ac/ax; dual band; portal cautivo; VLAN separada |
| **Ethernet Gigabit** | Red cableada dentro del bus | Conecta validadores, cámaras, GPS, consola, DVR |
| **Radio VHF/UHF** | Respaldo de voz | Push-to-Talk; comunicación conductor-CCO ante falla celular |

### 10.2.2 Operadores Móviles y Cobertura

Sincelejo cuenta con cobertura 4G de los principales operadores móviles de Colombia (Claro, Movistar, Tigo). El sistema utiliza dual-SIM en cada bus para conmutar automáticamente entre operadores ante falla de cobertura. El plan de datos corporativo debe incluir:

- Datos ilimitados o paquete ≥ 50 GB/mes por bus
- Priorización de tráfico (QoS) para aplicaciones empresariales
- APN privado (Access Point Name) para aislamiento de tráfico
- Roaming nacional incluido (si buses operan fuera de Sincelejo)
- SLA de disponibilidad de red ≥ 99.5%

### 10.2.3 Estimación de Consumo de Datos por Bus

| Aplicación | Consumo estimado | Prioridad |
|------------|-----------------|-----------|
| GPS/GNSS (posición 3 seg) | ~50 MB/día | Alta |
| Recaudo (transacciones) | ~20 MB/día | Alta |
| CCTV (2 cámaras, 15 fps, H.265) | ~5-10 GB/día | Media |
| Conteo de pasajeros (metadatos) | ~5 MB/día | Media |
| SIU (WiFi pasajeros) | ~5-10 GB/día | Baja |
| Audio bidireccional | ~100 MB/día (si se usa) | Alta |
| **Total estimado** | **~15-25 GB/día por bus** | |

Para 34 buses: 510-850 GB/día en total; ~15-25 TB/mes. El plan de datos corporativo debe contemplar este volumen con márgenes de crecimiento.

## 10.3 Red de Transporte: CCO-Cloud

### 10.3.1 Enlace de Internet Dedicado

El CCO requiere un enlace de internet dedicado simétrico para comunicación con la nube y servicios externos:

| Parámetro | Especificación |
|-----------|---------------|
| **Tecnología** | Fibra óptica GPON o dedicada; o radio enlace dedicado |
| **Velocidad** | 100 Mbps simétrico (mínimo); 300 Mbps recomendado |
| **Latencia** | < 50 ms hacia nube nacional (AWS/Azure Bogotá/Medellín) |
| **SLA** | ≥ 99.5% de disponibilidad; MTTR < 4 horas |
| **IP** | IP fija pública (para VPN inbound); o IP privada con NAT |
| **Respaldo** | Enlace de respaldo (4G/5G o radio) con failover automático |

### 10.3.2 VPN y Seguridad de Red

| Componente | Tecnología | Función |
|------------|------------|---------|
| VPN CCO-Cloud | IPsec o WireGuard | Túnel seguro para tráfico operativo |
| VPN Proveedores | IPsec separado | Acceso controlado a proveedores SaaS |
| Firewall UTM | NGFW (Palo Alto, Fortinet, pfSense) | Stateful inspection, IDS/IPS, DLP, filtrado de aplicaciones |
| Segmentación | VLANs + ACLs | Separación de red de operadores, CCTV, servidores, invitados |
| DNS Seguro | DNS-over-HTTPS (DoH) o DNS-over-TLS (DoT) | Prevención de envenenamiento DNS |

## 10.4 Red de Servicio: Aplicaciones y Usuarios

### 10.4.1 API Gateway

El API Gateway es el punto de entrada único para todas las comunicaciones entre dispositivos de campo, aplicaciones móviles, y sistemas backend. Centraliza: autenticación (OAuth 2.0 + JWT); rate limiting; logging; transformación de protocolos; y enrutamiento a microservicios.

| Característica | Especificación |
|---------------|---------------|
| Protocolos | REST (JSON/HTTPS), GraphQL, WebSocket, MQTT |
| Autenticación | OAuth 2.0, OpenID Connect, API Keys |
| Rate Limiting | Por cliente, por endpoint, por método |
| TLS | 1.3 obligatorio; certificados Let's Encrypt o comercial |
| Escalabilidad | Horizontal (load balancer + múltiples instancias) |
| Monitoreo | Prometheus + Grafana; logs en Elasticsearch |

### 10.4.2 CDN y Cache

| Componente | Función | Tecnología |
|------------|---------|------------|
| CDN | Distribución de contenido estático (app, web, imágenes) | CloudFront, Cloudflare, o Akamai |
| Cache | Almacenamiento de datos frecuentes | Redis Cluster; TTL configurado |
| Edge Computing | Procesamiento cercano al usuario | Cloudflare Workers; AWS Lambda@Edge |


---

# 11. CIBERSEGURIDAD Y GOBERNANZA DE DATOS

## 11.1 Marco de Seguridad

La ciberseguridad del SETP Sincelejo se basa en el modelo de "Defensa en Profundidad" (Defense in Depth), con múltiples capas de protección que van desde el perímetro físico hasta los datos en reposo. La estrategia sigue el framework NIST Cybersecurity Framework: Identificar, Proteger, Detectar, Responder, Recuperar.

## 11.2 Capas de Seguridad

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ CAPA 1: PERÍMETRO FÍSICO                                                   │
│  Control de acceso biométrico al CCO; CCTV; guardia de seguridad; alarmas  │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA 2: PERÍMETRO DE RED                                                   │
│  Firewall UTM; VPN; IDS/IPS; segmentación VLAN; DMZ; WAF                 │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA 3: SEGURIDAD DE ENDPOINTS                                             │
│  EDR en estaciones de trabajo; antivirus; hardening de SO; patch management│
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA 4: SEGURIDAD DE APLICACIONES                                          │
│  OWASP Top 10; pentesting; SAST/DAST; code review; WAF                   │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA 5: SEGURIDAD DE DATOS                                                 │
│  Cifrado AES-256; tokenización; HSM; backup cifrado; DLP                   │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA 6: SEGURIDAD DE IDENTIDAD Y ACCESO                                  │
│  IAM; MFA; RBAC; PAM; SSO; auditoría de accesos                          │
├─────────────────────────────────────────────────────────────────────────────┤
│ CAPA 7: SEGURIDAD OPERATIVA                                                │
│  SIEM; SOC; threat intelligence; IR plan; DR plan; backups                 │
└─────────────────────────────────────────────────────────────────────────────┘
```

## 11.3 Controles de Seguridad por Componente

| Componente | Controles de Seguridad |
|------------|------------------------|
| **Validadores (CC-SRC-01)** | SAM criptográfico; TLS 1.3; lista blanca offline; firma de transacciones; anti-tampering |
| **Router WiFi (CC-SIU-01)** | Firewall stateful; VPN; WPA3-Enterprise; VLAN; QoS; IDS/IPS básico; OTA firmado |
| **GPS (CC-SGCF-01)** | TLS 1.3; autenticación de dispositivo; firma de posiciones; anti-replay |
| **CCTV (CC-SGCF-03)** | Cifrado de stream; autenticación de cámara; integridad de video; watermarking |
| **CCO** | 802.1X; EDR; DLP; segmentación VLAN; acceso físico biométrico; CCTV; SIEM |
| **Cloud** | CSP shared responsibility; cifrado en reposo y tránsito; IAM; WAF; pentesting; compliance |

## 11.4 Gobernanza de Datos y Privacidad

### 11.4.1 Clasificación de Datos

| Nivel | Ejemplos | Protección |
|-------|----------|------------|
| **Crítico** | Claves criptográficas, datos bancarios EMV, credenciales de admin | HSM; acceso MFA; auditoría 100%; retención mínima |
| **Sensible** | Datos de pasajeros (saldo, recargas, viajes), datos de conductores, video de incidentes | Cifrado AES-256; acceso RBAC; retención definida; derechos ARCO |
| **Interno** | Rutas, frecuencias, reportes operativos, estadísticas agregadas | Acceso autenticado; logs de acceso; backup |
| **Público** | Horarios de rutas, mapas de paradas, tarifas, políticas | Acceso público; integridad verificada |

### 11.4.2 Cumplimiento Normativo

| Norma | Requisito | Implementación |
|-------|-----------|----------------|
| **Ley 1581/2012** | Protección de datos personales | Política de privacidad; consentimiento; derechos ARCO; registro de tratamiento; DPO |
| **Decreto 1377/2013** | Autorización de tratamiento | Formulario de autorización; aviso de privacidad; finalidades explícitas |
| **Circular Externa 052/2021** | Ciberseguridad financiera | Pentesting anual; monitoreo 24/7; plan de respuesta a incidentes; seguro cibernético |
| **ISO 27001:2022** | Gestión de seguridad de la información | ISMS; políticas; controles; auditorías internas; mejora continua |
| **PCI DSS** (si aplica EMV) | Seguridad de datos de tarjetas de pago | Segmentación de red; cifrado; scans de vulnerabilidad; ASV; SAQ o ROC |


---

# 12. REQUERIMIENTOS FUNCIONALES (RF) Y NO FUNCIONALES (RNF) GLOBALES

## 12.1 Requerimientos Funcionales Globales (RF-G)

Estos requerimientos aplican a todo el sistema ITS del SETP Sincelejo, no a un componente individual.

| ID | Requerimiento | Prioridad |
|----|--------------|-----------|
| RF-G-01 | El sistema debe permitir la operación de 34 buses simultáneos con recaudo electrónico en tiempo real | Obligatorio |
| RF-G-02 | El sistema debe soportar 5 rutas configurables con geocercas independientes | Obligatorio |
| RF-G-03 | El sistema debe procesar ≥ 10.000 transacciones de recaudo por día | Obligatorio |
| RF-G-04 | El sistema debe transmitir posiciones GPS de 34 buses con latencia < 3 segundos | Obligatorio |
| RF-G-05 | El sistema debe permitir la operación offline de validadores ante pérdida de conectividad | Obligatorio |
| RF-G-06 | El sistema debe sincronizar transacciones offline al restaurar conectividad | Obligatorio |
| RF-G-07 | El sistema debe generar reportes regulatorios para MinTransporte y SuperTransporte | Obligatorio |
| RF-G-08 | El sistema debe integrarse con la ANSV para reporte de incidentes de seguridad vial | Obligatorio |
| RF-G-09 | El sistema debe soportar múltiples medios de pago: Mifare, QR, EMV, efectivo | Deseable |
| RF-G-10 | El sistema debe proporcionar app móvil para usuarios (iOS y Android) | Obligatorio |
| RF-G-11 | El sistema debe proporcionar micrositio web para consulta de información | Obligatorio |
| RF-G-12 | El sistema debe permitir la gestión de tarjetas (emisión, recarga, bloqueo) desde el CCO | Obligatorio |
| RF-G-13 | El sistema debe detectar y alertar eventos de seguridad (botón de pánico, exceso de velocidad, fuera de ruta) | Obligatorio |
| RF-G-14 | El sistema debe permitir la comunicación bidireccional conductor-CCO | Deseable |
| RF-G-15 | El sistema debe generar alertas predictivas ante comportamientos anormales (ML) | Deseable |
| RF-G-16 | El sistema debe soportar escalabilidad a 100+ buses sin rediseño arquitectónico | Obligatorio |
| RF-G-17 | El sistema debe cumplir con normativa de protección de datos (Ley 1581/2012) | Obligatorio |
| RF-G-18 | El sistema debe cumplir con estándares de ciberseguridad (ISO 27001, NIST) | Obligatorio |
| RF-G-19 | El sistema debe permitir auditoría completa de transacciones y eventos | Obligatorio |
| RF-G-20 | El sistema debe proporcionar disponibilidad ≥ 99.5% para servicios críticos | Obligatorio |

## 12.2 Requisitos No Funcionales Globales (RNF-G)

| ID | Requisito | Valor |
|----|----------|-------|
| RNF-G-01 | Disponibilidad del sistema de recaudo | ≥ 99.9% |
| RNF-G-02 | Disponibilidad del sistema de control de flota | ≥ 99.5% |
| RNF-G-03 | Disponibilidad de la app móvil | ≥ 99.5% |
| RNF-G-04 | Latencia de validación de pago | < 300 ms |
| RNF-G-05 | Latencia de transmisión de posición GPS | < 3 segundos |
| RNF-G-06 | Latencia de alerta de botón de pánico | < 10 segundos |
| RNF-G-07 | Precisión de localización GPS | < 5 m (CEP 95%) |
| RNF-G-08 | Precisión de conteo de pasajeros | ≥ 97% |
| RNF-G-09 | Tiempo de retención de video | ≥ 30 días |
| RNF-G-10 | Tiempo de respuesta del CCO a emergencia | < 2 minutos (human response) |
| RNF-G-11 | Escalabilidad de buses | De 34 a 100+ sin rediseño |
| RNF-G-12 | Escalabilidad de transacciones | De 10.000 a 50.000+ por día |
| RNF-G-13 | RTO (Recovery Time Objective) ante desastre | < 4 horas |
| RNF-G-14 | RPO (Recovery Point Objective) ante desastre | < 1 hora |
| RNF-G-15 | Cifrado de datos en tránsito | TLS 1.3 (100% del tráfico) |
| RNF-G-16 | Cifrado de datos en reposo | AES-256 |
| RNF-G-17 | Autenticación de usuarios | MFA obligatoria para admin; MFA opcional para usuarios |
| RNF-G-18 | Auditoría de accesos | 100% de operaciones críticas logueadas |
| RNF-G-19 | Backup de datos | Diario; retención ≥ 30 días; almacenamiento off-site |
| RNF-G-20 | Penetration testing | Anual; por tercero independiente |
| RNF-G-21 | Disaster Recovery Drill | Semestral |
| RNF-G-22 | Actualización de seguridad | Críticas: < 24 horas; Altas: < 7 días; Medias: < 30 días |
| RNF-G-23 | Temperatura de operación (equipos de campo) | -10°C a +55°C |
| RNF-G-24 | Humedad (equipos de campo) | 5% a 95% RH |
| RNF-G-25 | Protección IP mínima (equipos de campo) | IP54 |
| RNF-G-26 | Vida útil de equipos de campo | ≥ 5 años |
| RNF-G-27 | Vida útil de equipos del CCO | ≥ 7 años |
| RNF-G-28 | MTBF de equipos de campo | ≥ 50.000 horas |
| RNF-G-29 | MTTR de equipos de campo | ≤ 2 horas (swap de unidad) |
| RNF-G-30 | Documentación técnica | Completa; actualizada; en español; disponible en línea |


---

# 13. PLAN DE IMPLEMENTACIÓN POR FASES

## 13.1 Fase 0: Preparación y Diseño Detallado (Mes 1-2)

| Actividad | Entregable | Responsable |
|-----------|------------|-------------|
| Revisión final de arquitectura con Metro Sabanas | Acta de aprobación de arquitectura | INNOVADATACO + Metro Sabanas |
| Estudio de mercado de equipos ITS | Informe de proveedores y precios | INNOVADATACO |
| Definición de proveedores y contratos | Contratos de compra | Metro Sabanas |
| Diseño detallado de red y cableado | Diagramas as-built | INNOVADATACO |
| Configuración de SaaS (SRC, SGCF, SIU) | Instancias operativas en cloud | Proveedores SaaS |
| Preparación del CCO (obra civil, energía, internet) | CCO listo para instalación | Metro Sabanas |
| Capacitación del equipo de operación | Certificación de operadores | INNOVADATACO |

## 13.2 Fase 1: Instalación en Buses Piloto (Mes 3)

| Actividad | Entregable | Cantidad |
|-----------|------------|----------|
| Instalación de equipos ITS en 5 buses piloto | Buses piloto operativos | 5 buses |
| Configuración de red y comunicaciones | Red operativa en buses piloto | 5 buses |
| Pruebas de integración end-to-end | Informe de pruebas | 1 documento |
| Pruebas de operación offline | Informe de robustez | 1 documento |
| Pruebas de botón de pánico y emergencias | Protocolo validado | 1 documento |
| Ajustes y refinamiento de configuración | Configuración optimizada | Sistema |
| Capacitación de conductores piloto | Conductores certificados | 10 conductores |

## 13.3 Fase 2: Despliegue en Flota Completa (Mes 4-5)

| Actividad | Entregable | Cantidad |
|-----------|------------|----------|
| Instalación en 29 buses restantes | Flota completa equipada | 29 buses |
| Configuración de CCO completo | CCO operativo 24/7 | 1 CCO |
| Migración de datos y configuración de SaaS | Producción en cloud | 1 sistema |
| Pruebas de carga y estrés | Informe de rendimiento | 1 documento |
| Pruebas de seguridad y penetración | Informe de vulnerabilidades | 1 documento |
| Capacitación de operadores del CCO | Operadores certificados | 5 operadores |
| Puesta en marcha oficial | Operación comercial ITS | 34 buses |

## 13.4 Fase 3: Estabilización y Optimización (Mes 6-8)

| Actividad | Entregable | Responsable |
|-----------|------------|-------------|
| Monitoreo de KPIs y ajustes | Dashboard de KPIs operativos | INNOVADATACO + Metro Sabanas |
| Optimización de frecuencias basada en datos | Itinerarios optimizados | INNOVADATACO |
| Implementación de app móvil para usuarios | App en App Store / Play Store | INNOVADATACO |
| Campaña de comunicación a usuarios | Materiales de comunicación | Metro Sabanas |
| Programa de coaching para conductores | Informe de comportamiento de conducción | INNOVADATACO |
| Auditoría de seguridad y cumplimiento | Certificación de cumplimiento | Tercero independiente |

## 13.5 Fase 4: Operación Continua y Mejora (Mes 9+)

| Actividad | Frecuencia | Responsable |
|-----------|------------|-------------|
| Mantenimiento preventivo de equipos | Mensual | Metro Sabanas (con soporte INNOVADATACO) |
| Actualización de firmware y software | Trimestral | INNOVADATACO |
| Revisión de KPIs y reportes regulatorios | Mensual | INNOVADATACO + Metro Sabanas |
| Planificación de expansiones | Semestral | INNOVADATACO + Metro Sabanas |
| Auditoría de seguridad | Anual | Tercero independiente |
| Renovación de contratos y licencias | Anual | Metro Sabanas |


---

# 14. ANEXOS TÉCNICOS

## Anexo A: Glosario de Términos ITS

| Término | Definición |
|---------|------------|
| **ANSV** | Agencia Nacional de Seguridad Vial |
| **APN** | Access Point Name; identificador de red para conexión de datos móviles |
| **CAN Bus** | Controller Area Network; protocolo de comunicación vehicular |
| **CCO** | Centro de Control de Operaciones |
| **CEP** | Circular Error Probable; medida de precisión de GPS (radio del círculo que contiene 50% de las mediciones) |
| **CCTV** | Closed Circuit Television; videovigilancia |
| **DVR** | Digital Video Recorder; grabador de video digital |
| **EMV** | Europay, Mastercard, Visa; estándar de tarjetas inteligentes para pago |
| **FAR** | False Acceptance Rate; tasa de falsas aceptaciones en biometría |
| **FRR** | False Rejection Rate; tasa de falsos rechazos en biometría |
| **GIS** | Sistema de Información Geográfica |
| **GNSS** | Global Navigation Satellite System; sistema global de navegación por satélite (GPS, GLONASS, Galileo, BeiDou) |
| **HSM** | Hardware Security Module; módulo de seguridad hardware para criptografía |
| **IR** | Infrarrojo; radiación electromagnética usada en visión nocturna |
| **ITS** | Intelligent Transportation Systems; Sistemas Inteligentes de Transporte |
| **KPI** | Key Performance Indicator; Indicador Clave de Rendimiento |
| **LTE** | Long Term Evolution; tecnología de comunicación móvil 4G |
| **Mifare** | Tecnología de tarjetas de proximidad de NXP Semiconductors |
| **MTBF** | Mean Time Between Failures; tiempo promedio entre fallas |
| **MTTR** | Mean Time To Repair; tiempo promedio de reparación |
| **NVR** | Network Video Recorder; grabador de video en red |
| **OTA** | Over-The-Air; actualización de firmware por aire (inalámbrica) |
| **PSE** | Pagos Seguros en Línea; plataforma de pagos electrónicos de Colombia |
| **PoE** | Power over Ethernet; alimentación eléctrica a través de cable Ethernet |
| **PTT** | Push-To-Talk; comunicación de voz half-duplex presionando un botón |
| **QoS** | Quality of Service; calidad de servicio en redes |
| **RF** | Requerimiento Funcional |
| **RNF** | Requisito No Funcional |
| **RPO** | Recovery Point Objective; punto objetivo de recuperación (pérdida máxima de datos aceptable) |
| **RTO** | Recovery Time Objective; tiempo objetivo de recuperación (tiempo máximo de indisponibilidad aceptable) |
| **SAM** | Secure Access Module; módulo de acceso seguro para criptografía de tarjetas |
| **SAST** | Static Application Security Testing; pruebas estáticas de seguridad de aplicaciones |
| **SFP+** | Small Form-factor Pluggable Plus; transceptor de fibra óptica de 10 Gbps |
| **SGCF** | Sistema de Gestión y Control de Flota |
| **SIEM** | Security Information and Event Management; gestión de información y eventos de seguridad |
| **SIU** | Sistema de Información al Usuario |
| **SRC** | Sistema de Recaudo y Cobro |
| **SST** | Sistema de Seguridad y Transporte |
| **SSL** | Secure Sockets Layer; protocolo de seguridad (ahora TLS) |
| **TLS** | Transport Layer Security; protocolo de seguridad de la capa de transporte |
| **UPS** | Uninterruptible Power Supply; fuente de alimentación ininterrumpida |
| **VLAN** | Virtual Local Area Network; red de área local virtual |
| **VMS** | Video Management System; sistema de gestión de video |
| **VoIP** | Voice over IP; voz sobre protocolo de internet |
| **VPN** | Virtual Private Network; red privada virtual |
| **WAF** | Web Application Firewall; firewall de aplicaciones web |
| **WDR** | Wide Dynamic Range; rango dinámico amplio en cámaras |

## Anexo B: Referencias Normativas

| Norma/Resolución | Descripción | Aplicación al SETP Sincelejo |
|------------------|-------------|------------------------------|
| Decreto 393/2010 | Creación del Ministerio de Transporte | Marco regulatorio del transporte público |
| Decreto 482/2023 | Reglamentación del transporte público terrestre automotor | Operación del SETP |
| Decreto 909/2023 | Estatuto de contratación del sector transporte | Contratación de servicios ITS |
| Decreto 1079/2015 | Decreto Único Reglamentario del Sector Transporte | Consolidación normativa del sector |
| Resolución 20203040034065 | Concepto ITS de MinTransporte | Lineamientos para implementación de ITS en transporte público |
| Ley 1581/2012 | Protección de datos personales | Tratamiento de datos de pasajeros |
| Decreto 1377/2013 | Autorización de tratamiento de datos personales | Consentimiento de usuarios del SETP |
| Circular Externa 052/2021 | Ciberseguridad financiera | Seguridad del sistema de recaudo |
| ISO 27001:2022 | Gestión de seguridad de la información | Seguridad del sistema ITS |
| ISO 14813-1 | Sistemas de transporte inteligente — Marco de referencia | Arquitectura ITS |
| ISO 39001 | Sistemas de gestión de seguridad vial | Seguridad del transporte público |
| PCI DSS | Seguridad de datos de tarjetas de pago | Si se implementa EMV |

## Anexo C: Consolidado de Componentes de Campo

| Código | Nombre | Cantidad | Subsistema | Ubicación |
|--------|--------|----------|------------|-----------|
| CC-SRC-01 | Validador de Tarjetas Mifare | 34 | SRC | Interior de bus |
| CC-SRC-02 | Lector/Validador QR y EMV | 34 | SRC | Interior de bus |
| CC-SGCF-01 | GPS/GNSS de Alta Precisión | 34 | SGCF | Techo del bus |
| CC-SGCF-02 | Contador de Pasajeros (2D/3D) | 34 | SGCF | Puertas del bus |
| CC-SGCF-03 | Cámaras CCTV Bus (2 unidades) | 68 | SGCF | Interior del bus |
| CC-SGCF-04 | Grabador DVR/NVR SSD | 34 | SGCF | Compartimento técnico bus |
| CC-SGCF-05 | Consola/Tablet Conductor | 34 | SGCF | Cabina del conductor |
| CC-SST-01 | Botón de Pánico y Alertas | 68 | SST | Cabina + pasajeros |
| CC-SIU-01 | Router WiFi 4G/5G | 34 | SIU | Techo/compartimento bus |
| CC-COM-01 | Radio VHF/UHF | 34 | COM | Cabina del conductor |
| CC-COM-02 | Gateway de Comunicaciones | 34 | COM | Compartimento técnico bus |
| CC-CCO-01 | Video Wall 2×2 | 1 | CCO | Pared principal CCO |
| CC-CCO-02 | Estación Supervisor (Triple) | 1 | CCO | Puesto de supervisor |
| CC-CCO-03 | Estación Doble Pantalla | 2 | CCO | Planeación + Conciliación |
| CC-CCO-04 | Estación Inicialización Tarjetas | 2 | CCO | Gestión de medios de pago |
| CC-CCO-05 | Estación Programación Rutas (GIS) | 1 | CCO | Planeación estratégica |
| CC-CCO-06 | Antena Inicialización SAM | 4 | CCO | En estaciones de inicialización |
| CC-CCO-07 | UPS Online 5 KVA | 1 | CCO | Rack/suelo CCO |
| CC-CCO-08 | Switch Gigabit Capa 3 | 1 | CCO | Rack CCO |
| CC-CCO-09 | Rack 19" 42U | 1 | CCO | CCO |
| CC-CCO-10 | Puesto de Trabajo Ergonómico | 5 | CCO | CCO |
| CC-CCO-11 | Cámaras CCTV del CCO | 4 | CCO | Techo/paredes CCO |
| CC-CCO-12 | Control de Acceso Biométrico | 1 | CCO | Puerta principal CCO |

**Total de componentes de campo en buses:** 374 unidades
**Total de componentes en CCO:** 22 unidades
**Total general:** 396 unidades

## Anexo D: Matriz de Responsabilidades (RACI)

| Actividad | INNOVADATACO | Metro Sabanas | Proveedor SaaS | Autoridades |
|-----------|-------------|--------------|---------------|-------------|
| Diseño de arquitectura ITS | R/A | C | I | I |
| Estudio de mercado de equipos | R/A | C | - | - |
| Compra de equipos | C | R/A | - | - |
| Configuración de SaaS | C | C | R/A | I |
| Instalación en buses | R/A | C | - | - |
| Configuración de CCO | R/A | C | - | - |
| Pruebas de integración | R/A | C | C | - |
| Pruebas de seguridad | R/A | C | C | - |
| Capacitación | R/A | C | - | - |
| Puesta en marcha | R/A | A | C | I |
| Operación continua | C | R/A | C | I |
| Reportes regulatorios | C | R | - | A |
| Auditoría de seguridad | C | C | - | R/A |

**Leyenda:** R = Responsible, A = Accountable, C = Consulted, I = Informed

---

**Fin del Documento**

---

*Documento generado por INNOVADATACO — ZEUS Intelligent Strategic Assistant*
*Fecha de generación: 2026-05-29*
*Versión: 1.1*
*Clasificación: CONFIDENCIAL — USO INTERNO INNOVADATACO*
*Proyecto: PROYECTO-004-2026-SETP-SINCELEJO*

