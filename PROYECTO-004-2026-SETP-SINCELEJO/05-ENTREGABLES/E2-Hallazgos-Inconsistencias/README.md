# PROYECTO-004-2026-SETP-SINCELEJO
## Documento 2: Inconsistencias, Hallazgos y Vacíos Técnicos
### Análisis Crítico de la Documentación SETP Sincelejo — Componente Tecnológico ITS

---

**Versión:** 1.0  
**Fecha:** Mayo 2026  
**Cliente:** METRO SABANAS S.A.S. / Sincelejo  
**Consultor:** INNOVADATACO  
**Clasificación:** CONFIDENCIAL — USO INTERNO  

---

## TABLA DE CONTENIDO

1. Resumen Ejecutivo de Hallazgos
2. Metodología de Análisis
3. Inconsistencias Críticas
4. Vacíos Estructurales
5. Documentación Faltante
6. Incongruencias de Flota
7. Presupuesto ITS — Vacíos Detectados
8. Riesgos por Hallazgos
9. Recomendaciones de Remediación
10. Matriz de Seguimiento

---

## 1. RESUMEN EJECUTIVO DE HALLAZGOS

Tras revisión exhaustiva de la documentación del SETP Sincelejo (incluyendo entregables 5-8, antecedentes, RFI 2025, MS-130-2025, RFI Autobuses 2022, y presupuesto ITS), se han identificado **37 hallazgos críticos** clasificados en:

| Categoría | Cantidad | Severidad |
|:---|:---|:---|
| **Inconsistencias críticas** | 8 | 🔴 Bloqueantes |
| **Vacíos estructurales** | 12 | 🟡 Mayores |
| **Documentación faltante** | 11 | 🟡 Mayores |
| **Incongruencias de flota** | 3 | 🔴 Bloqueantes |
| **Presupuesto en $0** | 3 | 🔴 Bloqueantes |

**Hallazgo más crítico:** El Excel de presupuesto ITS de METRO SABANAS tiene **TODOS los valores unitarios en $0**, haciendo imposible cualquier análisis financiero del componente tecnológico.

---

## 2. METODOLOGÍA DE ANÁLISIS

### Documentos Revisados

| Documento | Estado | Hallazgos |
|:---|:---|:---|
| ENTREGABLE 5 — Especificaciones Técnicas | ✅ Revisado | Tecnología mencionada sin profundidad |
| ENTREGABLE 6 — Informe Definitivo | ✅ Revisado | ITS descrito superficialmente |
| ENTREGABLE 7 — Estructuración Financiera | ✅ Revisado | No desagrega componente ITS |
| ENTREGABLE 8 — Modelo Financiero Excel | ✅ Revisado | **Valores en $0** |
| ANTECEDENTES — Estudios previos 2023 | ✅ Revisado | 46 buses, sin ITS detallado |
| MS-130-2025 — Justificación reducción | ✅ Revisado | 34 buses, ITS no mencionado |
| RFI 2025 — Solicitud información | ✅ Revisado | 75 buses, "cloud-first", sin detalle técnico |
| RFI Autobuses oct 2022 | ✅ Revisado | Solo especificaciones vehiculares, **sin ITS embarcado** |
| Presupuesto ITS MetroSabanas Excel | ✅ Revisado | **Plantilla vacía, $0 en todos los campos** |

### Criterios de Evaluación

1. **Completitud:** ¿La documentación cubre todo el componente ITS?
2. **Consistencia:** ¿Los números coinciden entre documentos?
3. **Profundidad técnica:** ¿Hay especificaciones detalladas?
4. **Ejecutividad:** ¿Se puede licitar/implementar con esta información?

---

## 3. INCONSISTENCIAS CRÍTICAS (🔴 BLOQUEANTES)

### IC-01: Incongruencia de Flota — 34 vs 46 vs 75 Buses

| Documento | Flota | Contexto |
|:---|:---|:---|
| **Estudios previos 2023 (ANTECEDENTES)** | 46 microbuses | Fase 1, presupuesto máximo $3.793.756.953 |
| **MS-130-2025 (Oficial actual)** | 34 buses | Sistema reducido, 5 rutas, 7.670 pax/día |
| **RFI 2025 (Solicitud internacional)** | 75 buses | "cloud-first", APIs modernas |

**Problema:** ¿El componente ITS se diseña para 34, 46, o 75 buses? Cada escenario implica:
- Diferente cantidad de equipamiento a bordo
- Diferente capacidad de servidores CCO
- Diferente ancho de banda
- Diferente inversión total

**Impacto:** No se puede dimensionar la arquitectura ITS sin definir la flota objetivo.

**Recomendación:** METRO SABANAS debe definir flota definitiva antes de cualquier diseño técnico.

---

### IC-02: Presupuesto ITS — Todos los Valores en $0

**Documento:** `presupuesto_ITS_MetroSabanas.xlsx` (extraído de carpeta ANTECEDENTES)

**Hallazgo:** La plantilla contiene:
- ✅ Columnas de componentes (descripción, cantidad, unidad)
- ✅ Estructura por categorías (SRC, SGCF, SIU, SST)
- ❌ **TODOS los campos de valor unitario están en $0**
- ❌ **TODOS los campos de valor total están en $0**

**Evidencia:**
```
Componente          | Cantidad | Unidad | V.Unitario | V.Total
GPS Tracker Bus     | 34       | Und    | $0         | $0
Validador NFC       | 68       | Und    | $0         | $0
Pantalla LED Paradero| 40      | Und    | $0         | $0
Router 4G Bus       | 34       | Und    | $0         | $0
CCTV Interior Bus   | 136      | Und    | $0         | $0
Botón Pánico        | 68       | Und    | $0         | $0
... (TODOS $0)
```

**Impacto:** Imposible:
- Estimar inversión total del componente ITS
- Comparar proveedores
- Construir modelo financiero
- Presentar a inversionistas

**Recomendación:** Diligenciar con valores de mercado o contratar estudio de precios.

---

### IC-03: RFI 2025 Menciona 75 Buses Pero Sin Detalle Técnico ITS

**Documento:** RFI 2025

**Hallazgo:** El RFI solicita información de "75 buses con tecnología cloud-first y APIs modernas" pero:
- No especifica qué tecnología ITS se requiere
- No define estándares de conectividad
- No menciona CCTV, validadores, o sistemas de recaudo
- No establece requisitos de ciberseguridad

**Impacto:** Proveedores no pueden cotizar sin especificaciones técnicas.

**Recomendación:** Complementar RFI con Especificaciones Técnicas Particulares (ETP) del componente ITS.

---

### IC-04: RFI Autobuses 2022 Solo Especifica Vehículo, No Tecnología

**Documento:** RFI Autobuses octubre 2022

**Hallazgo:** El documento detalla exhaustivamente:
- Motor Euro VI / GNV / Eléctrico
- Dimensiones, capacidad, accesibilidad PMR
- Autonomía, consumo

**Pero NO menciona:**
- GPS / rastreo
- Validadores de pasajeros
- Pantallas de información
- CCTV
- Conectividad 4G/5G
- Botón de pánico

**Impacto:** Los buses podrían entregarse sin preparación eléctrica ni mecánica para instalar ITS.

**Recomendación:** Emitir adenda al RFI de buses incluyendo especificaciones de preparación para ITS.

---

### IC-05: No Se Define Medio de Pago Ni Tarifa

**Hallazgo:** Ningún documento define:
- ¿Efectivo, tarjeta, o ambos?
- ¿Tarifa plana o por zonas?
- ¿Tarjeta propia o interoperable nacional?
- ¿Sistema de recarga?

**Impacto:** No se puede diseñar el SGCF sin conocer el modelo de pago.

**Recomendación:** Definir modelo tarifario y de pago antes de diseñar sistema de recaudo.

---

### IC-06: No Se Define Ubicación del CCO

**Hallazgo:** Ningún documento especifica:
- Dirección del Centro de Control
- Dimensiones mínimas
- Requerimientos eléctricos
- Conectividad disponible en ubicación

**Impacto:** No se puede diseñar infraestructura CCO ni estimar costos.

**Recomendación:** Definir ubicación CCO y realizar visita técnica.

---

### IC-07: No Se Define Cantidad de Paraderos

**Hallazgo:** Ningún documento establece:
- Número exacto de paraderos
- Tipología (básico, intermedio, terminal)
- Ubicaciones específicas
- Equipamiento por tipo

**Impacto:** No se puede dimensionar sistema de información a usuarios ni estimar inversión.

**Recomendación:** Realizar estudio de demanda y ubicación de paraderos.

---

### IC-08: No Se Menciona Ciberseguridad en Ningún Documento

**Hallazgo:** Revisados 9 documentos principales:
- Ninguno menciona ciberseguridad ITS
- Ninguno menciona protección de datos de recaudo
- Ninguno menciona cumplimiento Ley 1581/2012
- Ninguno menciona estándares ISO 27001 o IEC 62443

**Impacto:** El sistema podría operar sin protección adecuada, exponiendo:
- Datos financieros de pasajeros
- Información operativa estratégica
- Sistema a ataques ransomware

**Recomendación:** Incluir capítulo de ciberseguridad en todos los documentos técnicos.

---

## 4. VACÍOS ESTRUCTURALES (🟡 MAYORES)

### VE-01: Sin Arquitectura ITS Definida

**Hallazgo:** No existe documento que defina:
- Arquitectura de referencia (4 niveles)
- Subsistemas integrados
- Flujos de información
- Interfaces entre sistemas

**Impacto:** Riesgo de crear silos tecnológicos incompatibles.

---

### VE-02: Sin Concepto de Operación ITS

**Hallazgo:** No hay documento que describa:
- Cómo opera el CCO 24/7
- Protocolos ante incidentes
- Turnos de operadores
- Flujo de información en emergencias

**Impacto:** El sistema podría no ser operable adecuadamente.

---

### VE-03: Sin Especificaciones de Equipamiento a Bordo

**Hallazgo:** No existen fichas técnicas de:
- GPS tracker
- Validador NFC
- Pantalla interior bus
- Cámaras CCTV
- Router 4G/5G
- Botón de pánico

**Impacto:** No se puede licitar equipamiento sin especificaciones.

---

### VE-04: Sin Especificaciones de Paraderos Inteligentes

**Hallazgo:** No hay diseño de:
- Tipologías de paradero
- Pantallas LED
- Sistema de alimentación (solar/eléctrica)
- Protección anti-vandalismo

**Impacto:** Los paraderos podrían no cumplir función informativa.

---

### VE-05: Sin Definición de Plataforma SaaS vs On-Premise

**Hallazgo:** No se decide:
- ¿Plataforma en nube (AWS/Azure/GCP) o servidores locales?
- ¿Software propio o licenciado?
- ¿Quién opera la plataforma?

**Impacto:** Decisiones arquitectónicas fundamentales pendientes.

---

### VE-06: Sin Definición de Conectividad

**Hallazgo:** No se especifica:
- Operador celular preferido
- Tipo de red (4G/5G)
- Arquitectura de red (VPN, SD-WAN)
- Respaldo de comunicaciones

---

### VE-07: Sin Plan de Implementación

**Hallazgo:** No existe cronograma de:
- Adquisición de equipamiento
- Instalación por fases
- Pruebas y aceptación
- Capacitación
- Puesta en marcha

---

### VE-08: Sin Requerimientos Funcionales Documentados

**Hallazgo:** No hay documento RF que establezca:
- Qué debe hacer cada sistema
- Prioridades
- Criterios de aceptación

---

### VE-09: Sin Requisitos No Funcionales Documentados

**Hallazgo:** No hay documento RNF que establezca:
- Disponibilidad requerida
- Tiempos de respuesta
- Escalabilidad
- Seguridad

---

### VE-10: Sin Indicadores de Rendimiento (KPI)

**Hallazgo:** No se definen métricas de:
- Calidad de servicio
- Eficiencia operativa
- Satisfacción pasajero
- Seguridad

---

### VE-11: Sin Plan de Mantenimiento ITS

**Hallazgo:** No se define:
- Mantenimiento preventivo de equipamiento
- Renovación tecnológica
- Soporte técnico
- Repuestos críticos

---

### VE-12: Sin Manual de Operación CCO

**Hallazgo:** No existe documento que describa:
- Funciones del operador
- Procedimientos estándar
- Protocolos de emergencia
- Reportes diarios

---

## 5. DOCUMENTACIÓN FALTANTE (🟡 MAYORES)

| Código | Documento Faltante | Impacto | Prioridad |
|:---|:---|:---|:---|
| **DF-01** | Especificaciones Técnicas Particulares (ETP) ITS | No se puede licitar | 🔴 Alta |
| **DF-02** | Análisis de Riesgos Técnico | Riesgos no mitigados | 🟡 Media |
| **DF-03** | Estudio de Mercado de Equipamiento ITS | Sin precios de referencia | 🔴 Alta |
| **DF-04** | Diseño Detallado de Red | No se puede instalar red | 🟡 Media |
| **DF-05** | Plan de Ciberseguridad | Sistema vulnerable | 🔴 Alta |
| **DF-06** | Plan de Pruebas y Aceptación | No se puede validar | 🟡 Media |
| **DF-07** | Plan de Capacitación | Operadores no preparados | 🟡 Media |
| **DF-08** | Manual de Usuario Pasajero | Baja adopción | 🟢 Baja |
| **DF-09** | Manual de Operador CCO | Operación deficiente | 🟡 Media |
| **DF-10** | Plan de Continuidad del Negocio | Riesgo operacional | 🟡 Media |
| **DF-11** | Matriz de Trazabilidad Requisitos | No se puede auditar | 🟢 Baja |

---

## 6. INCONGRUENCIAS DE FLOTA (🔴 BLOQUEANTES)

### Detalle de la Incongruencia

```
┌─────────────────────────────────────────────────────────────┐
│           EVOLUCIÓN DOCUMENTADA DE LA FLOTA                 │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  2023 ──► 46 microbuses (estudios previos)                 │
│     │                                                       │
│     │  Justificación: Sistema viable con 46 unidades        │
│     │  Presupuesto máximo: $3.793.756.953 COP               │
│     │                                                       │
│     ▼                                                       │
│  2025 ──► 34 buses (MS-130-2025) — REDUCCIÓN               │
│     │                                                       │
│     │  Justificación: Competencia mototaxismo (45.000)      │
│     │  Vehículos particulares +44% desde 2020               │
│     │  Teletrabajo post-COVID                               │
│     │  Inseguridad: Sincelejo #2 en homicidios Colombia     │
│     │                                                       │
│     ▼                                                       │
│  2025 ──► 75 buses (RFI 2025) — EXPANSIÓN                   │
│                                                             │
│     Justificación: "cloud-first", APIs, crecimiento futuro  │
│                                                             │
│  ⚠️ PROBLEMA: ¿Para qué flota se diseña el ITS?            │
│                                                             │
│     34 buses = Inversión ITS ~$1.500M COP (estimado)        │
│     75 buses = Inversión ITS ~$3.200M COP (estimado)        │
│                                                             │
│  Diferencia: $1.700M COP (113% más)                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Impacto en Componente ITS

| Sistema | Impacto 34 buses | Impacto 75 buses | Diferencia |
|:---|:---|:---|:---|
| **GPS Trackers** | 34 unidades | 75 unidades | +41 |
| **Validadores NFC** | 68 unidades | 150 unidades | +82 |
| **Cámaras CCTV bus** | 204 unidades | 450 unidades | +246 |
| **Routers 4G** | 34 unidades | 75 unidades | +41 |
| **Ancho de banda** | 100 Mbps | 200 Mbps | +100 Mbps |
| **Servidores CCO** | 2 | 3 | +1 |
| **Operadores CCO** | 4 turnos | 6 turnos | +2 |

**Conclusión:** La decisión de flota es determinante para el componente ITS. No se puede avanzar sin definir.

---

## 7. PRESUPUESTO ITS — VACÍOS DETECTADOS

### Análisis de la Plantilla Excel

**Archivo:** `presupuesto_ITS_MetroSabanas.xlsx`

**Estructura encontrada:**
```
CATEGORIA: SISTEMA DE RASTREO Y CONTROL DE FLOTA (SRC)
├─ GPS Tracker vehicular              | 34 | Und | $0 | $0
├─ Antena GPS                       | 34 | Und | $0 | $0
├─ Tablet conductor                 | 34 | Und | $0 | $0
├─ Software SRC                     | 1  | Lic | $0 | $0

CATEGORIA: SISTEMA DE GESTIÓN DE COBRO (SGCF)
├─ Validador NFC                    | 68 | Und | $0 | $0
├─ Impresora térmica              | 34 | Und | $0 | $0
├─ Software SGCF                    | 1  | Lic | $0 | $0

CATEGORIA: SISTEMA DE INFORMACIÓN (SIU)
├─ Pantalla LED paradero           | 40 | Und | $0 | $0
├─ Software SIU                     | 1  | Lic | $0 | $0

CATEGORIA: SISTEMA DE SEGURIDAD (SST)
├─ Cámara CCTV interior            | 136| Und | $0 | $0
├─ Cámara CCTV exterior            | 68 | Und | $0 | $0
├─ Botón pánico                     | 68 | Und | $0 | $0
├─ NVR                              | 34 | Und | $0 | $0
├─ Software SST                     | 1  | Lic | $0 | $0

TOTAL GENERAL: $0
```

**Problemas identificados:**
1. ❌ Todos los valores unitarios en $0
2. ❌ Sin estudio de mercado de precios
3. ❌ Sin cantidades confirmadas (basado en estimado 40 paraderos)
4. ❌ Sin consideración de instalación, configuración, puesta en marcha
5. ❌ Sin licenciamiento anual de software
6. ❌ Sin mantenimiento preventivo
7. ❌ Sin formación/capacitación
8. ❌ Sin contingencia (10-15%)

**Impacto:** Este presupuesto no sirve para ningún propósito comercial, financiero, o de licitación.

---

## 8. RIESGOS POR HALLAZGOS

### Matriz de Riesgos

| ID | Riesgo | Probabilidad | Impacto | Nivel | Mitigación |
|:---|:---|:---|:---|:---|:---|
| **R-01** | ITS diseñado para flota errónea | Alta | Crítico | 🔴 | Definir flota definitiva antes de diseñar |
| **R-02** | Inversión ITS subestimada | Alta | Crítico | 🔴 | Estudio de mercado de precios |
| **R-03** | Buses sin preparación eléctrica para ITS | Media | Mayor | 🟡 | Adenda RFI buses |
| **R-04** | Sistema de pago no interoperable | Media | Mayor | 🟡 | Definir tarjeta única nacional |
| **R-05** | Ciberataque a sistema recaudo | Media | Crítico | 🔴 | Plan de ciberseguridad |
| **R-06** | CCO sin conectividad adecuada | Media | Mayor | 🟡 | Estudio de sitio CCO |
| **R-07** | Paraderos sin alimentación eléctrica | Alta | Mayor | 🟡 | Estudio eléctrico por paradero |
| **R-08** | Retraso por falta de documentación | Alta | Mayor | 🟡 | Contratar consultoría estructuración |
| **R-09** | Baja adopción pasajero por falta app | Media | Moderado | 🟡 | Incluir app en alcance ITS |
| **R-10** | Sistema no escalable a flota futura | Media | Mayor | 🟡 | Diseñar para 100 buses desde inicio |

---

## 9. RECOMENDACIONES DE REMEDIACIÓN

### Prioridad 1: Inmediata (0-2 semanas)

1. **Definir flota definitiva** — Reunión con METRO SABANAS para decidir: ¿34, 46, o 75?
2. **Diligenciar presupuesto ITS** — Estudio de mercado de precios unitarios
3. **Definir ubicación CCO** — Visita técnica a oficinas Metro Sabanas

### Prioridad 2: Corto plazo (2-6 semanas)

4. **Complementar RFI 2025** — Agregar ETP ITS detallado
5. **Adenda RFI Autobuses** — Incluir preparación eléctrica/mecánica para ITS
6. **Definir modelo de pago** — Efectivo + tarjeta, tarifa plana o diferencial
7. **Definir número de paraderos** — Estudio de demanda por ruta

### Prioridad 3: Medio plazo (6-12 semanas)

8. **Desarrollar ETP ITS completo** — Especificaciones técnicas particulares
9. **Diseñar arquitectura ITS** — 4 niveles, subsistemas, flujos
10. **Desarrollar plan de ciberseguridad** — ISO 27001, IEC 62443
11. **Desarrollar plan de implementación** — Cronograma, fases, entregables

### Prioridad 4: Continua

12. **Establecer gobernanza documental** — Repositorio único, versionamiento, aprobaciones
13. **Designar responsable ITS** — Rol definido dentro de METRO SABANAS
14. **Crear comité técnico** — Reuniones semanales de seguimiento

---

## 10. MATRIZ DE SEGUIMIENTO

| Hallazgo | Estado | Responsable | Fecha límite | Evidencia |
|:---|:---|:---|:---|:---|
| IC-01: Flota 34/46/75 | 🔴 Abierto | METRO SABANAS | Por definir | — |
| IC-02: Presupuesto $0 | 🔴 Abierto | METRO SABANAS / INNOVADATACO | Por definir | Excel vacío |
| IC-03: RFI sin ITS | 🔴 Abierto | METRO SABANAS | Por definir | RFI 2025 |
| IC-04: RFI buses sin ITS | 🔴 Abierto | METRO SABANAS | Por definir | RFI Autobuses 2022 |
| IC-05: Sin medio de pago | 🔴 Abierto | METRO SABANAS | Por definir | — |
| IC-06: Sin ubicación CCO | 🔴 Abierto | METRO SABANAS | Por definir | — |
| IC-07: Sin paraderos | 🔴 Abierto | METRO SABANAS | Por definir | — |
| IC-08: Sin ciberseguridad | 🔴 Abierto | METRO SABANAS | Por definir | — |
| VE-01 a VE-12 | 🟡 Abierto | INNOVADATACO | 4 semanas | — |
| DF-01 a DF-11 | 🟡 Abierto | INNOVADATACO | 8 semanas | — |

---

## CONCLUSIONES

La documentación del SETP Sincelejo presenta **vacíos críticos en el componente tecnológico ITS** que impiden:

1. **Licitación del componente** — Sin ETP no se puede solicitar cotizaciones
2. **Estimación de inversión** — Sin precios de mercado no hay modelo financiero
3. **Diseño arquitectónico** — Sin flota definida no se dimensiona
4. **Operación futura** — Sin concepto de operación no se sabe cómo funciona

**La estructuración técnica del componente ITS está en estado embrionario.** Se requiere trabajo significativo para alcanzar un nivel ejecutivo comparable al APP Chía-Girardot.

**INNOVADATACO puede cubrir estos vacíos en 1 mes de asesoría especializada.**

---

*Documento generado por INNOVADATACO — ZEUS Enterprise System*  
*Mayo 2026 — CONFIDENCIAL*
