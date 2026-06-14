# ENTREGABLE 3.1 — CONCEPTO DE OPERACIÓN TECNOLÓGICA DEL SETP

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E3.1  
**Versión:** 1.0  
**Fecha:** 15 de junio de 2026

---

## 1. RESUMEN EJECUTIVO

Este documento define el Concepto de Operación Tecnológica (ConOps) del SETP Sincelejo, estableciendo roles, procesos, indicadores de desempeño (KPIs), escenarios de operación y procedimientos que regirán el funcionamiento del sistema tecnológico.

---

## 2. ROLES Y RESPONSABILIDADES

### 2.1 Estructura Organizacional de Operación

```
                    DIRECCIÓN SETP
                         │
         ┌───────────────┼───────────────┐
         │               │               │
    OPERACIONES    TECNOLOGÍA      ADMINISTRACIÓN
         │               │               │
    ┌────┴────┐    ┌────┴────┐    ┌────┴────┐
    │Supervisor│    │Admin   │    │Financiero│
    │  Flota   │    │Sistema │    │          │
    ├─────────┤    ├─────────┤    ├─────────┤
    │Operador  │    │Soporte │    │Recaudo   │
    │Radio/Chat│    │Técnico │    │          │
    ├─────────┤    ├─────────┤    ├─────────┤
    │Conductor │    │Seguridad│   │Talento   │
    │          │    │Informática│  │Humano    │
    └─────────┘    └─────────┘    └─────────┘
```

### 2.2 Matriz de Roles

| Rol | Responsabilidades | Perfil |
|-----|-------------------|--------|
| **Director SETP** | Estrategia, gobierno, relaciones institucionales | Profesional >10 años exp. |
| **Supervisor de Flota** | Monitoreo, control, atención incidentes | Técnico/Profesional transporte |
| **Administrador de Sistema** | Configuración, mantenimiento, actualizaciones | Ingeniero sistemas |
| **Soporte Técnico** | Resolución de incidentes, mantenimiento preventivo | Técnico especializado |
| **Operador de Radio/Chat** | Comunicación con conductores, atención usuarios | Bachiller + capacitación |
| **Conductor** | Operación del vehículo, cumplimiento ruta | Licencia conducción C2/C3 |

---

## 3. PROCESOS OPERATIVOS

### 3.1 Proceso de Despacho

```
INICIO
  │
  ▼
┌──────────────────┐
│ 1. Programación  │──> Definir horarios, rutas, conductores
│    de Servicio   │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ 2. Pre-opera-    │──> Checklist vehículo, combustible, SOAT
│    ción          │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ 3. Despacho      │──> Asignación de ruta, validación tarjeta
│                  │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ 4. Monitoreo en  │──> Seguimiento GPS, tiempos, desvíos
│    Ruta          │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ 5. Cierre de     │──> Reporte de fallas, recaudo, kilometraje
│    Servicio      │
└────────┬─────────┘
         │
         ▼
        FIN
```

### 3.2 Proceso de Atención a Incidentes

| Paso | Acción | Responsable | SLA |
|------|--------|-------------|-----|
| 1 | Detección automática (GPS, sensor, reporte) | Sistema / Conductor | < 1 min |
| 2 | Alerta en Centro de Control | Sistema | Inmediato |
| 3 | Clasificación de incidente | Supervisor | < 5 min |
| 4 | Asignación de respuesta | Supervisor | < 10 min |
| 5 | Ejecución de protocolo | Equipo campo | < 30 min |
| 6 | Cierre y reporte | Supervisor | < 24 h |

### 3.3 Proceso de Recaudo y Conciliación

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│ Validación  │────>│  Backoffice │────>│ Conciliación│
│ a bordo     │     │  Pagos      │     │ Financiera  │
│ (Tiempo real)│    │  (Cada 15m) │     │  (Diaria)   │
└─────────────┘     └─────────────┘     └─────────────┘
       │                   │                   │
       ▼                   ▼                   ▼
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│ Tarjetas    │     │ Transacciones│    │ Reporte     │
│ sin contacto│     │ en BD        │     │ Recaudo     │
└─────────────┘     └─────────────┘     └─────────────┘
```

---

## 4. INDICADORES DE DESEMPEÑO (KPIs)

### 4.1 KPIs Operativos

| ID | Indicador | Fórmula | Meta | Frecuencia |
|----|-----------|---------|------|------------|
| KPI-01 | Cumplimiento de rutas | (Rutas completadas / Programadas) × 100 | > 95% | Diaria |
| KPI-02 | Puntualidad | (Salidas a tiempo / Total salidas) × 100 | > 90% | Diaria |
| KPI-03 | Velocidad promedio | Distancia total / Tiempo total | Según ruta | Diaria |
| KPI-04 | Desvíos | Número de desvíos no autorizados | < 2% | Semanal |
| KPI-05 | Incidentes | Número de incidentes / 10.000 km | < 5 | Mensual |

### 4.2 KPIs de Servicio al Usuario

| ID | Indicador | Fórmula | Meta | Frecuencia |
|----|-----------|---------|------|------------|
| KPI-06 | Satisfacción | Encuestas positivas / Total encuestas | > 85% | Mensual |
| KPI-07 | Tiempo espera | Tiempo promedio en parada | < 10 min | Diaria |
| KPI-08 | Información en tiempo real | % paradas con info actualizada | 100% | Continua |
| KPI-09 | Quejas | Número de quejas / 1.000 usuarios | < 5 | Mensual |

### 4.3 KPIs Tecnológicos

| ID | Indicador | Fórmula | Meta | Frecuencia |
|----|-----------|---------|------|------------|
| KPI-10 | Disponibilidad sistema | (Tiempo operativo / Tiempo total) × 100 | > 99.5% | Mensual |
| KPI-11 | Latencia GPS | Tiempo desde evento hasta visualización | < 5 seg | Continua |
| KPI-12 | Transacciones exitosas | (Transacciones OK / Total) × 100 | > 99.9% | Diaria |
| KPI-13 | Dispositivos online | (Dispositivos conectados / Total) × 100 | > 98% | Continua |

---

## 5. ESCENARIOS DE OPERACIÓN

### 5.1 Escenario Normal

Condiciones:
- Clima favorable
- Tráfico habitual
- Todos los sistemas operativos
- Personal completo

Operación:
- Ruta y horario según programación
- Monitoreo estándar
- Reportes periódicos

### 5.2 Escenario de Lluvia / Evento Climático

Activación: Alerta meteorológica o condiciones detectadas

Acciones:
1. Aumentar frecuencia de monitoreo
2. Activar protocolo de seguridad
3. Ajustar tiempos de ruta (hasta +20%)
4. Comunicar a usuarios vía app/pantallas
5. Preparar servicios de contingencia

### 5.3 Escenario de Falla Tecnológica

Activación: Pérdida de conectividad GPS, validador, etc.

Acciones:
1. Alerta automática a Centro de Control
2. Modo offline del bus (datos locales)
3. Protocolo de respaldo manual
4. Soporte técnico en ruta si es crítico
5. Registro de incidente para análisis

### 5.4 Escenario de Emergencia (Accidente, Seguridad)

Activación: Botón de pánico, sensor impacto, llamada de emergencia

Acciones:
1. Alerta inmediata a Centro de Control
2. Notificación a autoridades (policía, bomberos, ambulancia)
3. Activación de protocolo de evacuación
4. Aislamiento de ruta si es necesario
5. Servicios de contingencia
6. Reporte y análisis post-incidente

---

## 6. PROCEDIMIENTOS ESPECÍFICOS

### 6.1 Apertura y Cierre de Servicio

| Actividad | Responsable | Checklist |
|-----------|-------------|-----------|
| Inspección vehículo | Conductor | Luces, frenos, llantas, aceite |
| Encendido sistema | Conductor | GPS online, validador funcionando |
| Validación tarjeta | Conductor | Tarjeta de servicio activa |
| Cierre de servicio | Conductor | Reporte de novedades, recaudo |

### 6.2 Cambio de Turno

| Paso | Acción | Sistema |
|------|--------|---------|
| 1 | Conductor A finaliza turno | Registro hora fin |
| 2 | Conductor B inicia turno | Validación credencial |
| 3 | Transferencia de información | Estado del bus, recaudo parcial |
| 4 | Continuación de servicio | Nueva asignación si aplica |

---

## 7. CAPACITACIÓN Y MANTENIMIENTO

| Tema | Audiencia | Periodicidad |
|------|-----------|--------------|
| Operación del sistema | Conductores | Mensual (refresher) |
| Atención de incidentes | Supervisores | Trimestral |
| Mantenimiento preventivo | Soporte técnico | Mensual |
| Actualizaciones de sistema | Administradores | Según versión |
| Seguridad informática | Todo el personal | Semestral |

---

**Preparado por:** Innovadataco  
**Fecha:** 15 de junio de 2026  
**Aprobado por:** _________________________
