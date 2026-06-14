# ENTREGABLE 2.2 — ARQUITECTURA TECNOLÓGICA CONCEPTUAL DEL SETP

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E2.2  
**Versión:** 1.0  
**Fecha:** 15 de junio de 2026

---

## 1. RESUMEN EJECUTIVO

Este documento define la arquitectura tecnológica conceptual del SETP Sincelejo, basada en los **4 sistemas definidos desde 2015** (Steer Davies Gleave + GSD+) y actualizados en la consultoría 2022 (A4 Asociados, CM-001-2022) y el proceso de contratación 2023 (MinTransporte, Resolución 20203040034065).

**Antecedentes:**
- **2015:** Estructuración tecnológica inicial (SRC, SGCF, SIU)
- **2022:** Actualización modelo de transporte (Contrato CM-001-2022)
- **2023:** Proceso contratación ITS con MinTransporte (46 vehículos, agregado SST)
- **2025:** RFI integración 3 contratos (flota + tecnología + operación)

**Los 4 sistemas del SETP Sincelejo:**
1. **SRC** — Sistema de Recaudo Centralizado (pago efectivo + tarjeta sin contacto)
2. **SGCF** — Sistema de Gestión y Control de Flota (GPS, programación, supervisión)
3. **SIU** — Sistema de Información al Usuario (web, app, pantallas, call center)
4. **SST** — Sistema de Seguridad de Transacciones (cifrado, seguridad, auditoría)

> **Nota:** Esta consultoría NO propone integraciones con SISPROV, RUNT, SIMAT o SICOV. Esos sistemas nacionales NO fueron definidos en el proyecto de Sincelejo (2015-2023) y NO aparecen en ningún documento contractual del SETP.

---

## 2. PRINCIPIOS ARQUITECTÓNICOS

| Principio | Descripción |
|-----------|-------------|
| **Modularidad** | Componentes independientes e intercambiables |
| **Escalabilidad** | Capacidad de crecer sin rediseño |
| **Interoperabilidad** | Integración con sistemas del SETP (SRC, SGCF, SIU, SST) y estándares de la Resolución 20203040034065 |
| **Seguridad** | Protección de datos y comunicaciones |
| **Disponibilidad** | 99.5% uptime en operación crítica |
| **Mantenibilidad** | Facilidad de actualización y soporte |

---

## 3. VISTA ARQUITECTURAL GENERAL

```
┌─────────────────────────────────────────────────────────────┐
│                    CAPA DE PRESENTACIÓN                      │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐       │
│  │   App    │ │  Portal  │ │ Pantallas│ │  CMS     │       │
│  │  Móvil   │ │   Web    │ │  Paradas │ │  Web     │       │
│  └────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘       │
├───────┼────────────┼────────────┼────────────┼──────────────┤
│       │            │      CAPA DE APLICACIÓN                 │
│  ┌────┴────────────┴────────────┴────────────┐               │
│  │         API Gateway / BFF                  │               │
│  └────┬───────────────────────────────────┬───┘               │
│       │                                   │                   │
│  ┌────┴────┐ ┌─────────┐ ┌─────────┐ ┌───┴────┐            │
│  │Gestión  │ │Informa- │ │ Gestión │ │Gestión │            │
│  │  Flota  │ │  ción   │ │  Pagos  │ │Tarifas │            │
│  └────┬────┘ └────┬────┘ └────┬────┘ └───┬────┘            │
├───────┼───────────┼───────────┼──────────┼─────────────────┤
│       │           │     CAPA DE PROCESOS   │                 │
│  ┌────┴───────────┴───────────┴──────────┴────┐              │
│  │        Motor de Reglas / BPMN               │              │
│  │    ┌─────────┐ ┌─────────┐ ┌─────────┐     │              │
│  │    │ Routing │ │ Algorit │ │ Alertas │     │              │
│  │    │ Óptimo  │ │  mos ML │ │Inteligen│     │              │
│  │    └─────────┘ └─────────┘ └─────────┘     │              │
│  └────┬───────────────────────────────────────┘              │
├───────┼───────────────────────────────────────────────────────┤
│       │          CAPA DE INTEGRACIÓN                         │
│  ┌────┴────────────────────────────────────────┐             │
│  │  ESB / Bus de Integración / Message Queue   │             │
│  │  ┌────────┐ ┌────────┐ ┌────────┐ ┌──────┐  │             │
│  │  │SRC │ │  SGCF  │ │ SIU  │ │SST │  │             │
│  │  │Adapter │ │Adapter │ │Adapter │ │Adapt │  │             │
│  │  └────────┘ └────────┘ └────────┘ └──────┘  │             │
│  └────┬────────────────────────────────────────┘             │
├───────┼───────────────────────────────────────────────────────┤
│       │          CAPA DE DATOS                               │
│  ┌────┴────────────┐ ┌──────────────┐ ┌──────────────┐      │
│  │   Base Datos    │ │ Data Lake /  │ │   Cache /    │      │
│  │  Transaccional  │ │ Data Warehouse│ │   CDN        │      │
│  │   (PostgreSQL)  │ │  (BigQuery)   │ │  (Redis)     │      │
│  └─────────────────┘ └──────────────┘ └──────────────┘      │
├─────────────────────────────────────────────────────────────┤
│                    CAPA DE INFRAESTRUCTURA                   │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────────────┐   │
│  │   Cloud     │ │  Kubernetes │ │    CI/CD / DevOps   │   │
│  │  (AWS/GCP)  │ │   Cluster   │ │    Pipelines        │   │
│  └─────────────┘ └─────────────┘ └─────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

---

## 4. SUBSISTEMAS DETALLADOS

### 4.1 Subsistema de Gestión de Flota

| Componente | Tecnología | Función |
|------------|-----------|---------|
| Rastreador GPS | GNSS multi-constelación | Localización en tiempo real |
| Unidad de control | ARM Cortex / Raspberry Pi | Procesamiento edge |
| Comunicaciones | 4G/LTE + WiFi | Conectividad |
| Sensor puertas | Reed switch / IR | Detección apertura/cierre |
| Contador pasajeros | IR / ToF | Conteo de embarques |
| Pantalla conductor | LCD 7" | Info de ruta y turno |

**Arquitectura de comunicación:**
```
Bus ──> Rastreador ──> 4G/LTE ──> VPN ──> API Gateway ──> BD
        │
        ├──> Sensor puertas
        ├──> Contador pasajeros
        └──> Pantalla conductor
```

### 4.2 Subsistema Centro de Control

| Componente | Especificación |
|------------|---------------|
| Servidores aplicación | 2x VMs (HA) — 8 vCPU, 32 GB RAM |
| Base de datos | PostgreSQL 15 — Replicación master-slave |
| Almacenamiento | 2 TB SSD — RAID 10 |
| Red | VLAN segregada — Firewall perimetral |
| UPS | 2 kVA — 30 min autonomía |
| CCTV | NVR 32 canales — 30 días retención |

### 4.3 Subsistema de Pago Electrónico

```
┌──────────────┐      ┌──────────────┐      ┌──────────────┐
│   Tarjeta    │─────>│  Validador   │─────>│  Backoffice  │
│  Sin Contacto│ NFC  │   a Bordo    │ 4G   │   Pagos      │
│  (Mifare DES)│      │ (Android POS)│      │  (Transacc)  │
└──────────────┘      └──────────────┘      └──────┬───────┘
                                                   │
              ┌────────────────────────────────────┘
              │
       ┌──────┴──────┐      ┌──────────────┐
       │   Pasarela  │─────>│   Banco /    │
       │   Pagos     │      │   ACH        │
       │ (Redeban)   │      │              │
       └─────────────┘      └──────────────┘
```

---

## 5. DIAGRAMA DE RED

```
                    INTERNET
                       │
              ┌────────┴────────┐
              │   Firewall /    │
              │   WAF / DDoS    │
              └────────┬────────┘
                       │
              ┌────────┴────────┐
              │   Load Balancer │
              │   (CloudFlare)  │
              └────────┬────────┘
                       │
         ┌─────────────┼─────────────┐
         │             │             │
    ┌────┴────┐  ┌────┴────┐  ┌────┴────┐
    │   API   │  │  Portal │  │  App    │
    │ Gateway │  │   Web   │  │ Mobile  │
    └────┬────┘  └─────────┘  └─────────┘
         │
    ┌────┴────────────────────────────┐
    │      PRIVATE SUBNET (VPN)       │
    │  ┌────────┐  ┌────────┐        │
    │  │  App   │  │   BD   │        │
    │  │Server  │  │Postgre │        │
    │  │  (K8s) │  │  SQL   │        │
    │  └────────┘  └────────┘        │
    │                                 │
    │  ┌────────┐  ┌────────┐        │
    │  │  NVR   │  │  VPN   │        │
    │  │  CCTV  │  │ Server │        │
    │  └────────┘  └────────┘        │
    └─────────────────────────────────┘
              │
         ┌────┴────┐
         │  4G/LTE │
         │  VPN    │
         └────┬────┘
              │
         ┌────┴────┐
         │   BUS   │
         │ (Onboard│
         │  Unit)  │
         └─────────┘
```

---

## 6. ESPECIFICACIONES TÉCNICAS BASE

### 6.1 Hardware Onboard

| Componente | Especificación mínima |
|------------|----------------------|
| Procesador | ARM Cortex-A72, 4 núcleos @ 1.5 GHz |
| RAM | 4 GB LPDDR4 |
| Almacenamiento | 64 GB eMMC |
| Conectividad | 4G Cat-4, WiFi 802.11ac, Bluetooth 5.0 |
| GPS | U-Blox NEO-M9N, multi-GNSS |
| Entradas | 4x GPIO, 2x RS-485, 1x CAN |
| Alimentación | 9-36V DC, protección transitorios |
| Temperatura | -20°C a +70°C |
| Certificación | IP65, EMC automotriz |

### 6.2 Software Base

| Capa | Tecnología |
|------|-----------|
| SO | Yocto Linux / Ubuntu Core |
| Contenedores | Docker |
| Orquestación | Kubernetes (edge) |
| Base de datos | PostgreSQL 15 |
| Cache | Redis |
| Mensajería | MQTT / Apache Kafka |
| API | REST + GraphQL |
| Frontend | React / Flutter |

---

## 7. PLAN DE CAPACIDAD

| Métrica | Inicial | Año 1 | Año 3 |
|---------|---------|-------|-------|
| Vehículos monitoreados | 46 | 50 | 100 |
| Usuarios activos/día | 10.000 | 15.000 | 30.000 |
| Transacciones/día | 15.000 | 25.000 | 60.000 |
| Eventos GPS/seg | 10 | 25 | 60 |
| Almacenamiento/mes | 50 GB | 120 GB | 300 GB |

---

## 8. RECOMENDACIONES DE IMPLEMENTACIÓN

1. **Fase 1 (Meses 1-3):** Infraestructura base + gestión de flota
2. **Fase 2 (Meses 4-6):** Pago electrónico + información al usuario
3. **Fase 3 (Meses 7-9):** Integraciones externas + optimizaciones
4. **Fase 4 (Meses 10-12):** Analytics avanzado + ML

---

**Preparado por:** Innovadataco  
**Fecha:** 15 de junio de 2026  
**Aprobado por:** _________________________
