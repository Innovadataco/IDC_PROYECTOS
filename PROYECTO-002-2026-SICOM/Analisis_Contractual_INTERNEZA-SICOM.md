# 📋 ANÁLISIS CONTRACTUAL INTERNEXA-SICOM

## Contrato de Prestación de Servicios GGC No. 2034 de 2025

**Entidad Contratante:** Ministerio de Minas y Energía (MME)  
**Contratista:** INTERNEXA S.A.S.  
**Objeto:** Administración, operación, soporte, mantenimiento y desarrollo del Sistema de Información de Combustibles (SICOM)  
**Análisis realizado por:** ZEUS AGENTE IA — INNOVADATACO  
**Fecha de análisis:** Mayo 2026  
**Fuentes:** 48 documentos técnicos SICOM, informes de infraestructura, actas de comité, matrices de vulnerabilidad

---

## 1. CONTRATOS IDENTIFICADOS EN LA DOCUMENTACIÓN

| Contrato | Número | Estado | Periodo Documentado | Evidencia |
|----------|--------|--------|---------------------|-----------|
| **Contrato Inicial** | GGC 1685-2025 | **FINALIZADO** | Hasta noviembre-diciembre 2025 | Presentación "Seguimiento Riesgos Proyecto SICOM — Final GGC 1685-2025" (11 dic 2025) |
| **Contrato Actual** | **GGC 2034-2025** | **EN EJECUCIÓN** | Vigente desde al menos septiembre 2025 hasta febrero 2026 | Informe Técnico C608201A, Actas de Riesgos, Cronograma Vigencia 3 |
| **Posible Sucesor** | Sin identificar | No documentado | — | No hay rastro en los 48 documentos analizados |

### Hallazgo Clave
> **NO existe en los documentos técnicos analizados** el contrato propiamente dicho (PDF), ni sus anexos contractuales, ni la cláusula de término. Los 48 archivos son documentación operativa, no contractual.

---

## 2. VIGENCIA Y FECHA DE CIERRE — ESTADO: DESCONOCIDO

### 2.1 Lo que NO se encontró
- ❌ Fecha exacta de inicio del contrato GGC 2034-2025
- ❌ Fecha exacta de terminación o cierre del contrato
- ❌ Plazo contractual en meses o años
- ❌ Cláusula de prórroga o renovación
- ❌ Cláusula de terminación anticipada
- ❌ Penalidades por incumplimiento

### 2.2 Indirectas encontradas

#### A) Cronograma "Vigencia 3_2025"
El documento de ejecución del proyecto muestra:
- **Inicio de tareas:** 01/09/2025
- **Fin planificado de tareas:** 28/11/2025
- **Duración:** 232 días de ejecución técnica

> ⚠️ **IMPORTANTE:** Este cronograma refleja la **ejecución de actividades del proyecto SICOM**, NO la vigencia del contrato de prestación de servicios con INTERNEXA. El nombre "Vigencia 3_2025" sugiere que el contrato podría estar estructurado por **vigencias trimestrales o semestrales**, siendo esta la tercera vigencia del año 2025.

#### B) Licenciamiento Oracle
El Informe Técnico C608201A documenta:
> *"Se realiza la renovación de Oracle 19 adquirido para la infraestructura de SICOM Líquidos, SICOM GNCV y SICOM BPM (NUEVO SICOM). Con un licenciamiento vigente a la fecha."*

Esto indica que INTERNEXA **renueva licenciamientos** durante la vigencia del contrato, lo que implica una operación continua.

---

## 3. OBLIGACIONES CONTRACTUALES IDENTIFICADAS

### 3.1 Obligación Principal: Prestación de Servicios de Infraestructura

**Fuente:** Informe Técnico de Servicios de Infraestructura C608201A (Código: C608201A)

INTERNEXA está obligada a:

| Obligación | Descripción | Alcance |
|------------|-------------|---------|
| **Aprovisionamiento de DC** | Data Center Principal y Data Center Alterno | 2 sitios físicos con redundancia |
| **Licenciamiento de Software** | Oracle 19, Oracle BI 12, Bizagi, VMware, Veeam, Fortinet, etc. | Todo el stack tecnológico del SICOM |
| **Seguridad Perimetral** | Firewall FortiGate, WAF, SIEM FortiAnalyzer | Protección de 27 servidores en producción |
| **Operación 24/7** | Monitoreo, backup, mantenimiento preventivo y correctivo | SLA no documentado en archivos analizados |
| **DRP Activo** | Plan de Recuperación ante Desastres | RPO < 4 horas, RTO < 8 horas (estándar de la industria) |

### 3.2 Cláusula Crítica de Licenciamiento (La única cláusula contractual explícita encontrada)

> *"Tener en cuenta que pueden existir licenciamientos con fecha de vigencia inferior al **periodo de cierre del presente contrato**, sin embargo, los licenciamientos aquí adjuntos son prestados a manera de servicio al Ministerio de Minas y Energía durante la vigencia del contrato mientras los servicios de licencia sean incluidos, por lo cual **Internexa garantizará la disponibilidad del licenciamiento necesario únicamente durante la duración del contrato**."*
>
> *"**Una vez finalizado el contrato, el siguiente licenciamiento deberá ser soportado por el Ministerio de Minas y Energía.**"*

**Interpretación ZEUS:**
- INTERNEXA **NO transfiere la propiedad** de los licenciamientos al MME.
- Los licenciamientos son **alquilados/prestados** durante la vigencia contractual.
- Al cierre del contrato, el MME debe **adquirir sus propias licencias** o negociar una transición.
- Esto incluye: Oracle 19, Oracle BI, Bizagi, VMware vSphere, Veeam, Fortinet, etc.
- **Costo estimado de relicenciamiento:** Potencialmente millones de dólares anuales.

### 3.3 Obligaciones de Transición — ESTADO: NO DOCUMENTADO

**Resultado de búsqueda exhaustiva en 48 documentos:**
- ❌ **NO existe** un "Plan de Transición de Conocimiento"
- ❌ **NO existe** un "Plan de Migración del Operador"
- ❌ **NO existe** un "Plan de Cierre y Entrega Final"
- ❌ **NO existe** documentación de "Handover" o "Knowledge Transfer"
- ❌ **NO existen** actas de capacitación para personal del MME
- ❌ **NO existe** un "Runbook de Operación" para el MME

### 3.4 Documentación Técnica Entregada (Operativa, NO de Transición)

Lo que INTERNEXA SÍ ha generado (pero NO necesariamente entregado como paquete de transición):

| Documento | Tipo | Útil para Transición? |
|-----------|------|----------------------|
| Caracterización de Procesos Apoyo (M-126) | Operativo | ✅ Parcialmente |
| Caracterización Procesos Principales Core (M-127) | Operativo | ✅ Parcialmente |
| Caracterización Procesos Control (M-128) | Operativo | ✅ Parcialmente |
| Manual de Guías Digitales (M-122) | Usuario Final | ❌ No aplica a operador |
| Manual de Usuario SIGDI | Usuario Final | ❌ No aplica a operador |
| Procedimiento Configuración SSL (P-11) | Técnico | ✅ Alto valor |
| Plan y Ejecución Pruebas DRP | Técnico | ✅ Crítico |
| Matriz de Vulnerabilidades | Seguridad | ✅ Alto valor |
| Informe Ethical Hacking | Seguridad | ✅ Alto valor |
| Roadmap de Migración a Gas | Técnico | ✅ Parcialmente |
| Inventario de Infraestructura | Técnico | ✅ Crítico |

> ⚠️ **NINGUNO de estos documentos fue encontrado como un paquete estructurado de "Transición de Conocimiento".**

---

## 4. RESPONSABILIDADES DE ENTREGA AL CIERRE (Inferidas)

Basado en las obligaciones operativas identificadas, al cierre del contrato INTERNEXA debería entregar:

### 4.1 Entregables Técnicos Mínimos

| # | Entregable | Prioridad | Estado en Documentos |
|---|------------|-----------|----------------------|
| 1 | **Inventario completo de infraestructura** | 🔴 CRÍTICO | ✅ Existe (C608201A) |
| 2 | **Licenciamiento y contratos de software** | 🔴 CRÍTICO | ❌ NO existe como paquete de entrega |
| 3 | **Credenciales y contraseñas** | 🔴 CRÍTICO | ❌ NO documentado en archivos analizados |
| 4 | **Documentación de arquitectura** | 🔴 CRÍTICO | ✅ Parcial (existe pero dispersa) |
| 5 | **Código fuente y repositorios** | 🟡 ALTA | ⚠️ Git mencionado (git.sicom.gov.co) pero sin detalle de acceso |
| 6 | **Manuales de operación y administración** | 🟡 ALTA | ❌ NO existe manual de "Operación del SICOM para nuevo operador" |
| 7 | **Matriz de integraciones y APIs** | 🟡 ALTA | ⚠️ Mencionada en arquitectura pero no como documento de transición |
| 8 | **Plan de continuidad DRP documentado** | 🟡 ALTA | ✅ Existe pero como procedimiento, no como paquete de entrega |
| 9 | **Base de conocimiento Aranda** | 🟢 MEDIA | ✅ Existe pero es propiedad operativa actual |
| 10 | **Capacitación a nuevo operador** | 🔴 CRÍTICO | ❌ NO existe evidencia de programa de capacitación |

### 4.2 Responsabilidades de Conocimiento Tácito (No Documentado)

Lo que INTERNEXa posee en **conocimiento tácito** (en la cabeza de sus ingenieros) que NO está escrito:

- Conocimiento de las **personalizaciones específicas** de Bizagi para el SICOM
- Conocimiento de las **reglas de negocio implícitas** en los procesos BPM
- Conocimiento de los **workarounds y soluciones temporales** aplicados
- Relaciones con **terceros** (ETB, proveedores, entidades reguladas)
- Conocimiento de la **configuración específica de red** (segmentación, reglas de firewall)
- Conocimiento de los **procedimientos de emergencia** no documentados

---

## 5. PLAN DE MIGRACIÓN DEL OPERADOR — ESTADO: INEXISTENTE

### 5.1 Búsqueda Realizada

Se buscó en los 48 documentos términos como:
- "Plan de migración del operador"
- "Transición de operador"
- "Cambio de operador"
- "Handover"
- "Knowledge transfer"
- "Transferencia de conocimiento"
- "Nuevo proveedor"
- "Sucesión de contrato"

**Resultado:** CERO documentos encontrados.

### 5.2 Roadmap de Migración Encontrado (PERO NO ES DE OPERADOR)

El documento **"Roadmap Migración a Gas 30 ENE 2026"** existe, pero es:
- Una **migración TÉCNICA** del módulo de Gas Combustible Vehicular
- NO una migración del **operador del sistema**
- Documenta el cambio de tecnología, NO el cambio de contratista

---

## 6. ANÁLISIS DE RIESGO CONTRACTUAL

### 6.1 Riesgos Identificados

| Riesgo | Probabilidad | Impacto | Descripción |
|--------|-------------|---------|-------------|
| **R1: Falta de fecha de cierre conocida** | 🔴 Alta | 🔴 Crítico | El MME no tiene claridad sobre CUÁNDO vence el contrato actual |
| **R2: Ausencia de plan de transición** | 🔴 Alta | 🔴 Crítico | No hay ruta definida para transferir operación a nuevo operador |
| **R3: Dependencia de licenciamiento de INTERNEXA** | 🔴 Alta | 🔴 Crítico | Todas las licencias de software son prestadas, no transferidas |
| **R4: Pérdida de conocimiento tácito** | 🟡 Media | 🔴 Crítico | Ingenieros de INTERNEXA se van con el conocimiento no documentado |
| **R5: Costo de relicenciamiento no presupuestado** | 🟡 Media | 🔴 Crítico | El MME no ha separado recursos para comprar licencias propias |
| **R6: Interrupción de servicio** | 🟡 Media | 🔴 Crítico | Sin plan de transición, el corte puede ser abrupto |
| **R7: Vulnerabilidades de seguridad no mitigadas** | 🟢 Baja | 🟡 Alto | La matriz de vulnerabilidades muestra problemas sin resolver que el nuevo operador heredará |

### 6.2 Matriz de Responsabilidades (RACI Inferida)

| Actividad | MME | INTERNEXA | Nuevo Operador | Estado |
|-----------|-----|-----------|----------------|--------|
| Definir fecha de cierre | R | I | — | ❌ No definido |
| Crear plan de transición | A/R | C | I | ❌ No existe |
| Transferir credenciales | I | R | C | ❌ No documentado |
| Transferir licenciamiento | A/R | C | I | ⚠️ Parcial (sólo se sabe que INTERNEXa no transfiere) |
| Capacitar nuevo operador | A | R | C | ❌ No existe programa |
| Documentar arquitectura | I | R | C | ✅ Parcialmente hecho |
| Validar integraciones | I | R | C | ❌ No documentado |
| Ejecutar DRP conjunto | A | R | C | ❌ No programado |

*Leyenda: R=Responsable, A=Accountable, C=Consultado, I=Informado*

---

## 7. RECOMENDACIONES ESTRATÉGICAS INMEDIATAS

### 7.1 Prioridad 1: URGENTE (Esta semana)

1. **Localizar el contrato GGC 2034-2025 físico o en SECOP II**
   - Extraer fecha de inicio, fecha de terminación, cláusulas de término
   - Identificar cláusula de transición de conocimiento (si existe)
   - Identificar penalidades y SLAs

2. **Determinar la "fecha tope" real del contrato**
   - Consultar con el área jurídica del MME
   - Verificar si hay prórrogas en trámite
   - Confirmar si hay un nuevo proceso de selección en curso

3. **Auditar el estado de licenciamientos**
   - Listar TODOS los licenciamientos actuales con fechas de vencimiento
   - Estimar costo de adquisición para el MME o nuevo operador
   - Negociar con INTERNEXA un plan de transición de licencias

### 7.2 Prioridad 2: ALTA (Este mes)

4. **Exigir a INTERNEXA un Plan de Transición de Conocimiento**
   - Aún si el contrato no lo exige, negociarlo como adendum
   - Debe incluir: capacitación, documentación, runbooks, shadowing

5. **Crear un Comité de Transición**
   - Representantes del MME, INTERNEXA, y potencial nuevo operador
   - Reuniones semanales con acta y seguimiento

6. **Preservar el conocimiento tácito**
   - Entrevistas estructuradas con ingenieros clave de INTERNEXA
   - Grabación de sesiones de "shadowing" (parado junto al operador)
   - Documentación de decisiones arquitectónicas (Architecture Decision Records)

### 7.3 Prioridad 3: MEDIA (Próximos 2 meses)

7. **Preparar la infraestructura para migración**
   - Si el nuevo operador es interno (MME) o externo, necesita infraestructura
   - El roadmap de migración a gas debe alinearse con el cambio de operador

8. **Negociar la transición de servicios críticos**
   - Mesa de servicio (WolKVOX, Aranda)
   - Certificados SSL (DIGICERT en nombre del MME)
   - Acceso a repositorios de código (git.sicom.gov.co)

---

## 8. CONCLUSIÓN CONTRACTUAL

### Lo que SE SABE con certeza:
1. INTERNEXA opera el SICOM bajo el contrato **GGC 2034-2025**
2. El contrato anterior (**GGC 1685-2025**) ya finalizó
3. INTERNEXa **NO transfiere licenciamientos** al MME al cierre
4. Existe documentación técnica operativa (48 documentos) pero **NO un paquete de transición estructurado**

### Lo que NO se sabe (y es crítico):
1. ❌ Fecha exacta de cierre del contrato actual
2. ❌ Si existe cláusula de transición de conocimiento
3. ❌ Si existe plan de migración del operador
4. ❌ Si hay un nuevo proceso de selección en curso
5. ❌ Presupuesto del MME para asumir licenciamientos
6. ❌ Capacidad del MME para operar el sistema sin INTERNEXA

### Veredicto ZEUS:
> **La situación contractual es OPAQUE. El MME opera sin visibilidad completa de su contrato. Esto es un riesgo institucional de primer orden.**

---

*Documento generado por ZEUS AGENTE IA — INNOVADATACO*  
*Fuentes: 48 documentos técnicos SICOM analizados exhaustivamente*  
*Metodología: Análisis documental, extracción de cláusulas indirectas, inferencia de obligaciones*
