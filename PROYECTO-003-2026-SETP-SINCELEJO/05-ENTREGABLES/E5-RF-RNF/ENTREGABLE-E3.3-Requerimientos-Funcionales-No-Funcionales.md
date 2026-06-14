# ENTREGABLE 3.3 — REQUERIMIENTOS FUNCIONALES Y NO FUNCIONALES

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E3.3  
**Versión:** 1.0  
**Fecha:** 15 de junio de 2026

---

## 1. RESUMEN EJECUTIVO

Este documento define los requerimientos funcionales (RF) y no funcionales (RNF) del sistema tecnológico del SETP Sincelejo, basado en los **4 sistemas definidos desde 2015** (SRC, SGCF, SIU, SST) y el proceso de contratación 2023 con el MinTransporte (46 vehículos).

**Antecedentes:**
- **2015:** Steer Davies Gleave + GSD+ definieron SRC, SGCF, SIU y 3 escenarios institucionales
- **2022:** A4 Asociados actualizaron el modelo (Contrato CM-001-2022)
- **2023:** MinTransporte lanzó proceso de contratación ITS con 46 vehículos, agregando SST
- **2025:** RFI de Metro Sabanas integra 3 contratos (flota + tecnología + operación)
- **2026:** Esta consultoría estructura los requerimientos de los 4 sistemas existentes

**Mapeo Requerimientos ↔ Sistemas SETP:**
| Sistema SETP | Subsistemas en este documento | Requerimientos clave |
|--------------|------------------------------|----------------------|
| **SGCF** | Gestión de Flota (2.1) + Centro de Control (2.2) | RF-001 a RF-018 |
| **SRC** | Pago Electrónico (2.3) + Gestión Tarifaria (2.5) | RF-019 a RF-026, RF-032 a RF-035 |
| **SIU** | Información al Usuario (2.4) | RF-027 a RF-031 |
| **SST** | Seguridad transversal (RNF-011 a RNF-016) | RNF-011 a RNF-016 |

> **Alcance:** Esta consultoría define los **requerimientos funcionales y no funcionales** como parte de la estructuración. **NO incluye implementación, instalación, operación ni puesta en marcha**. El objetivo final es producir los **Estudios Previos ITS** para el proceso de licitación/contratación.

---

## 2. REQUERIMIENTOS FUNCIONALES (RF)

### 2.1 Módulo de Gestión de Flota

| ID | Requerimiento | Prioridad | Dependencia |
|----|--------------|-----------|-------------|
| RF-001 | El sistema debe rastrear la ubicación GPS de cada bus en tiempo real con actualizaciones cada 10-30 segundos | Alta | Ninguna |
| RF-002 | El sistema debe almacenar histórico de recorridos mínimo 2 años | Alta | RF-001 |
| RF-003 | El sistema debe generar alertas por desvío de ruta > 200 metros | Alta | RF-001 |
| RF-004 | El sistema debe detectar y registrar eventos de apertura/cierre de puertas | Media | Hardware onboard |
| RF-005 | El sistema debe contar embarques y desembarques de pasajeros | Media | Sensores |
| RF-006 | El sistema debe calcular y reportar velocidad promedio por tramo | Media | RF-001 |
| RF-007 | El sistema debe permitir asignación de rutas a conductores con horarios | Alta | RF-008 |
| RF-008 | El sistema debe mantener registro de conductores, licencias y turnos | Alta | Ninguna |
| RF-009 | El sistema debe generar alertas por exceso de velocidad | Alta | RF-001 |
| RF-010 | El sistema debe permitir comunicación bidireccional conductor-centro de control | Media | Radio/Chat |

### 2.2 Módulo de Centro de Control

| ID | Requerimiento | Prioridad | Dependencia |
|----|--------------|-----------|-------------|
| RF-011 | El sistema debe visualizar posición de todos los buses en mapa en tiempo real | Alta | RF-001 |
| RF-012 | El sistema debe permitir filtrar buses por ruta, estado, velocidad | Media | RF-011 |
| RF-013 | El sistema debe generar alertas automáticas por: detención prolongada, desvío, pánico, falla técnica | Alta | RF-001 |
| RF-014 | El sistema debe permitir configurar geocercas (zonas de interés) | Media | RF-011 |
| RF-015 | El sistema debe generar reportes operativos diarios, semanales y mensuales | Alta | RF-001 |
| RF-016 | El sistema debe integrar videovigilancia CCTV de buses y terminales | Media | Cámaras |
| RF-017 | El sistema debe permitir envío de mensajes masivos a conductores | Media | RF-010 |
| RF-018 | El sistema debe mantener registro de incidentes con clasificación y seguimiento | Alta | Ninguna |

### 2.3 Módulo de Pago Electrónico

| ID | Requerimiento | Prioridad | Dependencia |
|----|--------------|-----------|-------------|
| RF-019 | El sistema debe permitir pago con tarjeta sin contacto (NFC) | Alta | Validador |
| RF-020 | El sistema debe permitir recarga de tarjetas en puntos autorizados | Alta | RF-019 |
| RF-021 | El sistema debe permitir recarga en línea vía app o web | Media | App/Web |
| RF-022 | El sistema debe calcular tarifa según trayecto o tiempo | Alta | RF-019 |
| RF-023 | El sistema debe aplicar tarifas diferenciadas (estudiante, adulto mayor, etc.) | Media | RF-022 |
| RF-024 | El sistema debe generar reporte de recaudo diario conciliado | Alta | RF-019 |
| RF-025 | El sistema debe detectar y prevenir fraudes (tarjetas clonadas, doble pago) | Alta | RF-019 |
| RF-026 | El sistema debe funcionar en modo offline con sincronización posterior | Alta | Conectividad |

### 2.4 Módulo de Información al Usuario

| ID | Requerimiento | Prioridad | Dependencia |
|----|--------------|-----------|-------------|
| RF-027 | El sistema debe mostrar tiempos estimados de llegada en pantallas de paradas | Media | RF-001 |
| RF-028 | El sistema debe proporcionar información de rutas y horarios vía app móvil | Media | App |
| RF-029 | El sistema debe enviar notificaciones push de demoras o cambios de ruta | Baja | App |
| RF-030 | El sistema debe permitir reporte de incidencias por parte de usuarios | Baja | App |
| RF-031 | El sistema debe integrar información con Google Maps/Waze | Baja | API externa |

### 2.5 Módulo de Gestión Tarifaria

| ID | Requerimiento | Prioridad | Dependencia |
|----|--------------|-----------|-------------|
| RF-032 | El sistema debe permitir configuración de tarifas base por ruta | Alta | Ninguna |
| RF-033 | El sistema debe gestionar subsidios de transporte por categoría de usuario | Media | RF-023 |
| RF-034 | El sistema debe generar reportes de subsidios para entes reguladores | Media | RF-033 |
| RF-035 | El sistema debe soportar tarifas dinámicas por demanda (peak/off-peak) | Baja | RF-032 |

---

## 3. REQUERIMIENTOS NO FUNCIONALES (RNF)

### 3.1 Rendimiento

| ID | Requerimiento | Métrica | Prioridad |
|----|--------------|---------|-----------|
| RNF-001 | Latencia de actualización GPS | < 5 segundos desde evento | Alta |
| RNF-002 | Tiempo de respuesta de API | < 200 ms para consultas simples | Alta |
| RNF-003 | Tiempo de respuesta de dashboard | < 3 segundos para carga inicial | Media |
| RNF-004 | Throughput de transacciones | > 100 TPS en hora pico | Alta |
| RNF-005 | Capacidad de almacenamiento | Escalable a 5 años de datos históricos | Media |

### 3.2 Disponibilidad y Confiabilidad

| ID | Requerimiento | Métrica | Prioridad |
|----|--------------|---------|-----------|
| RNF-006 | Disponibilidad del sistema | > 99.5% mensual | Alta |
| RNF-007 | Disponibilidad del servicio de pago | > 99.9% | Alta |
| RNF-008 | Recuperación ante desastres | RTO < 4 horas, RPO < 1 hora | Alta |
| RNF-009 | Tolerancia a fallos de red | Operación offline > 24 horas | Alta |
| RNF-010 | Redundancia de comunicaciones | 4G + WiFi backup | Media |

### 3.3 Seguridad

| ID | Requerimiento | Métrica | Prioridad |
|----|--------------|---------|-----------|
| RNF-011 | Cifrado de comunicaciones | TLS 1.3 para todo tráfico | Alta |
| RNF-012 | Cifrado de datos sensibles | AES-256 en reposo | Alta |
| RNF-013 | Autenticación multi-factor | MFA para usuarios administrativos | Alta |
| RNF-014 | Auditoría de accesos | Registro de toda acción crítica | Alta |
| RNF-015 | Prevención de intrusión | WAF, IDS/IPS activo | Media |
| RNF-016 | Cumplimiento PCI DSS | Si aplica para pagos | Alta |

### 3.4 Escalabilidad

| ID | Requerimiento | Métrica | Prioridad |
|----|--------------|---------|-----------|
| RNF-017 | Escalabilidad horizontal | Soportar 3x flota sin rediseño | Media |
| RNF-018 | Escalabilidad de usuarios | Soportar 100.000 usuarios activos | Media |
| RNF-019 | Escalabilidad de transacciones | 10x carga actual | Media |
| RNF-020 | Despliegue automático | CI/CD con zero-downtime | Media |

### 3.5 Usabilidad

| ID | Requerimiento | Métrica | Prioridad |
|----|--------------|---------|-----------|
| RNF-021 | Tiempo de aprendizaje conductor | < 2 horas | Alta |
| RNF-022 | Interfaz intuitiva centro de control | < 5 clics para funciones comunes | Media |
| RNF-023 | Accesibilidad app móvil | WCAG 2.1 AA | Media |
| RNF-024 | Soporte multi-idioma | Español (inicial), inglés opcional | Baja |
| RNF-025 | Diseño responsive | Adaptable a tablets y móviles | Media |

### 3.6 Mantenibilidad

| ID | Requerimiento | Métrica | Prioridad |
|----|--------------|---------|-----------|
| RNF-026 | Actualizaciones OTA | Sin intervención física | Alta |
| RNF-027 | Tiempo de mantenimiento correctivo | MTTR < 4 horas | Alta |
| RNF-028 | Documentación técnica | Completa y actualizada | Media |
| RNF-029 | Monitoreo proactivo | Alertas antes de falla | Media |
| RNF-030 | Logs estructurados | JSON, centralizados, indexados | Media |

### 3.7 Interoperabilidad

| ID | Requerimiento | Métrica | Prioridad |
|----|--------------|---------|-----------|
| RNF-031 | Integración SRC-SGCF-SIU-SST | Protocolo interno del SETP | Alta |
| RNF-032 | Interoperabilidad Resolución 20203040034065 | Estándares MinTransporte | Alta |
| RNF-033 | Formato de datos GPS | NMEA 0183 compatible | Media |
| RNF-034 | Exportación de reportes | PDF, Excel, CSV | Media |
| RNF-035 | API pública documentada | OpenAPI 3.0 | Media |

### 3.8 Cumplimiento Normativo

| ID | Requerimiento | Norma | Prioridad |
|----|--------------|-------|-----------|
| RNF-036 | Cumplimiento Decreto 393/2010 | Transporte público | Alta |
| RNF-037 | Cumplimiento Decreto 482/2023 | Modificación 393 | Alta |
| RNF-038 | Cumplimiento Resolución 28675/2022 | PMITS | Alta |
| RNF-039 | Protección de datos personales | Ley 1581 de 2012 | Alta |
| RNF-040 | Accesibilidad | Decreto 1496 de 2015 | Media |

---

## 4. MATRIZ DE TRAZABILIDAD

| RF/RNF | Entregable | Diseño | Test | Estado |
|--------|-----------|--------|------|--------|
| RF-001 | E2.2, E3.2 | Arquitectura | GPS Test | Pendiente |
| RF-011 | E2.2, E3.2 | Centro Control | Visualización | Pendiente |
| RF-019 | E3.2 | Pagos | NFC Test | Pendiente |
| RNF-001 | E3.2 | Performance | Latencia | Pendiente |
| RNF-006 | E3.2 | Infraestructura | Uptime | Pendiente |

---

## 5. GLOSARIO

| Término | Definición |
|---------|------------|
| **RF** | Requerimiento Funcional |
| **RNF** | Requerimiento No Funcional |
| **GPS** | Global Positioning System |
| **NFC** | Near Field Communication |
| **RTO** | Recovery Time Objective |
| **RPO** | Recovery Point Objective |
| **TPS** | Transactions Per Second |
| **MFA** | Multi-Factor Authentication |
| **OTA** | Over-The-Air (actualizaciones) |
| **MTTR** | Mean Time To Repair |

---

**Preparado por:** Innovadataco  
**Fecha:** 15 de junio de 2026  
**Aprobado por:** _________________________
