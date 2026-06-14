# RESUMEN EJECUTIVO — Sistemas Tecnológicos del SETP Sincelejo

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Elaborado por:** Innovadataco  
**Fecha:** 15 de junio de 2026  
**Versión:** 1.0

---

## 1. VISIÓN GENERAL

El Sistema Estratégico de Transporte Público de Sincelejo (SETP) tiene una **historia tecnológica definida desde 2015** cuando la Unión Temporal Steer Davies Gleave + GSD+ estructuró el componente tecnológico del sistema. Esta consultoría de Innovadataco (2026) se enmarca en la **continuidad de ese proceso**, con antecedentes de una consultoría anterior (A4 Asociados, 2022) y un proceso de contratación tecnológica con el MinTransporte (2023).

| Año | Evento | Documento |
|-----|--------|-----------|
| **2015** | Estructuración tecnológica, legal y financiera | Informe ETL GSD+ / Steer Davies Gleave |
| **2022** | Actualización del modelo de transporte | Contrato CM-001-2022 (A4 Asociados) |
| **2023** | Proceso de contratación ITS con MinTransporte | Estudios previos, Anexo Técnico ITS |
| **2025** | RFI integración de 3 contratos | RFI SETP Sincelejo (Metro Sabanas) |
| **2026** | **Consultoría Innovadataco** | Estructuración componentes tecnológicos |

### 1.1 Sistemas Tecnológicos Definidos (2015-2023)

El proyecto define **4 sistemas tecnológicos** operados bajo **3 escenarios institucionales**:

| Sistema | Sigla | Función | Estado 2022 |
|---------|-------|---------|-------------|
| **Sistema de Recaudo Centralizado** | **SRC** | Pago efectivo + tarjeta sin contacto + viaje a crédito | Diseñado, no implementado |
| **Sistema de Gestión y Control de Flota** | **SGCF** | Programación, supervisión, reportes de operación | Diseñado, no implementado |
| **Sistema de Información al Usuario** | **SIU** | Portal web, app móvil, call center, paneles en buses | Diseñado, no implementado |
| **Sistema de Seguridad de Transacciones** | **SST** | Cifrado, seguridad de datos, auditoría | Agregado en 2023 |

### 1.2 Escenarios Institucionales (2015)

| Escenario | Quién opera la tecnología |
|-----------|---------------------------|
| **"Base"** | Metro Sabanas opera SGCF+SIU, operador de transporte opera flota, concesionario externo opera SRC |
| **"Socio tecnológico"** | Un único concesionario opera los 4 sistemas (SRC+SGCF+SIU+SST) |
| **"Operador recaudador"** | El operador de transporte asume los 4 sistemas |

### 1.3 Alcance de esta Consultoría (2026)

Esta consultoría cubre exclusivamente la **estructuración** (revisión, diseño conceptual y especificación) de los 4 sistemas ya definidos desde 2015. **NO incluye implementación, instalación, operación ni puesta en marcha** de los sistemas.

Alineada con:
- **Resolución 20203040034065** del MinTransporte (2020)
- **RFI 2025** de integración de 3 contratos (flota + tecnología + operación)
- **Proceso de contratación 2023** (46 vehículos, 9 meses, pago condicionado a validación)

**El objetivo final es producir los Estudios Previos ITS** que alimentarán el proceso de licitación/contratación del componente tecnológico del SETP Sincelejo.

```
┌─────────────────────────────────────────────────────────────┐
│              SISTEMAS TECNOLÓGICOS DEL SETP                │
│                    Sincelejo — 46 vehículos                      │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │  GESTIÓN    │  │   PAGO      │  │ INFORMACIÓN │        │
│  │   FLOTA     │  │ ELECTRÓNICO │  │   USUARIO   │        │
│  │   (GPS)     │  │   (NFC)     │  │  (App/Web)  │        │
│  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘        │
│         │                │                │               │
│         └────────────────┼────────────────┘               │
│                          │                                │
│              ┌─────────────┴─────────────┐                 │
│              │     CENTRO DE CONTROL       │                 │
│              │      (CVP / Software)      │                 │
│              │  • Monitoreo en tiempo real  │                 │
│              │  • Alarmas y alertas         │                 │
│              │  • Reportes operativos       │                 │
│              └─────────────┬─────────────┘                 │
│                            │                                │
│              ┌─────────────┴─────────────┐                 │
│              │   GESTIÓN TARIFARIA         │                 │
│              │  • Tarifas • Subsidios       │                 │
│              │  • Recaudo • Conciliación    │                 │
│              └─────────────────────────────┘                 │
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │         INTEGRACIÓN CON SISTEMAS NACIONALES          │   │
│  │   SRC    ←→  SGCF   ←→   SIU   ←→  SST          │   │
│  └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

---

## 2. SUBSISTEMAS DETALLADOS

### 2.1 GESTIÓN DE FLOTA (Onboard Unit)

**¿Qué hace?** Rastrea, monitorea y gestiona cada bus en tiempo real.

| Componente | Función | Prioridad |
|------------|---------|-----------|
| **GPS/GNSS** | Ubicación cada 10-30 segundos | 🔴 Crítico |
| **4G/LTE** | Transmisión de datos en tiempo real | 🔴 Crítico |
| **Sensor de puertas** | Detecta apertura/cierre | 🟡 Medio |
| **Contador de pasajeros** | Embarques/desembarques (IR/ToF) | 🟡 Medio |
| **Pantalla conductor** | Info de ruta, alertas | 🟡 Medio |
| **Botón de pánico** | Emergencia → Centro de Control | 🔴 Crítico |

**Hardware base:** ARM Cortex-A72, 4GB RAM, 64GB, 4G Cat-4, GPS multi-GNSS, IP65

**Flujo de datos:**
```
Bus (Onboard) → 4G/LTE → VPN → Centro de Control → Base de Datos
```

---

### 2.2 PAGO ELECTRÓNICO

**¿Qué hace?** Permite el pago de pasajes con tarjeta sin contacto y gestiona la recauda.

| Componente | Función | Prioridad |
|------------|---------|-----------|
| **Validador NFC** | Lee tarjeta MIFARE DESFire | 🔴 Crítico |
| **Lector QR** | Tickets digitales | 🟡 Medio |
| **Backoffice de pagos** | Conciliación, tarifas, reportes | 🔴 Crítico |
| **Pasarela de pagos** | Integración con banco (Redeban/ACH) | 🔴 Crítico |
| **Portal de recargas** | Web/app para recargar saldo | 🟡 Medio |

**Tarjetas soportadas:** MIFARE DESFire EV2, ISO 14443 A/B  
**Modo offline:** Funciona sin conectividad, sincroniza cuando recupera red

**Flujo de transacción:**
```
Usuario → Tarjeta NFC → Validador a bordo → Backoffice → Banco/ACH
```

---

### 2.3 INFORMACIÓN AL USUARIO

**¿Qué hace?** Comunica al ciudadano tiempos de espera, rutas y novedades.

| Canal | Descripción | Prioridad |
|-------|-------------|-----------|
| **App móvil** | iOS/Android — rutas, tiempos, recargas | 🟡 Medio |
| **Pantallas en paradas** | LED 32"-43" — tiempo estimado de llegada | 🟡 Medio |
| **Notificaciones push** | Demoras, cambios de ruta, alertas | 🟢 Bajo |
| **Web portal** | Planificación de viajes | 🟡 Medio |
| **WhatsApp/SMS** | Consulta de saldo y tiempos | 🟢 Bajo |

**Tecnología:** Flutter/React Native, MQTT/WebSocket para tiempo real

---

### 2.4 CENTRO DE CONTROL (CVP)

**¿Qué hace?** Es el "cerebro" del sistema: visualiza, alerta, reporta.

| Módulo | Función | Tecnología |
|--------|---------|------------|
| **Mapa en tiempo real** | Posición de todos los buses | Mapbox/Leaflet |
| **Tablero de control** | KPIs, alertas, estado de flota | Grafana |
| **Alarmas inteligentes** | Desvío, exceso de velocidad, pánico | Prometheus |
| **Videovigilancia** | CCTV buses y terminales | NVR 32 canales |
| **Reportes** | Operativos, financieros, de calidad | Superset/Metabase |
| **Comunicaciones** | Chat/radio con conductores | MQTT/WebSocket |

**Infraestructura:** 2 servidores HA, PostgreSQL 15, 2TB SSD, UPS 2kVA, firewall perimetral

**Arquitectura de red:**
```
Internet → Firewall/WAF → Load Balancer → API Gateway → Servidores App → BD PostgreSQL
                                ↓
                           VPN 4G/LTE ← Onboard Units (buses)
```

---

### 2.5 GESTIÓN TARIFARIA

**¿Qué hace?** Administra tarifas, subsidios y genera reportes financieros.

| Función | Descripción | Prioridad |
|---------|-------------|-----------|
| **Motor tarifario** | Tarifa base, diferenciada por categoría | 🔴 Crítico |
| **Subsidios** | Estudiante, adulto mayor, discapacidad | 🟡 Medio |
| **Conciliación** | Emparejamiento con banco diario | 🔴 Crítico |
| **Reportes financieros** | Ingresos por línea, bus, conductor | 🔴 Crítico |
| **Blacklist** | Tarjetas bloqueadas o reportadas | 🟡 Medio |

---

## 3. ARQUITECTURA TECNOLÓGICA (5 Capas)

```
┌─────────────────────────────────────────┐
│  CAPA 1: PRESENTACIÓN                    │
│  App móvil · Portal web · Pantallas · CMS│
├─────────────────────────────────────────┤
│  CAPA 2: APLICACIÓN                      │
│  API Gateway · Gestión flota · Pagos ·   │
│  Información · Tarifas                   │
├─────────────────────────────────────────┤
│  CAPA 3: PROCESOS                        │
│  Motor de reglas · Routing · Algoritmos  │
│  ML · Alertas inteligentes               │
├─────────────────────────────────────────┤
│  CAPA 4: INTEGRACIÓN                     │
│  ESB · SRC · SGCF · SIU · SST    │
├─────────────────────────────────────────┤
│  CAPA 5: DATOS + INFRAESTRUCTURA         │
│  PostgreSQL · Redis · Cloud · Kubernetes │
└─────────────────────────────────────────┘
```

---

## 4. INTEGRACIONES EXTERNAS

| Sistema | Datos | Protocolo | Prioridad |
|---------|-------|-----------|-----------|
| **SRC** | Recaudo centralizado, tarjetas | Interno | 🔴 Crítico |
| **SGCF** | Gestión flota, GPS, control | Interno | 🔴 Crítico |
| **SIU** | Información usuario, web, app | Interno | 🟡 Medio |
| **SST** | Seguridad transacciones, cifrado | Interno | 🟡 Medio |
| **Bancos/ACH** | Conciliación financiera | Redeban/ACH | 🔴 Crítico |

---

## 5. INDICADORES CLAVE (KPIs)

### Operativos
| KPI | Meta | Frecuencia |
|-----|------|------------|
| Cumplimiento de rutas | > 95% | Diaria |
| Puntualidad | > 90% | Diaria |
| Incidentes / 10.000 km | < 5 | Mensual |

### Tecnológicos
| KPI | Meta | Frecuencia |
|-----|------|------------|
| Disponibilidad del sistema | > 99.5% | Mensual |
| Latencia GPS | < 5 segundos | Continua |
| Transacciones exitosas | > 99.9% | Diaria |

### Servicio al usuario
| KPI | Meta | Frecuencia |
|-----|------|------------|
| Satisfacción del usuario | > 85% | Mensual |
| Tiempo de espera en parada | < 10 min | Diaria |

---

## 6. PLAN DE IMPLEMENTACIÓN (12 meses)

| Fase | Meses | Alcance | Entregables |
|------|-------|---------|-------------|
| **Fase 1** | 1-2 | Infraestructura cloud + centro de control | Servidores, red, CCTV, software base |
| **Fase 2** | 3-4 | Piloto 10 buses | Onboard units, GPS, validadores, pruebas |
| **Fase 3** | 5-6 | Rollout total 46 vehículos | Instalación flota completa, operación |
| **Fase 4** | 7-8 | Pago electrónico + app usuarios | Validadores activos, recargas, app móvil |
| **Fase 5** | 9-12 | Integraciones + optimización | SRC, SGCF, SIU, SST, analytics |

---

## 7. ESPECIFICACIONES DE SEGURIDAD

| Capa | Método |
|------|--------|
| Comunicaciones | TLS 1.3 |
| Datos sensibles | AES-256-GCM |
| Autenticación | OAuth 2.0 + MFA |
| Dispositivos | Certificados X.509 |
| Auditoría | Registro completo de acciones críticas (2 años) |

---

## 8. RESUMEN DE INVERSIONES ESTIMADAS (Por definir en RFQ)

| Lote | Descripción | Estado |
|------|-------------|--------|
| Lote 1 | Unidades Onboard (46 vehículos) | Por cotizar |
| Lote 2 | Centro de Control (servidores, red, CCTV) | Por cotizar |
| Lote 3 | Software de gestión (plataforma, app, BI) | Por cotizar |
| Lote 4 | Sistema de pago electrónico | Por cotizar |
| Lote 5 | Implementación, capacitación, soporte | Por cotizar |

---

**Documento base:** Entregables E2.1, E2.2, E3.1, E3.2 del PROYECTO-003-2026-SETP-SINCELEJO  
**Elaborado por:** Innovadataco — 15 de junio de 2026
