# PLAN DE MIGRACIÓN EJECUTIVO SICOM
## PROYECTO 002-2026 | CI2 / IND TECH | Ministerio de Minas y Energía

**Fecha:** 2026-06-06  
**Elaborado por:** ZEUS — Innovadataco  
**Responsable Ejecutivo:** Jelkin Zair Carrillo Franco (Gerente de Empalme)  
**Destinatario:** CI2 / IND TECH — Luis Felipe Herrera (Gerente de Proyecto)  
**Cliente Final:** Ministerio de Minas y Energía (MME) — Elizabeth (Supervisora de Contrato)  
**Vigencia del Plan:** 4 semanas (1 mes) | 19 mayo — 19 junio 2026  
**Inicio Operación CI2:** 1 julio 2026  

---

## 1. DECLARACIÓN DE PROPÓSITO

### 1.1 ¿Por qué existe este plan?
El SICOM (Sistema de Información de Combustibles Minerales) es un sistema crítico de misión del Estado colombiano. Su operación no puede interrumpirse. La transición del operador actual (INTERNEXA) al nuevo operador (CI2 / IND TECH) requiere una **orquestación quirúrgica** donde cada día cuenta, cada recurso tiene una función específica y cada entregable valida que el sistema seguirá funcionando sin que los ciudadanos, las entidades reguladas ni el Ministerio noten el cambio.

### 1.2 Propósito Estratégico
Organizar, ejecutar y documentar la transferencia de conocimiento, acceso, documentación y capacidad operativa del SICOM desde INTERNEXA hacia CI2 / IND TECH, en un **periodo de 4 semanas**, con una **probabilidad de éxito aceptable** y un **plan de contingencia** para cada escenario de riesgo.

### 1.3 Propósito Operativo
Transformar al equipo de 6 especialistas asignados por CI2 en un **equipo de empalme funcional** que:
- Conozca la arquitectura del SICOM (sí o sí, en 4 semanas)
- Tenga acceso documentado a todos los sistemas
- Pueda ejecutar procedimientos operativos básicos sin supervisión de INTERNEXA
- Esté listo para asumir el control operativo el 1 de julio de 2026

---

## 2. ALCANCE DEL EMPALME (4 SEMANAS)

### 2.1 ¿Qué está INCLUIDO?

| # | Entregable | Alcance | Resultado Esperado |
|---|-----------|---------|-------------------|
| 1 | **Inventario Técnico** | Documentación completa de servidores, bases de datos, aplicaciones, integraciones, credenciales, licencias y configuraciones | Un documento maestro que CI2 pueda usar el día 1 sin INTERNEXA |
| 2 | **Acceso y Validación** | Credenciales de sólo consulta para arquitectura, credenciales operativas de respaldo, validación de accesos | Cada especialista CI2 puede entrar a su sistema asignado sin ayuda |
| 3 | **Transferencia de Conocimiento** | Shadowing con especialistas INTERNEXA, grabación de sesiones, manuales de procedimientos | CI2 puede ejecutar operaciones rutinarias sin consultar a INTERNEXA |
| 4 | **Documentación de Procedimientos** | Runbooks para operaciones diarias, semanales y mensuales | Manual operativo que CI2 pueda seguir paso a paso |
| 5 | **Pruebas de Recuperación** | Validación de backups, pruebas de restore, simulación de fallos | CI2 sabe cómo recuperar el sistema si algo falla |
| 6 | **Reporte de Riesgos** | Matriz de riesgos actualizada, vulnerabilidades identificadas, plan de mitigación | CI2 sabe qué puede fallar y cómo responder |
| 7 | **Interacción con MME** | Reuniones de seguimiento, entrega de insumos, atención de inquietudes | MME tiene confianza en el proceso y recibe reportes quincenales |

### 2.2 ¿Qué está EXCLUIDO?

| # | Exclusión | Justificación |
|---|----------|---------------|
| 1 | **Migración de infraestructura física** | CI2 heredará la infraestructura (si el contrato lo permite) o INTERNEXA la mantiene durante la vigencia del contrato CI2 (5 meses) |
| 2 | **Compra de licenciamiento nuevo** | El plan asume que INTERNEXA mantiene licencias durante el empalme. La compra de licencias propias es responsabilidad del MME post-empalme |
| 3 | **Desarrollo de nuevas funcionalidades** | Este plan es SOLO empalme operativo. Nuevos desarrollos son fuera de alcance |
| 4 | **Auditoría de seguridad completa** | Se hará identificación de vulnerabilidades, pero remediación completa es post-empalme |
| 5 | **Capacitación de usuarios finales MME** | El empalme es técnico-operativo. Capacitación de usuarios es responsabilidad del MME con CI2 post-corte |

### 2.3 Alcance Geográfico y Organizacional

- **Sede principal:** Bogotá D.C. (Ministerio de Minas y Energía + Data Center INTERNEXA)
- **Stakeholders:** 5 grupos (MME, CI2, INTERNEXA, Innovadataco, entidades reguladas)
- **Sistemas involucrados:** 8 subsistemas SICOM + 7 integraciones externas
- **Equipo de empalme:** 6 especialistas CI2 + 1 PM Innovadataco + 1 Gerente CI2

---

## 3. EQUIPO DE EMPALME — ROLES Y RESPONSABLES

### 3.1 Estructura del Equipo (7 personas)

```
┌─────────────────────────────────────────────────────────┐
│  GERENTE DE EMPALME / PM EJECUTIVO                       │
│  Jelkin Zair Carrillo Franco (Innovadataco)              │
│  → Responsable: Cronograma, calidad, riesgos, comunicación│
│  → Reporta a: Luis Felipe Herrera (CI2) + Elizabeth (MME)│
└──────────────────────┬────────────────────────────────────┘
                       │ Coordina
                       ▼
┌─────────────────────────────────────────────────────────┐
│  COORDINADOR TÉCNICO CI2                                 │
│  [Designar por CI2]                                     │
│  → Responsable: Técnico día a día, validación de entregables│
│  → Reporta a: Jelkin + Luis Felipe Herrera               │
└──────────────────────┬────────────────────────────────────┘
                       │ Dirige técnicamente
                       ▼
┌─────────┬─────────┬─────────┬─────────┬─────────┬─────────┐
│  ESPE.  │  ESPE.  │  ESPE.  │  ESPE.  │  ESPE.  │  ESPE.  │
│SOFTWARE │   BD    │   INFRA │  REDES  │  SEGUR. │  ARQUI. │
│  [S1]   │  [S2]   │  [S3]   │  [S4]   │  [S5]   │  [S6]   │
│  CI2    │  CI2    │  CI2    │  CI2    │  CI2    │  CI2    │
└─────────┴─────────┴─────────┴─────────┴─────────┴─────────┘
```

### 3.2 Detalle de Responsables

#### Jelkin Zair Carrillo Franco — Gerente de Empalme / PM Ejecutivo (Innovadataco)
- **Responsabilidad #1:** Mantener el cronograma de 4 semanas, ajustar cada día si hay desviaciones
- **Responsabilidad #2:** Ser el único punto de contacto entre CI2, INTERNEXA y MME (evita confusión)
- **Responsabilidad #3:** Validar calidad de cada entregable antes de que CI2 lo acepte
- **Responsabilidad #4:** Documentar TODO (actas, decisiones, riesgos, incidencias)
- **Responsabilidad #5:** Escalar problemas a Luis Felipe (CI2) y a Elizabeth (MME) cuando sea necesario
- **Responsabilidad #6:** Preparar reportes quincenales para el MME (formato establecido en contrato)
- **Tiempo estimado:** 100% dedicado durante las 4 semanas (40h/semana mínimo)

#### Coordinador Técnico CI2 — [Designar por CI2]
- **Responsabilidad #1:** Validar técnicamente cada entregable de INTERNEXA
- **Responsabilidad #2:** Asegurar que los 6 especialistas CI2 reciban la información que necesitan
- **Responsabilidad #3:** Resolver dudas técnicas que los especialistas no puedan resolver solos
- **Responsabilidad #4:** Reportar impedimentos técnicos a Jelkin diariamente
- **Tiempo estimado:** 100% dedicado (40h/semana mínimo)

#### Especialista de Software [S1] — CI2
- **Responsabilidad #1:** Conocer el stack de aplicaciones SICOM (Java, BPM, Web, APPs)
- **Responsabilidad #2:** Documentar arquitectura de aplicaciones, dependencias, APIs
- **Responsabilidad #3:** Shadowing con desarrollador INTERNEXA para operaciones de despliegue
- **Responsabilidad #4:** Validar que puede hacer deploy básico sin ayuda
- **Entregables:** Diagrama de aplicaciones, runbook de deploy, lista de dependencias JAR/módulos
- **Tiempo estimado:** 100% dedicado (40h/semana)

#### Especialista de Base de Datos [S2] — CI2
- **Responsabilidad #1:** Conocer esquema Oracle 19c (tablas, índices, procedimientos, jobs)
- **Responsabilidad #2:** Validar backups diarios y probar restore en ambiente de pruebas
- **Responsabilidad #3:** Documentar consultas críticas que el sistema ejecuta automáticamente
- **Responsabilidad #4:** Shadowing con DBA INTERNEXA para operaciones de mantenimiento
- **Entregables:** Diagrama ER, runbook de backup/restore, lista de jobs críticos, queries de monitoreo
- **Tiempo estimado:** 100% dedicado (40h/semana)

#### Especialista de Infraestructura [S3] — CI2
- **Responsabilidad #1:** Conocer el parque de servidores (27 VMs, VMware, hardware, storage)
- **Responsabilidad #2:** Documentar configuración de cada servidor (OS, recursos, servicios)
- **Responsabilidad #3:** Shadowing con administrador de infraestructura INTERNEXA
- **Responsabilidad #4:** Validar acceso a consolas de administración (vCenter, iLO, etc.)
- **Entregables:** Inventario de servidores, runbook de monitoreo, mapa de dependencias físicas
- **Tiempo estimado:** 100% dedicado (40h/semana)

#### Especialista de Redes [S4] — CI2
- **Responsabilidad #1:** Conocer diagrama de red (VLANs, firewalls, switches, balanceadores)
- **Responsabilidad #2:** Documentar reglas de firewall, NATs, VPNs, segmentación de red
- **Responsabilidad #3:** Shadowing con ingeniero de redes INTERNEXA
- **Responsabilidad #4:** Validar acceso a consolas de Fortinet y switches
- **Entregables:** Diagrama de red, lista de reglas de firewall, runbook de troubleshooting de red
- **Tiempo estimado:** 100% dedicado (40h/semana)

#### Especialista de Seguridad [S5] — CI2
- **Responsabilidad #1:** Conocer políticas de seguridad, certificados SSL, WAF, SIEM
- **Responsabilidad #2:** Revisar matriz de vulnerabilidades y validar estado actual
- **Responsabilidad #3:** Documentar procedimientos de gestión de incidentes de seguridad
- **Responsabilidad #4:** Shadowing con especialista de seguridad INTERNEXA
- **Entregables:** Runbook de seguridad, estado de vulnerabilidades, procedimiento de renovación de certificados
- **Tiempo estimado:** 100% dedicado (40h/semana)

#### Arquitecto de Software [S6] — CI2
- **Responsabilidad #1:** Comprender visión global de la arquitectura SICOM (8 subsistemas)
- **Responsabilidad #2:** Documentar flujos de datos entre subsistemas e integraciones externas
- **Responsabilidad #3:** Identificar puntos de fragilidad y dependencias críticas
- **Responsabilidad #4:** Validar que el diseño arquitectónico documentado coincide con la realidad
- **Entregables:** Diagrama de arquitectura global, flujos de datos, puntos de fragilidad, recomendaciones de mejora
- **Tiempo estimado:** 100% dedicado (40h/semana)

---

## 4. CRONOGRAMA DE 4 SEMANAS — FASES DETALLADAS

### Semana 1: GOBIERNO + INVENTARIO (Día 1-7)
**Objetivo:** Instalar gobierno, obtener acceso y documentar todo lo que existe.

| Día | Actividad | Responsable | Entregable | Tiempo Est. |
|-----|-----------|-------------|------------|-------------|
| L1 | Acta de constitución del equipo de empalme | Jelkin | Acta firmada | 4h |
| L1 | Reunión de kickoff con CI2 (6 especialistas + coordinador) | Jelkin | Acta de kickoff | 3h |
| L1 | Solicitud formal a INTERNEXA para acceso de sólo consulta | Jelkin + CI2 | Correo formal | 2h |
| M2 | Reunión con MME (Elizabeth) — presentación de plan y solicitud de insumos | Jelkin | Acta con MME | 3h |
| M2 | INTERNEXA entrega acceso de lectura a arquitectura (si autoriza) | INTERNEXA | Credenciales | — |
| M2 | Especialistas CI2 reciben orientación de seguridad y NDA | S5 + Jelkin | NDA firmado | 2h |
| X3 | **Inventario Técnico — Día 1:** Especialistas exploran su área con acceso de lectura | S1-S6 | Notas preliminares | 8h |
| X3 | Reunión diaria de sincronización (15 min) | Jelkin | Acta diaria | 0.5h |
| J4 | **Inventario Técnico — Día 2:** Documentación preliminar de cada especialista | S1-S6 | Borradores | 8h |
| J4 | Validación de accesos — ¿qué sistemas no se pueden ver? | S1-S6 | Lista de bloqueos | 2h |
| V5 | **Inventario Técnico — Día 3:** Consolidación de información | Jelkin + Coordinador | Documento borrador | 6h |
| V5 | Reunión con INTERNEXA — solicitud de información faltante | Jelkin | Lista de gaps | 2h |
| S6 | Trabajo independiente — cada especialista profundiza en su área | S1-S6 | Notas | 4h |
| S6 | Jelkin prepara reporte semanal para Luis Felipe (CI2) | Jelkin | Reporte semanal #1 | 4h |
| D7 | **DOMINGO — DESCANSO** | — | — | — |

**Hitos Semana 1:**
- ✅ Equipo de empalme instalado y operando
- ✅ Acceso de lectura a arquitectura validado (o bloqueos documentados)
- ✅ Primer borrador de inventario técnico (cada especialista)
- ✅ Primera reunión con MME realizada
- ✅ Reporte semanal #1 entregado a CI2

---

### Semana 2: DOCUMENTACIÓN + SHADOWING (Día 8-14)
**Objetivo:** Obtener la documentación completa y comenzar shadowing con INTERNEXA.

| Día | Actividad | Responsable | Entregable | Tiempo Est. |
|-----|-----------|-------------|------------|-------------|
| L8 | Reunión con INTERNEXA — entrega de documentación técnica | Jelkin + Coordinador | Acta + lista documentos | 3h |
| L8 | Especialistas validan documentación recibida vs. lo que vieron en campo | S1-S6 | Validación de docs | 6h |
| M9 | **Shadowing Día 1:** Cada especialista acompaña a su contraparte INTERNEXA | S1-S6 | Notas de shadowing | 8h |
| X10 | **Shadowing Día 2:** Continuación, profundización en operaciones críticas | S1-S6 | Notas de shadowing | 8h |
| X10 | Jelkin revisa avance de documentación con cada especialista | Jelkin | Feedback individual | 3h |
| J11 | **Shadowing Día 3:** Procedimientos de respaldo, monitoreo, troubleshooting | S1-S6 | Notas de shadowing | 8h |
| J11 | Reunión con MME (semanal) — reporte de avance y solicitud de decisiones | Jelkin | Acta con MME | 2h |
| V12 | **Shadowing Día 4:** Operaciones de alto impacto (deploys, cambios en BD, mantenimiento) | S1-S6 | Notas de shadowing | 8h |
| V12 | Validación de backups — S2 prueba restore en ambiente de pruebas | S2 | Resultado de restore | 4h |
| S13 | Documentación de Runbooks — cada especialista escribe procedimientos | S1-S6 | Runbooks v1 | 6h |
| S13 | Jelkin prepara reporte semanal #2 | Jelkin | Reporte semanal #2 | 4h |
| D14 | **DOMINGO — DESCANSO** | — | — | — |

**Hitos Semana 2:**
- ✅ Documentación técnica de INTERNEXA recibida y validada
- ✅ Shadowing de 4 días completado por cada especialista
- ✅ Runbooks v1 escritos para cada área
- ✅ Prueba de restore de backup validada (o riesgo documentado)
- ✅ Reporte semanal #2 entregado

---

### Semana 3: VALIDACIÓN + PRUEBAS (Día 15-21)
**Objetivo:** Validar que CI2 puede operar sin INTERNEXA y probar recuperación ante fallos.

| Día | Actividad | Responsable | Entregable | Tiempo Est. |
|-----|-----------|-------------|------------|-------------|
| L15 | **Prueba de Fuego #1:** S1 intenta deploy básico en ambiente de pruebas sin ayuda | S1 | Resultado + log | 4h |
| L15 | **Prueba de Fuego #2:** S2 ejecuta backup y verifica integridad sin ayuda | S2 | Resultado + log | 4h |
| L15 | Reunión de revisión — Jelkin evalúa gaps con cada especialista | Jelkin + S1-S6 | Lista de gaps | 3h |
| M16 | **Prueba de Fuego #3:** S3 reinicia servicio en VM de prueba sin ayuda | S3 | Resultado + log | 4h |
| M16 | **Prueba de Fuego #4:** S4 identifica y resuelve problema de red simulado | S4 | Resultado + log | 4h |
| X17 | **Prueba de Fuego #5:** S5 ejecuta procedimiento de revisión de vulnerabilidades | S5 | Resultado + log | 4h |
| X17 | **Prueba de Fuego #6:** S6 traza flujo de datos completo de una transacción | S6 | Diagrama + log | 4h |
| J18 | Simulacro de DRP (Disaster Recovery Plan) — CI2 intenta recuperar sistema con documentación solo | Todos | Resultado de simulacro | 6h |
| J18 | Reunión con MME — presentación de avances y solicitud de decisiones pendientes | Jelkin | Acta con MME | 2h |
| V19 | Corrección de gaps — cada especialista refuerza áreas donde falló | S1-S6 | Runbooks v2 | 6h |
| S20 | Jelkin prepara reporte semanal #3 + informe quincenal para MME | Jelkin | Reporte quincenal | 6h |
| D21 | **DOMINGO — DESCANSO** | — | — | — |

**Hitos Semana 3:**
- ✅ 6 pruebas de fuego ejecutadas (una por especialista)
- ✅ Simulacro de DRP ejecutado (con resultado documentado)
- ✅ Runbooks v2 (corregidos tras pruebas)
- ✅ Informe quincenal #1 entregado a MME
- ✅ Gaps críticos identificados y plan de cierre definido

---

### Semana 4: CIERRE + EMPALME FINAL (Día 22-28)
**Objetivo:** Cerrar documentación, validar últimos detalles y preparar corte de julio.

| Día | Actividad | Responsable | Entregable | Tiempo Est. |
|-----|-----------|-------------|------------|-------------|
| L22 | Reunión de cierre con INTERNEXA — validación final de entregables | Jelkin + Coordinador | Acta de cierre | 3h |
| L22 | INTERNEXA entrega credenciales operativas finales (si aplica) | INTERNEXA | Lista de credenciales | — |
| M23 | **Validación Final:** Cada especialista prueba acceso operativo completo | S1-S6 | Checklist de validación | 6h |
| X24 | Preparación de corte — Jelkin define plan de corte del 1 de julio | Jelkin | Plan de corte | 6h |
| X24 | Reunión con CI2 — presentación de estado de empalme a Luis Felipe | Jelkin | Presentación | 2h |
| J25 | Reunión con MME — informe final de empalme a Elizabeth | Jelkin | Informe final | 3h |
| J25 | MME asigna permisos de consulta de arquitectura a CI2 (si no lo hizo) | Elizabeth (MME) | Confirmación | — |
| V26 | Corrección de últimos detalles — Jelkin coordina cierre de gaps menores | Jelkin + S1-S6 | Lista de cierre | 4h |
| S27 | Preparación de entregables finales — consolidación de documentación | Jelkin | Carpeta de entregables | 6h |
| D28 | **FIN DE EMPALME — CIERRE OFICIAL** | Todos | Acta de cierre | 2h |

**Hitos Semana 4:**
- ✅ Acta de cierre con INTERNEXA firmada
- ✅ Validación final de accesos operativos
- ✅ Plan de corte del 1 de julio documentado
- ✅ Informe final de empalme entregado a MME
- ✅ Carpeta de entregables completa (inventario, runbooks, diagramas, credenciales)
- ✅ Acta de cierre oficial del empalme

---

## 5. INTERACCIÓN CON EL CLIENTE MME

### 5.1 ¿Qué necesitamos del MME?

| # | Insumo | Quién lo Solicita | Para cuándo | Importancia |
|---|--------|------------------|-------------|-------------|
| 1 | **Acceso a salas de reuniones** en el MME para reuniones de empalme | Jelkin | Día 1 | 🔴 Crítica |
| 2 | **Contacto directo de Elizabeth** (celular, correo) para escalaciones urgentes | Jelkin | Día 1 | 🔴 Crítica |
| 3 | **Permisos de consulta de arquitectura** para CI2 (sólo lectura) | Jelkin + CI2 | Día 2 | 🔴 Crítica |
| 4 | **Insumos contractuales** (contrato GGC-2034-2025, actas de modificaciones) | Jelkin | Día 3 | 🟡 Alta |
| 5 | **Historial de reportes quincenales** que INTERNEXA entregó al MME | Jelkin | Día 3 | 🟡 Alta |
| 6 | **Contactos de entidades reguladas** (EDS, DI, CI, Comercializadores) | Jelkin | Semana 2 | 🟡 Alta |
| 7 | **Presupuesto para licenciamiento** (confirmación de que MME sabe que debe comprar) | Luis Felipe (CI2) | Semana 2 | 🟡 Alta |
| 8 | **Decisión sobre infraestructura** (¿CI2 hereda VMs? ¿MME compra nuevas?) | Luis Felipe (CI2) | Semana 3 | 🟡 Alta |
| 9 | **Atención de inquietudes** — responder preguntas del MME sobre el empalme | Jelkin | Continuo | 🟢 Media |
| 10 | **Aprobación de informes quincenales** — Elizabeth valida y aprueba | Elizabeth (MME) | Semana 2 y 4 | 🟢 Media |

### 5.2 Reuniones con MME — Calendario Propuesto

| Reunión | Día | Duración | Participantes | Propósito |
|---------|-----|----------|---------------|-----------|
| **Kickoff con MME** | Día 2 (M2) | 1h | Elizabeth + Jelkin + Luis Felipe | Presentar plan, solicitar insumos, establecer comunicación |
| **Semanal #1** | Día 7 (V5) | 30min | Elizabeth + Jelkin | Reporte de avance semana 1, resolver bloqueos |
| **Quincenal #1** | Día 14 (S13) | 1h | Elizabeth + Jelkin + Luis Felipe | Informe formal de 2 semanas, decisiones pendientes |
| **Semanal #2** | Día 16 (M16) | 30min | Elizabeth + Jelkin | Avance, validar accesos, atender inquietudes |
| **Quincenal #2 / Final** | Día 25 (J25) | 1.5h | Elizabeth + Jelkin + Luis Felipe | Informe final, cierre de empalme, próximos pasos |

### 5.3 ¿Qué reportes entregamos al MME?

| Reporte | Frecuencia | Contenido | Responsable |
|---------|-----------|-----------|-------------|
| **Acta de Reunión** | Cada reunión | Decisiones, acciones, responsables | Jelkin |
| **Reporte Semanal** | Cada viernes | Avance %, hitos, riesgos, próxima semana | Jelkin |
| **Informe Quincenal** | Día 14 y 25 | Resumen ejecutivo, métricas, riesgos, decisiones | Jelkin |
| **Informe de Riesgos** | Semana 2 y 4 | Matriz actualizada, mitigaciones, alertas | Jelkin + S5 |
| **Informe Final** | Día 25 | Estado del empalme, entregables, recomendaciones | Jelkin |

---

## 6. GESTIÓN DE RIESGOS — PLAN DE CONTINGENCIA

### 6.1 Riesgos Críticos y Respuesta

| Riesgo | Probabilidad | Impacto | Mitigación | Plan B |
|--------|-------------|---------|------------|--------|
| **INTERNEXA no entrega acceso de lectura** | Alta | Crítico | Solicitar formalmente por escrito, escalar a MME contractualmente | Subcontratar a un ex-empleado de INTERNEXA como consultor |
| **INTERNEXA no entrega documentación** | Alta | Alto | Presionar contractualmente, documentar nosotros mismos durante shadowing | Usar documentación de versiones anteriores + ingeniería inversa |
| **Especialista CI2 no entiende el sistema** | Media | Alto | Asignar más horas de shadowing, traer consultor externo | Asignar 2 especialistas al mismo área |
| **Backup no es restaurable** | Media | Crítico | Probar restore en día 5 (no esperar al final) | Documentar procedimiento de reconstrucción desde cero |
| **Licenciamiento Oracle vence** | Media | Crítico | Alertar a MME desde día 1, incluir en informes quincenales | Plan de contingencia: migración a PostgreSQL (evaluar) |
| **Personal clave INTERNEXA renuncia** | Media | Alto | Entrevistar y documentar conocimiento de personas clave ASAP | Grabar sesiones de shadowing como respaldo |
| **MME no responde solicitudes** | Media | Alto | Escalar a Luis Felipe (CI2) para que presione comercialmente | Documentar intentos y decisiones asumidas |
| **Prueba de DRP falla** | Media | Alto | Corregir procedimientos, documentar gaps, plan de remedio | Plan de contingencia: cloud temporal con réplica mínima |

### 6.2 Watchlist — Indicadores de Alerta Temprana

| Semáforo | Indicador | Día de revisión | Acción si se prende |
|----------|-----------|-----------------|-------------------|
| 🔴 | INTERNEXA niega acceso después de solicitud formal | Día 3 | Escalar a MME contractualmente |
| 🔴 | Especialista reporta "no entiendo nada" | Día 5 | Asignar consultor externo urgente |
| 🔴 | Backup falla prueba de restore | Día 5 | Alertar a MME, plan de reconstrucción |
| 🟡 | Documentación llega incompleta | Día 8 | Solicitar nuevamente, documentar gaps |
| 🟡 | Shadowing cancelado por INTERNEXA | Día 10 | Negociar alternativas, grabar sesiones |
| 🟡 | Especialista reporta riesgo de seguridad nuevo | Día 12 | Incluir en informe quincenal, alertar a MME |
| 🟢 | Shadowing avanza según cronograma | Día 7, 14 | Continuar según plan |
| 🟢 | Pruebas de fuego exitosas | Día 15, 18 | Validar y documentar |
| 🟢 | MME aprueba informes sin objeciones | Día 14, 25 | Continuar según plan |

---

## 7. ESTIMACIÓN DE TIEMPO Y RECURSOS

### 7.1 Resumen de Tiempo por Rol (4 semanas)

| Rol | Semana 1 | Semana 2 | Semana 3 | Semana 4 | Total |
|-----|----------|----------|----------|----------|-------|
| Jelkin (PM) | 40h | 40h | 40h | 40h | 160h |
| Coordinador Técnico CI2 | 40h | 40h | 40h | 40h | 160h |
| Especialista Software (S1) | 40h | 40h | 40h | 30h | 150h |
| Especialista BD (S2) | 40h | 40h | 40h | 30h | 150h |
| Especialista Infra (S3) | 40h | 40h | 40h | 30h | 150h |
| Especialista Redes (S4) | 40h | 40h | 40h | 30h | 150h |
| Especialista Seguridad (S5) | 40h | 40h | 40h | 30h | 150h |
| Arquitecto Software (S6) | 40h | 40h | 40h | 30h | 150h |
| **TOTAL EQUIPO** | **320h** | **320h** | **320h** | **270h** | **1,230h** |

### 7.2 Recursos Adicionales Necesarios

| Recurso | Cantidad | Para qué | Costo Est. |
|---------|----------|----------|------------|
| Consultor externo (ex-INTERNEXA o experto Oracle+Java+BPM) | 1 persona × 2 semanas | Refuerzo si especialista CI2 no alcanza | $3,000-5,000 USD |
| Ambiente de pruebas (cloud temporal) | 1 instancia | Pruebas de restore, DRP, deploys | $500-1,000 USD |
| Grabador de pantalla + almacenamiento | Licencia | Grabar sesiones de shadowing | $200-500 USD |
| **TOTAL RECURSOS ADICIONALES** | | | **$3,700-6,500 USD** |

### 7.3 Presupuesto de Licenciamiento (Advertencia al MME)

| Software | Licencia Anual Est. (USD) | Quién debe comprar | Urgencia |
|----------|--------------------------|-------------------|----------|
| Oracle Database 19c Enterprise | $150,000-300,000 | MME | 🔴 Antes de julio 2026 |
| Oracle BI 12c | $50,000-100,000 | MME | 🔴 Antes de julio 2026 |
| VMware vSphere Enterprise | $30,000-60,000 | MME | 🟡 Durante contrato CI2 |
| Fortinet (FW + WAF + SIEM) | $20,000-40,000 | MME | 🟡 Durante contrato CI2 |
| Bizagi BPM Suite | $25,000-50,000 | MME | 🟡 Durante contrato CI2 |
| Veeam Backup | $10,000-20,000 | MME | 🟡 Durante contrato CI2 |
| **TOTAL ESTIMADO** | **$285,000-570,000/año** | | |

---

## 8. FORMATO DE ENTREGABLES

### 8.1 Lista de Entregables del Empalme

| ID | Entregable | Formato | Responsable | Fecha |
|----|-----------|---------|-------------|-------|
| E1 | Inventario Técnico SICOM | Excel + PDF | Jelkin + S1-S6 | Día 7 (borrador), Día 25 (final) |
| E2 | Diagrama de Arquitectura Global | Visio/Draw.io | S6 | Día 14 (borrador), Día 25 (final) |
| E3 | Runbook de Operaciones por Área | Word/PDF | S1-S6 | Día 14 (v1), Día 25 (v2) |
| E4 | Matriz de Riesgos y Vulnerabilidades | Excel + PDF | S5 + Jelkin | Día 10 (borrador), Día 25 (final) |
| E5 | Plan de Corte (1 julio 2026) | Word/PDF + cronograma | Jelkin | Día 20 (borrador), Día 25 (final) |
| E6 | Reportes Semanales (4) | Word/PDF | Jelkin | Viernes de cada semana |
| E7 | Informes Quincenales (2) | Word/PDF | Jelkin | Día 14, Día 25 |
| E8 | Informe Final de Empalme | Word/PDF | Jelkin | Día 25 |
| E9 | Actas de Reuniones | Word/PDF | Jelkin | Cada reunión |
| E10 | Grabaciones de Shadowing | MP4/Video | S1-S6 | Continuo (almacenar en Drive) |
| E11 | Credenciales y Accesos | Excel (cifrado) | Jelkin + Coordinador | Día 25 (entregado a CI2) |
| E12 | Lista de Contactos Clave | Excel | Jelkin | Día 7 |
| E13 | Recomendaciones de Mejora | Word/PDF | S6 | Día 25 |

### 8.2 Estructura de Documentos en GitHub

```
PROYECTO-002-2026-SICOM/
├── 06-EMPALME/
│   ├── 01-PLAN-EMPALME.md           ← Este documento
│   ├── 02-INVENTARIO-TECNICO/
│   ├── 03-RUNBOOKS/
│   ├── 04-RIESGOS/
│   ├── 05-REPORTES-SEMANALES/
│   ├── 06-INFORMES-QUINCENALES/
│   ├── 07-CORTE/
│   └── 08-FINAL/
```

---

## 9. COMUNICACIÓN Y GOBIERNO

### 9.1 Ritmo de Comunicación

| Ritmo | Actividad | Participantes | Día/Hora |
|-------|-----------|---------------|----------|
| **Diario** | Standup (15 min) | Jelkin + S1-S6 + Coordinador | 8:30 AM cada día |
| **Semanal** | Revisión de avance | Jelkin + S1-S6 + Coordinador + Luis Felipe (CI2) | Viernes 4:00 PM |
| **Quincenal** | Reunión con MME | Jelkin + Elizabeth + Luis Felipe | Día 14 y 25, 10:00 AM |
| **Por demanda** | Escalaciones | Jelkin + Luis Felipe + Elizabeth (según severidad) | Cuando se prenda alerta |

### 9.2 Canales de Comunicación

| Canal | Uso | Quién administra |
|-------|-----|-----------------|
| **Grupo WhatsApp** | Alertas urgentes, coordinación rápida | Jelkin |
| **Correo formal** | Actas, reportes, solicitudes a MME | Jelkin |
| **Google Drive** | Documentos, grabaciones, entregables | Jelkin |
| **GitHub** | Documentos técnicos, versionamiento | Jelkin + S6 |
| **Jira/Monday** | Seguimiento de tareas (si CI2 lo usa) | Coordinador CI2 |

### 9.3 Reglas de Gobierno

1. **Cada día tiene una actividad principal** — no se inventa, se sigue el cronograma
2. **Cada semana tiene un hito** — si no se cumple, se escala en 24h
3. **Cada riesgo tiene un dueño** — no hay riesgos "de todos"
4. **Cada documento tiene una versión** — v0.1, v0.2, v1.0 (no hay "el documento final")
5. **Cada reunión tiene un acta** — sin acta, la reunión no existió
6. **Cada decisión se documenta** — quién decidió, qué, cuándo, por qué

---

## 10. VEREDICTO HONESTO ZEUS

### 10.1 ¿Es viable un empalme en 4 semanas?

| Condición | Viabilidad | Justificación |
|-----------|------------|---------------|
| **Con cooperación TOTAL de INTERNEXA** | 🟡 Difícil pero posible (~60%) | El tiempo es justo, pero con acceso y shadowing se puede lograr |
| **Con resistencia pasiva de INTERNEXA** | 🔴 Muy difícil (~35%) | El tiempo no alcanza para documentar + validar sin acceso completo |
| **Sin acceso a arquitectura** | 🔴 Imposible (~15%) | No se puede empalmar lo que no se puede ver |
| **Con consultor externo adicional** | 🟡 Difícil pero posible (~70%) | El refuerzo compensa la curva de aprendizaje |

### 10.2 Recomendaciones para Maximizar Éxito

1. **Día 1-2:** Obtener acceso de lectura a TODA la arquitectura. Si INTERNEXA se resiste, escalar a MME inmediatamente. Sin esto, el plan no avanza.
2. **Día 3-5:** Validar que los backups funcionan. Si no, todo el plan cambia.
3. **Día 7:** Evaluar honestamente si el equipo CI2 está aprendiendo o no. Si no, traer refuerzo.
4. **Día 14:** Si a mitad del empalme hemos logrado <50% de lo planeado, negociar extensión con MME.
5. **Semana 3:** El simulacro de DRP es la prueba de fuego. Si falla, el corte del 1 de julio es riesgoso.
6. **Semana 4:** No completar el 100% no es fracaso. Entregar el 80% documentado y validado es mejor que el 100% incompleto.

### 10.3 La Frase que Resume Todo

> **"Empalmar el SICOM en 4 semanas es como hacer una operación de trasplante de corazón en 4 horas. Se puede hacer, pero requiere un equipo quirúrgico perfecto, cero distracciones y la cooperación del paciente. Si cualquiera de estos falla, el resultado no es el óptimo."**

---

## 11. ANEXOS

### Anexo A: Checklist de Inicio de Empalme (Día 1)

- [ ] Acta de constitución firmada
- [ ] Equipo CI2 completo presente (6 especialistas + coordinador)
- [ ] NDA firmado por todos
- [ ] Solicitud formal a INTERNEXA enviada (acceso de lectura)
- [ ] Reunión con MME realizada
- [ ] Grupo de comunicación creado (WhatsApp + Drive + GitHub)
- [ ] Cronograma impreso y visible para todos
- [ ] Plan de riesgos inicial presentado
- [ ] Recursos adicionales presupuestados (si aplica)

### Anexo B: Plantilla de Reporte Semanal

```
REPORTE SEMANAL DE EMPALME SICOM — Semana [X]
Fecha: [DD/MM/YYYY]
Elaborado por: Jelkin Zair Carrillo Franco (Innovadataco)

1. RESUMEN EJECUTIVO (3-5 líneas)
   → Estado general: [Verde/Amarillo/Rojo]
   → Avance vs. plan: [X%]

2. HITOS DE LA SEMANA
   → [Hito 1]: [Estado] — [Observaciones]
   → [Hito 2]: [Estado] — [Observaciones]

3. RIESGOS ACTIVOS
   → [Riesgo 1]: [Probabilidad] — [Acción en curso]

4. DECISIONES TOMADAS
   → [Decisión 1]: [Quién decidió] — [Fecha]

5. PRÓXIMA SEMANA
   → [Actividad 1]: [Responsable] — [Fecha]

6. ESCALACIONES NECESARIAS
   → [Si aplica, quién debe decidir qué]
```

### Anexo C: Plantilla de Acta de Reunión

```
ACTA DE REUNIÓN — EMPALME SICOM
Fecha: [DD/MM/YYYY] | Hora inicio: [HH:MM] | Hora fin: [HH:MM]
Lugar: [Presencial/Virtual]

ASISTENTES:
- [Nombre] — [Rol] — [Entidad]

OBJETIVO:
[1-2 líneas]

TEMAS TRATADOS:
1. [Tema 1]
   → [Resumen de discusión]
   → [Decisión, si aplica]

2. [Tema 2]
   → [Resumen de discusión]
   → [Decisión, si aplica]

ACCIONES PENDIENTES:
| # | Acción | Responsable | Fecha límite | Estado |
|---|--------|-------------|--------------|--------|
| 1 | [Describir] | [Nombre] | [Fecha] | [Pendiente/En curso/Cerrada] |

PRÓXIMA REUNIÓN:
Fecha: [DD/MM/YYYY] | Hora: [HH:MM]

Elaboró: Jelkin Zair Carrillo Franco
Fecha de acta: [DD/MM/YYYY]
```

---

**Documento elaborado por ZEUS — Innovadataco**  
**Fecha:** 2026-06-06  
**Versión:** 1.0  
**Clasificación:** Interno — CI2 / IND TECH / MME  
**Próxima revisión:** Día 7 de empalme (si aplica)

---

> **"ZEUS online. La empresa está operando."** ⚡
