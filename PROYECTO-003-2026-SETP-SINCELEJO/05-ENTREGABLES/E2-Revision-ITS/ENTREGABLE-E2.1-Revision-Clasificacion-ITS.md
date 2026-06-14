# ENTREGABLE 2.1 — REVISIÓN Y CLASIFICACIÓN DE SERVICIOS ITS

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E2.1  
**Versión:** 1.0  
**Fecha:** 15 de junio de 2026

---

## 1. RESUMEN EJECUTIVO

Este documento presenta la revisión y clasificación de los Servicios de Sistemas Inteligentes de Transporte (ITS) y subsistemas tecnológicos aplicables al Sistema Estratégico de Transporte Público de Sincelejo (SETP), basado en la normativa colombiana vigente y las mejores prácticas internacionales.

---

## 2. MARCO NORMATIVO

### 2.1 Normativa Nacional

| Documento | Año | Aplicación |
|-----------|-----|------------|
| Decreto 393 de 2010 | 2010 | Regulación transporte público |
| Decreto 482 de 2023 | 2023 | Modificación Decreto 393 |
| Decreto 2060 de 2015 | 2015 | Estrategia Nacional ITS |
| Resolución 28675 de 2022 | 2022 | Plan Maestro ITS Colombia (PMITS) |
| Resolución 20203040034065 | 2020 | Estándares ITS |
| Resolución 20223040028675 | 2022 | PMITS |

### 2.2 Estándares Internacionales

| Estándar | Descripción |
|----------|-------------|
| ISO 14813-1 | Framework de ITS |
| ISO 14813-5 | Referencia de servicios ITS |
| ISO 14813-6 | Identificación de usuarios |
| NTC 6203 | Sistemas inteligentes de transporte |

---

## 3. CLASIFICACIÓN DE SERVICIOS ITS

### 3.1 Taxonomía ISO 14813

Los servicios ITS se clasifican en 5 dominios principales:

```
SERVICIOS ITS
├── 1. Servicios de Tráfico y Gestión Vial
│   ├── Control de tráfico urbano
│   ├── Gestión de incidentes
│   ├── Información al viajero
│   └── Control de peajes
├── 2. Servicios de Transporte Público
│   ├── Gestión de flota
│   ├── Información al usuario
│   ├── Prioridad semafórica
│   └── Gestión tarifaria
├── 3. Servicios de Mercancías y Logística
│   ├── Gestión de flotas comerciales
│   └── Intercambio electrónico de datos
├── 4. Servicios de Seguridad Vial
│   ├── Asistencia en emergencias
│   ├── Gestión de vehículos peligrosos
│   └── Prevención de accidentes
└── 5. Servicios de Apoyo y Complementarios
    ├── Pago electrónico
    ├── Información meteorológica
    └── Reservas y viajes combinados
```

---

## 4. SUBSISTEMAS ITS APLICABLES AL SETP

### 4.1 Subsistema de Gestión de Flota (ATMS + APTS)

| Componente | Descripción | Prioridad |
|------------|-------------|-----------|
| GPS/GNSS | Localización satelital de buses | Alta |
| OBD-II | Diagnóstico a bordo | Media |
| Comunicaciones M2M | Transmisión datos flota | Alta |
| Pantallas a bordo | Información al pasajero | Media |

### 4.2 Subsistema de Centro de Control

| Componente | Descripción | Prioridad |
|------------|-------------|-----------|
| Software CVP | Plataforma de visualización | Alta |
| Servidores | Infraestructura computacional | Alta |
| CCTV | Videovigilancia | Media |
| Almacenamiento | Base de datos histórica | Alta |

### 4.3 Subsistema de Información al Usuario

| Componente | Descripción | Prioridad |
|------------|-------------|-----------|
| Aplicación móvil | Info en tiempo real | Media |
| Pantallas LED en paradas | Tiempos de espera | Media |
| SMS/WhatsApp | Notificaciones | Baja |
| Web portal | Planificación de viajes | Media |

### 4.4 Subsistema de Pago Electrónico

| Componente | Descripción | Prioridad |
|------------|-------------|-----------|
| Validadores a bordo | Lectura tarjetas | Alta |
| Sistema backoffice | Conciliación financiera | Alta |
| Tarjetas sin contacto | Medio de pago | Alta |
| Portal de recargas | Recarga en línea | Media |

### 4.5 Subsistema de Gestión Tarifaria

| Componente | Descripción | Prioridad |
|------------|-------------|-----------|
| Motor tarifario | Cálculo de tarifas | Alta |
| Integración subsidies | Subsidios de transporte | Media |
| Reportes financieros | Consolidación | Alta |

---

## 5. MATRIZ DE PRIORIZACIÓN

| Subsistema | Impacto Operativo | Complejidad Técnica | Costo | Prioridad |
|------------|-------------------|---------------------|-------|-----------|
| Gestión de Flota | Alto | Media | Medio | **1 - Crítico** |
| Centro de Control | Alto | Alta | Alto | **1 - Crítico** |
| Pago Electrónico | Alto | Alta | Alto | **1 - Crítico** |
| Información al Usuario | Medio | Media | Medio | **2 - Importante** |
| Gestión Tarifaria | Medio | Media | Medio | **2 - Importante** |

---

## 6. REQUERIMIENTOS DE INTEROPERABILIDAD

### 6.1 Con Sistemas Nacionales

| Sistema | Interfaz | Datos |
|---------|----------|-------|
| SRC | Sistema de Recaudo Centralizado | Recaudo, tarjetas |
| SGCF | Sistema de Gestión y Control de Flota | GPS, operación |
| SIU | Sistema de Información al Usuario | Web, app, pantallas |
| SST | Sistema de Seguridad de Transacciones | Seguridad, cifrado |

### 6.2 Estándares de Comunicación

- **DSRC:** WAVE IEEE 802.11p
- **Celular:** 4G/LTE, 5G ready
- **Satelital:** GPS/GNSS, GLONASS
- **Protocolos:** NTCIP, SAE J2735, GTFS-RT

---

## 7. RECOMENDACIONES

1. **Priorizar** subsistemas críticos: Gestión de Flota, Centro de Control, Pago Electrónico
2. **Adoptar** arquitectura modular para escalabilidad futura
3. **Garantizar** interoperabilidad con sistemas nacionales desde el diseño
4. **Considerar** soluciones cloud-híbridas para reducir CAPEX inicial
5. **Planificar** fases de implementación por prioridad operacional

---

## 8. GLOSARIO

| Término | Definición |
|---------|------------|
| **ITS** | Intelligent Transportation Systems |
| **SETP** | Sistema Estratégico de Transporte Público |
| **ATMS** | Advanced Traffic Management System |
| **APTS** | Advanced Public Transportation System |
| **CVP** | Centro de Visualización y Procesamiento |
| **OBD-II** | On-Board Diagnostics |
| **DSRC** | Dedicated Short Range Communications |
| **GTFS-RT** | General Transit Feed Specification - Realtime |

---

**Preparado por:** Innovadataco  
**Fecha:** 15 de junio de 2026  
**Aprobado por:** _________________________
