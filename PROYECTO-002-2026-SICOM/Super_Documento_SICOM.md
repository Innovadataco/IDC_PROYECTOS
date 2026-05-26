# SICOM — SUPER DOCUMENTO TÉCNICO Y FUNCIONAL
**Sistema de Información de Combustibles Líquidos Derivados del Petróleo**
**Ministerio de Minas y Energía — Colombia**

---

**Versión:** 2.0 (Reformateo profesional — fiel al contenido original)  
**Fecha de análisis:** Mayo 2026  
**Fuente:** Carpeta documental SICOM (Google Drive) — 48 documentos técnicos analizados  
**Alcance:** Arquitectura de procesos, funcionalidades, módulos, actores, infraestructura, seguridad, operación, gobernanza y migración

---

## TABLA DE CONTENIDO

1. [Resumen Ejecutivo](#1-resumen-ejecutivo)
2. [Visión General del SICOM](#2-visión-general-del-sicom)
3. [Marco Normativo y Regulatorio](#3-marco-normativo-y-regulatorio)
4. [Arquitectura de Procesos](#4-arquitectura-de-procesos)
5. [Módulos del Sistema](#5-módulos-del-sistema)
6. [Actores, Roles y Responsables](#6-actores-roles-y-responsables)
7. [Funcionalidades Detalladas](#7-funcionalidades-detalladas)
8. [Infraestructura Tecnológica](#8-infraestructura-tecnológica)
9. [Seguridad de la Información](#9-seguridad-de-la-información)
10. [Operación y Soporte](#10-operación-y-soporte)
11. [Integraciones y APIs](#11-integraciones-y-apis)
12. [Glosario Técnico](#12-glosario-técnico)
13. [Gobernanza del Proyecto y Control de Cambios](#13-gobernanza-del-proyecto-y-control-de-cambios)
14. [Migración a Gas](#14-migración-a-gas)
15. [Indicadores y Reportes de Servicio (ANS)](#15-indicadores-y-reportes-de-servicio-ans)
16. [Riesgos y Controles](#16-riesgos-y-controles)
17. [Anexo A: Historial de RFCs](#anexo-a-historial-de-rfcs-documentados)
18. [Anexo B: Control de Cambios](#anexo-b-control-de-cambios)
19. [Anexo C: Activos de Infraestructura](#anexo-c-activos-de-infraestructura-sicom)
20. [Anexo D: Procedimiento de Gestión de Vulnerabilidades](#anexo-d-procedimiento-de-gestión-de-vulnerabilidades)
21. [Anexo E: Módulo de Contingencias](#anexo-e-módulo-de-contingencias-de-abastecimiento)
22. [Anexo F: Dataset de Casos Aranda](#anexo-f-dataset-de-casos-aranda-enero-2026)
23. [Anexo G: Workaround Módulo Encuestas](#anexo-g-solución-workaround-módulo-encuestas)
24. [Anexo H: Listado de Requerimientos](#anexo-h-listado-general-de-requerimientos-sicom-líquidos)

---

## 1. RESUMEN EJECUTIVO

El **SICOM** (Sistema de Información de Combustibles Líquidos Derivados del Petróleo) constituye la plataforma tecnológica estratégica del Ministerio de Minas y Energía de Colombia, encargada de organizar, controlar y sistematizar la comercialización, distribución, transporte y almacenamiento de combustibles líquidos derivados del petróleo, alcohol carburante y biodiesel a nivel nacional.

Este sistema integra a todos los agentes de la cadena de distribución en una única plataforma de información, gestionando —desde la creación de agentes y sus plantas hasta la generación de órdenes de pedido, guías digitales de transporte, monitoreo de vehículos, registro de precios, control de volúmenes y declaración de información operativa— con una arquitectura robusta que garantiza la trazabilidad, seguridad y cumplimiento normativo de cada transacción.

El SICOM está construido sobre una arquitectura BPM (Business Process Management) usando **Bizagi**, con múltiples módulos integrados: portal web, SIGDI (guías digitales), BI (Business Intelligence), call center, portal de autogestión, y está respaldado por una infraestructura de alta disponibilidad con medidas de seguridad de nivel empresarial (WAF, SIEM, ethical hacking, pentesting).

### 1.1 Estado General del Sistema

| Dimensión | Estado | Indicador |
|-----------|--------|-----------|
| **Operación Plataforma Líquidos** | Estable, con incidentes menores | 🟢 Verde |
| **Operación Plataforma GNCV** | Estable | 🟢 Verde |
| **Disponibilidad ANS** | 99.77% (dic 2025) vs >99.98% comprometido | 🔴 Rojo |
| **Seguridad** | Pentesting + Vulnerabilidades monitoreadas | 🟡 Amarillo |
| **Migración a Gas** | En desarrollo, backlog activo | 🟡 Amarillo |
| **Call Center / Mesa de Ayuda** | Operativo, ~1,900 casos/mes | 🟢 Verde |
| **DRP / Continuidad** | Pruebas documentadas, RPO/RTO definidos | 🟡 Amarillo |
| **Control de Cambios** | Comité activo, RFCs gestionados | 🟢 Verde |

> **Evaluación:** El SICOM es una plataforma **madura y crítica** para la operación del sector combustibles en Colombia. Su arquitectura BPM permite flexibilidad normativa, aunque presenta desafíos de disponibilidad que requieren atención continua.

---

## 2. VISIÓN GENERAL DEL SICOM

### 2.1 Definición

> **SICOM** es el Sistema de Información de la Cadena de Distribución de Combustibles Líquidos Derivados del Petróleo del Ministerio de Minas y Energía, el cual integra a los agentes de la cadena a nivel nacional en un solo sistema de información y mediante el cual se organiza, controla y sistematiza la comercialización, distribución, transporte y almacenamiento de combustibles líquidos derivados del petróleo, alcohol carburante y biodiesel.

### 2.2 Tipos de Combustibles Gestionados

El SICOM administra los siguientes combustibles:

| Combustible | Código | Observaciones |
|-------------|--------|---------------|
| Gasolina motor extra | — | Uso general vehicular |
| Gasolina corriente | — | Uso general vehicular |
| Gasolina oxigenada | — | Zonas de altura |
| Combustibles de aviación (Avgas, Jet Fuel) | — | Aviación civil y militar |
| Queroseno | — | Iluminación y calefacción |
| Diésel extra / Diésel de bajo azufre | — | Uso vehicular y maquinaria |
| Diésel corriente (ACPM) | — | Uso industrial y agrícola |
| Diésel marino / fluvial | — | Embarcaciones |
| Fuel oil / Combustóleo | — | Quemadores industriales |
| Alcohol carburante | — | Mezcla con gasolina |
| Biodiesel | — | Mezcla con diésel |

### 2.3 Tipos de Agentes de la Cadena

| Tipo de Agente | Código SICOM | Descripción |
|----------------|--------------|-------------|
| **Refinador** | 01 | Procesa crudo para producir combustibles |
| **Importador** | 02 | Importa combustibles al país |
| **Almacenador** | 03 | Opera instalaciones de almacenamiento |
| **Distribuidor Mayorista** | 04 | Distribuye al por mayor mediante plantas de abastecimiento |
| **Transportador** | 05 | Transporta combustibles por carretera, fluvial o ferrocarril |
| **Distribuidor Minorista** | 06 | Opera estaciones de servicio (EDS) o comercializadores industriales |
| **Gran Consumidor** | 07 | Consume grandes volúmenes de combustible (fuerzas militares, industria) |

### 2.4 Tipos de Estaciones de Servicio (EDS)

| Tipo | Características |
|------|-----------------|
| **EDS Automotriz** | Surtidores fijos para vehículos automotores |
| **EDS Aviación** | Combustibles para aeronaves (Avgas, Jet Fuel) |
| **EDS Marítima** | Combustibles para embarcaciones marítimas |
| **EDS Fluvial** | Combustibles para transporte fluvial |
| **EDS Mixta** | Combustibles líquidos y gaseosos en un mismo sitio |
| **EDS Privada** | Exclusiva para flota propia de una empresa |
| **EDS Pública** | Abierta al público general |
| **EDS Dedicada** | Solo un tipo de combustible (ej: solo diésel) |

### 2.5 Plataformas del SICOM

| Plataforma | URL / Acceso | Función Principal |
|------------|-------------|-------------------|
| **Portal Web SICOM (Home)** | https://www.sicom.gov.co | Portal principal de gestión y autenticación |
| **Nuevo SICOM** | Plataforma evolutiva | Optimización UX y nuevos módulos BPM |
| **SIGDI** | https://sigdi.sicom.gov.co/guias/ | Guías digitales de transporte |
| **Portal de Autogestión** | Integrado en SICOM | Registro de casos y solicitudes sin call center |
| **Bizagi (BPM)** | Motor de procesos interno | Workflow engine y orquestación de procesos |
| **BI / Cubos** | https://bi.sicom.gov.co | Inteligencia de negocio y calidad del dato |
| **Call Center** | https://mesadeservicio.sicom.gov.co | Mesa de servicio y tickets Aranda |

---

## 3. MARCO NORMATIVO Y REGULATORIO

El SICOM opera bajo un marco normativo robusto que define su alcance, obligaciones y restricciones:

| Norma | Descripción | Aplicación en SICOM |
|-------|-------------|---------------------|
| **Decreto 1073 de 2015** | Decreto Único del Sector Minas y Energía | Normativa principal que regula la operación del SICOM |
| **Decreto 1135 de 2022** | Modificaciones al régimen de combustibles | Actualizaciones recientes al marco regulatorio |
| **Resolución SIGDI 40483 de 2023** | Sistema de Información de Guías Digitales de Transporte | Regula la generación y control de guías digitales |
| **Resolución 0242 de 2019** | Marco regulatorio de operación | Procedimientos y obligaciones de agentes |
| **Decreto 1120 de 2021** | Disposiciones sobre comercialización | Normativa sobre precios, volúmenes y comercialización |

> **Nota regulatoria:** Cada cambio normativo requiere ajustes en los procesos BPM, reglas de negocio y parámetros del sistema, gestionados mediante el Comité de Control de Cambios (CCC).

---

## 4. ARQUITECTURA DE PROCESOS

El SICOM está diseñado sobre una arquitectura de procesos BPMN 2.0 (Business Process Model and Notation), implementada en la plataforma **Bizagi**. Los procesos se dividen en tres grandes grupos funcionales que cubren el ciclo de vida completo de la cadena de suministro.

### 4.1 Macroproceso de Combustibles Líquidos

El macroproceso describe el flujo end-to-end de la cadena de suministro:

```
[Agente] → [Creación/Validación] → [Orden de Pedido] → [Despacho] → [Transporte/SIGDI] → [Cierre/Cumplido] → [Monitoreo/Control]
```

**Fases del macroproceso:**
1. **Registro y Habilitación:** Creación de agentes, plantas, vehículos y usuarios
2. **Comercialización:** Órdenes de pedido, precios, volúmenes máximos
3. **Logística:** Despacho, transporte, guías digitales, monitoreo
4. **Cierre y Declaración:** Cumplidos, declaración de información, control

### 4.2 Procesos de Apoyo (M-126)

Los procesos de apoyo alimentan y soportan los procesos principales:

| Proceso | Descripción | Responsable | Reglas Clave |
|---------|-------------|-------------|--------------|
| **Crear Agente** | Registro de nuevo agente en portal web. Genera código SICOM de 6 dígitos. | Agente + MME | Validación en 60 días, NIT único, código: 2 dígitos tipo + 4 consecutivo |
| **Validar Información** | Subproceso reusable de validación por funcionarios MME | MME | Dos validadores: Responsable Funcional + Coordinador |
| **Actualizar Agente** | Modificación de datos del agente existente | Agente + MME | Reutiliza subproceso "Validar Información" |
| **Gestión de Usuarios** | Creación, modificación, inactivación de usuarios | Agente + Admin | Usuarios principales y secundarios |
| **Gestión de Acuerdos y Productos** | Configuración de acuerdos comerciales y catálogo | Agente | Define relaciones comerciales entre agentes |
| **Gestión de Plantas** | Creación y actualización de plantas de abastecimiento | Agente + MME | Incluye EDS automotriz, aviación, marítima, fluvial, industrial |
| **Gestión de Vehículos** | Registro de vehículos autorizados para transporte | Agente | SOAT, pólizas, revisión técnico-mecánica, licencias |
| **Validación Documentos Vehículo** | Verificación automática de documentos | Sistema (Jobs) | Alertas diarias de vencimiento |
| **Gestión de Mezclas** | Configuración de mezclas de combustibles | Agente + MME | Gasolina corriente oxigenada, extra oxigenada |

**Reglas de Negocio Detalladas — Crear Agente:**
- No se permite crear una razón social con el mismo NIT/RUT existente.
- Un NIT puede tener múltiples códigos SICOM asociados (uno por tipo de agente).
- El código SICOM tiene 6 dígitos: 2 primeros = tipo de agente, 4 últimos = consecutivo.
- Las direcciones se normalizan automáticamente mediante servicio de geocodificación.
- Correos electrónicos y páginas web se validan automáticamente (estructura y disponibilidad).
- Si la EDS es operada por propietario, los datos son no editables; si es arrendatario, permite edición.
- Solo se permite adjuntar documentos en formato PDF.
- Duración máxima de validación: 60 días calendario.

### 4.3 Procesos Principales / Core (M-127)

Los procesos principales gestionan la generación y ejecución de órdenes de pedido:

| Proceso | Descripción | Actores | Estados |
|---------|-------------|---------|---------|
| **Orden de Pedido Simple (OPS)** | Tipo más común. Permite solicitar múltiples productos. Genera cumplido si aplica. Posibilidad de devoluciones. | Solicitante → Proveedor → Puesto de Control | Solicitud → Aceptada → Despachada → Tránsito → Cumplido → Cerrada |
| **Orden de Pedido Programada** | Órdenes con programación temporal recurrente | Agente | Programada → Activa → Cerrada |
| **Orden de Pedido Anticipada Individual** | Solicitud anticipada por un agente individual | Agente | Anticipada → Aceptada → Despacho |
| **Orden de Pedido Anticipada por Nominación** | Solicitud anticipada con nominación de volúmenes | Agente + MME | Nominada → Aprobada → Despacho |
| **Orden de Pedido de Transferencia** | Transferencia de combustibles entre instalaciones del mismo agente | Agente | Transferencia → Aceptada → Despacho |
| **Gestión de Despachos OP** | Control de despachos para órdenes anticipadas | Agente Proveedor | Pendiente → Despachado |
| **Cargue Masivo de Entregas** | Proceso batch para cargar múltiples entregas | Agente + Sistema | Procesado → Validado |
| **Actualizar Órdenes de Pedido** | Modificación de órdenes existentes | Agente | Actualizada → Revalidada |
| **Recepción Guía Digital** | Subproceso de recepción y validación de guías | Agente + SIGDI | Generada → Firmada |
| **Monitoreo de Vehículos** | Subproceso de seguimiento de vehículos en tránsito | Sistema + Agente | En tránsito → Entregado |

**Flujo Detallado de Orden de Pedido Simple:**

1. **Agente Solicitante CREA** la orden de pedido con productos, volúmenes y planta destino.
2. **Sistema GENERA** y envía resultado del cumplido (si aplica según configuración).
3. **Sistema CARGA** vehículos habilitados del proveedor para asignación.
4. **Agente Proveedor ACEPTA** la orden → Si rechaza: notifica rechazo con observaciones, fin del proceso.
5. **Agente Proveedor DESPACHA** la orden → Asigna vehículo, conductor, precintos. Si rechaza: notifica, fin.
6. **Subproceso: RECEPCIÓN GUÍA DIGITAL** en SIGDI (código de autorización de 15 dígitos).
7. **Subproceso: MONITOREO VEHÍCULOS** — seguimiento en tránsito con alertas de desviación.
8. **Puesto de Control VALIDA Y REGISTRA** cumplido de entrega (volúmenes, calidad, observaciones).
9. **Agente Solicitante DILIGENCIA** cumplimiento de requisitos pendientes.
10. **Agente / Sistema CIERRA** la orden de pedido. Estado final: Cerrada.

**Estados de una Orden de Pedido:**
- Solicitud → Aceptada → Despachada → En tránsito (monitoreo) → Cumplido validado → Cerrada → Rechazada / Anulada

**Devoluciones posibles en el flujo:**
- Devolución a solicitud (desde estado de aceptación)
- Devolución en despacho (corrección de datos de transporte)
- Anulación total (evento intermedio "Anular OPS" en cualquier estado previo a cierre)

**Notificaciones automáticas por correo electrónico:**
- Creación de orden → Notificación al proveedor
- Aceptación/Rechazo → Notificación al solicitante
- Despacho → Notificación al solicitante y transportador
- Cierre → Notificación final a ambas partes
- Anulación → Notificación de cancelación

### 4.4 Procesos de Control (M-128)

Los procesos de control permiten al Ministerio regular y supervisar la operación:

| Proceso | Descripción | Responsable | Frecuencia |
|---------|-------------|-------------|------------|
| **Inhabilitar Agente** | Desactivación total de agente, plantas y usuarios asociados | Operador Líder MME | Bajo demanda |
| **Notificar Vigencia Documentos** | Alertas automáticas por vencimiento de documentos | Sistema (Jobs) | Diaria |
| **Registro de Precios** | Ingreso de precios de combustibles por agentes | Agente | Periódica |
| **Asignación Precios Mínimos y Máximos** | Fijación de rangos de precios por parte del MME | MME | Periódica |
| **Asignación Volumen Máximo** | Definición de cupos máximos de compra por agente/producto | MME | Periódica |
| **Gestión Solicitudes Volumen Máximo** | Administración de solicitudes de incremento de cupos | Agente + MME | Bajo demanda |
| **Asignación/Reasignación Volúmenes** | Reasignación de cupos entre agentes o productos | MME | Bajo demanda |
| **Declaración de Información** | Reporte periódico de operaciones por parte de los agentes | Agente | Mensual/Quincenal |
| **Cargue Masivo Declaración** | Carga batch de declaraciones de información | Agente | Mensual |
| **Actualizar Declaración** | Corrección de declaraciones enviadas | Agente | Bajo demanda |
| **Bloqueo/Desbloqueo Agentes** | Control de acceso temporal por incumplimiento | Sistema (Jobs) + Operador | Diaria / Automático |

**Jobs Automáticos de Control (Cron Jobs diarios):**

| Job | Función | Impacto |
|-----|---------|---------|
| **JobAlerVencPoliVehi** | Alerta vencimiento póliza vehicular | Bloquea vehículos con documentos vencidos |
| **JobValDocsAg** | Validación documentos agente | Alerta agentes con documentos próximos a vencer |
| **JobValDocsPlan** | Validación documentos planta | Alerta plantas con documentos próximos a vencer |
| **JobValDocsVehi** | Validación documentos vehículos | Bloquea vehículos por SOAT/póliza vencida |

---

## 5. MÓDULOS DEL SISTEMA

### 5.1 Portal Web SICOM (Home)

El portal web es el punto de entrada principal para todos los agentes de la cadena. Diseñado como una aplicación web responsiva con autenticación segura.

**Funcionalidades principales:**
- **Autenticación:** Usuario y contraseña con política de complejidad. Bloqueo por intentos fallidos.
- **Registro de nuevos agentes:** Solicitud de creación con formulario guiado y adjuntos obligatorios.
- **Gestión de órdenes de pedido:** Creación, consulta, seguimiento y cierre de órdenes.
- **Consulta de estados:** Estado del agente, plantas, vehículos, documentos.
- **Actualización de documentos vencidos:** Carga de nuevos documentos para revalidación.
- **Asociación de vehículos:** Registro de nuevos vehículos y conductores.
- **Gestión de usuarios secundarios:** Creación y inactivación de usuarios adicionales por agente.
- **Registro de precios:** Ingreso de precios de venta por producto y planta.
- **Declaración de información:** Formularios de declaración periódica.
- **Portal de autogestión:** Radicación de casos sin intervención del call center.

### 5.2 SIGDI — Sistema de Información Guías Digitales de Transporte

SIGDI es el módulo crítico encargado de la generación de guías digitales de transporte para las órdenes de pedido despachadas en SICOM. Su correcta operación garantiza la trazabilidad legal del transporte de combustibles a nivel nacional.

**Funcionalidades principales:**

| Función | Descripción | Detalle Técnico |
|---------|-------------|-----------------|
| **Generación de Guías** | Creación automática de guía digital a partir de orden de pedido en estado "despachado" | Se ejecuta en segundo plano mediante Web Service |
| **Código de Autorización** | Número de 15 dígitos generado automáticamente por SICOM para cada orden | Identificador único de guía |
| **Número de Guía** | Consecutivo de 16 dígitos (inicia con 6 dígitos del código SICOM del agente) | Identificador visible en PDF |
| **Verificación de Firma** | Validación de autenticidad mediante código enviado por correo electrónico | Código de verificación de 6 dígitos |
| **Registro de Manifiesto** | Ingreso de precintos, código de manifiesto y empresa transportadora | Datos de seguridad del transporte |
| **Previsualización** | Vista previa de guía en PDF con marca de agua "diligenciamiento" (sin vigencia) | Visualización previa a firma |
| **Firma Digital** | Firma electrónica de la guía con fecha/hora de salida, vigencia, marca de agua "vigente" | PDF firmado con vigencia real |
| **Histórico de Guías** | Registro de todas las guías generadas por día, descargables e imprimibles | Histórico permanente |
| **Reporte de Novedades** | Notificación de ajustes realizados en SICOM sobre guías vigentes | Alerta de modificaciones |
| **Actualización de Firma** | Carga de firma en formato imagen (PNG, JPEG, JPG) o dibujo manual | Firma personalizada del autorizado |
| **Aprobación de Firma** | El administrador del sistema aprueba las firmas cargadas antes de su uso | Control de calidad de firmas |

**Flujo detallado SIGDI:**

1. Orden de pedido en SICOM alcanza estado **"Despachado"**.
2. Usuario de planta ingresa a SIGDI con credenciales de SICOM (mismo usuario/clave).
3. Sistema solicita **verificación de firma** — envía código de 6 dígitos al correo registrado.
4. Usuario ingresa **código de autorización** de 15 dígitos generado por SICOM.
5. Sistema **carga datos de la orden** (productos, volúmenes, origen, destino) — **NO EDITABLES**.
6. Usuario registra **manifiesto, precintos** y empresa transportadora.
7. Sistema presenta botones **"Previsualizar"** y **"Firmar"**.
8. **Previsualización:** Genera PDF sin firma, sin vigencia, con marca de agua "diligenciamiento".
9. **Firma:** Sistema valida que no haya actualizaciones recientes en SICOM. Si todo es válido, aplica firma digital.
10. **Guía firmada:** PDF con firma, fecha/hora de salida, vigencia en horas, marca "vigente".
11. **Notificación automática:** Correo electrónico de confirmación al agente con guía adjunta.
12. **Histórico:** Guía disponible para descarga e impresión en cualquier momento.

> **Regla crítica:** Los datos de la guía NO son editables en SIGDI. Si requieren cambio, se debe ajustar la orden de pedido en SICOM, devolverla al estado "despachado", y regenerar la guía.

### 5.3 BPM Bizagi

Bizagi es el motor de workflows que orquesta todos los procesos del SICOM, proporcionando flexibilidad para adaptarse a cambios normativos.

**Características técnicas:**
- Procesos modelados en BPMN 2.0 con notación estándar.
- Subprocesos reusables (ej: "Validar Información" se usa en Crear Agente y Actualizar Agente).
- Tareas de servicio (scripts automáticos en JavaScript/VBScript).
- Tareas de usuario con asignación por roles, grupos o reglas de negocio.
- Compuertas exclusivas de divergencia para decisiones condicionales.
- Eventos de inicio por mensaje (SOAP) para integraciones.
- Eventos intermedios de anulación, devolución y cierre.
- Duraciones configurables por actividad con alertas de vencimiento.
- Notificaciones automáticas por correo electrónico con plantillas personalizadas.

### 5.4 BI — Business Intelligence / Calidad del Dato

El módulo de BI proporciona inteligencia de negocio, control de calidad del dato y soporte a la toma de decisiones del MME.

**Componentes:**
- **Cubos OLAP:** Análisis multidimensional de datos operativos (ventas, inventarios, movimientos).
- **Tableros de control (Dashboards):** Visualización en tiempo real de indicadores clave.
- **Reportes de calidad del dato:** Medición de completitud, exactitud, consistencia y oportunidad.
- **Seguimiento quincenal:** Evaluación periódica de la calidad de la información reportada por agentes.
- **Matrices de competencias:** Seguimiento de capacitación y certificación de agentes.
- **Informes trimestrales:** Reportes consolidados al MME con análisis de tendencias.

**Tipos de reportes generados:**
- Calidad del dato por agente (ranking, alertas, comparativas).
- Calidad del dato por proceso (órdenes, guías, declaraciones).
- Estadísticas de cumplimiento normativo.
- Alertas de inconsistencias y datos fuera de rango.

### 5.5 Call Center / Mesa de Ayuda

**Infraestructura operativa:**
- **Plataforma telefónica:** WolKVOX (centro de contacto IP).
- **Sistema de tickets:** Aranda Service Desk (gestión de casos y SLAs).
- **Niveles de atención:** N1 (primer nivel / orientación) / N2 (especializado / técnico).

**Funciones del call center:**
- Atención telefónica a agentes de la cadena (horario extendido).
- Gestión de casos y tickets de soporte con categorización.
- Protocolos de atención documentados por tipo de incidente.
- Grabación de llamadas para calidad y auditoría (registro mensual).
- Informes mensuales de casos atendidos, tiempos de resolución y satisfacción.
- Escalamiento automático a N2 para casos técnicos complejos o fuera de SLA.

### 5.6 Portal de Autogestión

Plataforma complementaria que permite a los agentes gestionar sus propios casos sin saturar el call center.

**Funciones:**
- Radicación de casos con categorización automática.
- Seguimiento de solicitudes en tiempo real.
- Consulta de estado de trámites y órdenes.
- Actualización de datos de planta para SIGDI (correo electrónico obligatorio).
- Registro de correo electrónico de planta (requerido para operación en SIGDI).
- Consulta de documentos vencidos y requisitos pendientes.

---

## 6. ACTORES, ROLES Y RESPONSABLES

### 6.1 Agentes de la Cadena

| Rol | Código | Función en SICOM |
|-----|--------|-----------------|
| **Agente Solicitante** | — | Crea órdenes de pedido, solicita productos a proveedores |
| **Agente Proveedor** | — | Acepta y despacha órdenes de pedido, registra precios |
| **Puesto de Control** | — | Valida y registra cumplidos de órdenes de pedido |
| **Distribuidor Mayorista** | 04 | Opera plantas de abastecimiento, suministra a minoristas |
| **Distribuidor Minorista** | 06 | Opera estaciones de servicio (EDS), vende al público |
| **Gran Consumidor** | 07 | Solicita volúmenes mayores, opera flotas propias |
| **Transportador** | 05 | Registra vehículos, transporta combustibles con guías |

### 6.2 Roles del Ministerio (MME)

| Rol | Función | Nivel de Autoridad |
|-----|---------|-------------------|
| **Responsable Funcional MME** | Valida información de agentes (1er validador) | Validador |
| **Coordinador MME** | Aprueba/Rechaza creación de agentes (2do validador) | Aprobador |
| **Operador Líder** | Inhabilita agentes, asigna precios/volúmenes, bloqueos | Administrador |
| **Administrador del Sistema** | Gestión de firmas SIGDI, configuración general | Técnico |
| **Profesional de Calidad** | Control de calidad del dato, auditorías | Analista |
| **Profesional de Operación Estadística** | Análisis estadístico, reportes al MME | Analista |

### 6.3 Equipo Operativo SICOM

#### Área Funcional

| Rol | Responsabilidad |
|-----|---------------|
| **Líder Funcional** | Dirección estratégica del sistema, toma de decisiones funcionales, interfaz con MME |
| **Analistas Funcionales** | Levantamiento de requerimientos, diseño de procesos, pruebas funcionales, documentación |
| **Formadores** | Capacitación a agentes, creación de material didáctico, webinars, microbits |
| **Profesional de Operación Estadística** | Análisis de datos, reportes estadísticos, indicadores de gestión |
| **Profesional de Calidad** | Aseguramiento de calidad, auditorías de procesos, control de calidad del dato |
| **Coordinador Call Center** | Dirección del centro de contacto, reportes de atención, gestión de SLAs |
| **Agente de Calidad** | Control de calidad en atención del call center, grabaciones, retroalimentación |

#### Área Técnica

| Rol | Responsabilidad |
|-----|---------------|
| **Líder Técnico** | Dirección técnica del proyecto, arquitectura de solución, decisiones tecnológicas |
| **Arquitecto de Software** | Diseño de arquitectura de aplicaciones, estándares técnicos, integraciones |
| **Desarrolladores Java** | Desarrollo backend, integraciones, APIs REST/SOAP, servicios web |
| **Desarrolladores BPM (Bizagi)** | Modelado e implementación de procesos en Bizagi, reglas de negocio |
| **Especialistas BI** | Diseño de cubos, tableros, ETL, calidad del dato, reportes analíticos |
| **Ingenieros de Pruebas (QA)** | Pruebas funcionales, automatizadas, regresión, validación de HU |
| **Administrador de Base de Datos** | Gestión de BD Oracle, tuning, backups, replicación, alta disponibilidad |
| **Especialistas en Inteligencia de Negocios** | Análisis de negocio, modelos predictivos, soporte a decisiones estratégicas |

---

## 7. FUNCIONALIDADES DETALLADAS

### 7.1 Gestión de Agentes

**Crear Agente (Proceso completo):**
- Registro desde portal web externo con formulario estructurado.
- Diligenciamiento de datos básicos: NIT, razón social, tipo de agente, dirección, contacto, representante legal.
- Adjuntos obligatorios según tipo de agente (RUT, cámara de comercio, actas) — **PDF únicamente**.
- Normalización automática de direcciones mediante servicio de geocodificación.
- Validación de estructura de correos electrónicos y páginas web (formato y resolución DNS).
- Cálculo automático de dígito de verificación del NIT con algoritmo oficial.
- Workflow de validación en Bizagi en dos etapas: Responsable Funcional (1er validador) + Coordinador (2do validador).
- Duración máxima de validación: 60 días calendario. Vencido el plazo, la solicitud se cancela automáticamente.
- Generación automática de código SICOM de 6 dígitos y credenciales de acceso.
- Notificación por correo electrónico con memorando de aprobación y credenciales.

**Actualizar Agente:**
- Modificación de datos del agente existente (dirección, contacto, representante).
- Reutilización del subproceso "Validar Información" con los mismos dos validadores.
- Control de versiones de documentos adjuntos (histórico de cambios).

**Inhabilitar Agente:**
- Desactivación completa en cascada: agente, plantas asociadas y usuarios relacionados.
- Notificación automática al agente con motivo de inhabilitación.
- Job automático de validación de documentos vencidos que puede derivar en inhabilitación.

**Bloqueo/Desbloqueo:**
- Bloqueo automático por documentos vencidos (Jobs diarios: JobValDocsAg, JobValDocsPlan).
- Desbloqueo manual por Operador Líder previa validación de documentos actualizados.

### 7.2 Gestión de Plantas

Tipos de plantas según el agente y su función en la cadena:
- **Planta de abastecimiento:** Distribuidor mayorista (almacenamiento y despacho).
- **EDS Automotriz:** Estación de servicio para vehículos automotores.
- **EDS Aviación:** Suministro de combustibles para aeronaves.
- **EDS Marítima:** Suministro para embarcaciones marítimas.
- **EDS Fluvial:** Suministro para transporte fluvial.
- **EDS Privada:** Uso exclusivo de flota propia.
- **EDS Pública:** Abierta al público general.
- **EDS Mixta:** Combustibles líquidos y gaseosos.
- **Comercializador Industrial:** Venta directa a industria sin surtidores públicos.
- **Instalación de Gran Consumidor:** Consumo propio de grandes volúmenes.

**Funcionalidades de gestión:**
- Creación de planta con datos georreferenciados (latitud, longitud, dirección normalizada).
- Asociación a agente propietario o arrendatario (determina editabilidad de datos).
- Configuración de productos habilitados por planta (gasolina, diésel, ACPM, etc.).
- Gestión de documentos de la planta (licencias ambientales, permisos de bomberos, etc.).
- Inhabilitación automática en cascada cuando se inhabilita el agente principal.
- Actualización de datos para SIGDI (correo electrónico obligatorio para recepción de códigos de verificación).

### 7.3 Gestión de Vehículos

**Datos del vehículo:**
- Placa, tipo de vehículo (camión cisterna, pipa, etc.), capacidad en galones.
- SOAT (vigencia, aseguradora, número de póliza).
- Póliza de seguro de mercancía (vigencia, coberturas).
- Revisión técnico-mecánica (vigencia, centro de diagnóstico).
- Licencia de conducción del conductor (categoría, vigencia, restricciones).

**Validaciones automáticas diarias:**
- **JobAlerVencPoliVehi:** Alerta de vencimiento de póliza vehicular 15 días antes.
- Bloqueo automático de vehículo si SOAT o póliza están vencidos.
- Asociación obligatoria a agente transportador habilitado.
- Validación de capacidad del vehículo vs. volumen de la orden de pedido.

### 7.4 Órdenes de Pedido

**Tipos de Orden de Pedido:**

| Tipo | Descripción | Uso Principal | Actores |
|------|-------------|---------------|---------|
| **Simple (OPS)** | Solicitud estándar de uno o más productos | Mayoría de transacciones comerciales | Solicitante → Proveedor → Puesto de Control |
| **Programada** | Órdenes con programación temporal recurrente | Suministro continuo a EDS | Agente + MME (si aplica) |
| **Anticipada Individual** | Solicitud anticipada por agente individual | Planificación de compras | Agente individual |
| **Anticipada por Nominación** | Solicitud anticipada con volúmenes nominados | Control de cupos Gran Consumidor | Agente + MME |
| **Transferencia** | Movimiento entre instalaciones del mismo agente | Reubicación de inventario interno | Agente (mismo NIT) |

**Estados del Flujo (máquina de estados):**
1. **Solicitud** → Orden creada, pendiente de aceptación.
2. **Aceptada** → Proveedor aceptó, pendiente de despacho.
3. **Despachada** → Producto cargado, en tránsito.
4. **En tránsito** → Monitoreo activo, guía digital generada.
5. **Cumplido validado** → Puesto de Control validó entrega.
6. **Cerrada** → Orden finalizada, facturación y declaración.
7. **Rechazada** → Proveedor rechazó, con observaciones.
8. **Anulada** → Cancelación total antes del cierre.

**Devoluciones y correcciones:**
- Devolución a solicitud (desde aceptación): Corregir productos, volúmenes o planta.
- Devolución en despacho: Corregir datos de transporte, vehículo o conductor.
- Anulación total: Evento intermedio "Anular OPS" disponible en estados previos a cierre.

**Notificaciones automáticas por correo electrónico:**
- **Creación:** Notificación inmediata al proveedor con detalles de la orden.
- **Aceptación/Rechazo:** Notificación al solicitante con estado y observaciones.
- **Despacho:** Notificación al solicitante y al transportador con datos de carga.
- **Cierre:** Notificación final con resumen de entrega y cumplido.
- **Anulación:** Notificación de cancelación con motivo registrado.

### 7.5 Guías Digitales (SIGDI)

Ver sección 5.2 para detalle completo del módulo. Puntos clave adicionales:

- Las guías se generan **SOLO** para órdenes en estado "Despachado".
- Los precios se registran en SICOM y se reflejan automáticamente en SIGDI.
- El cierre de OPS genera automáticamente la guía digital mediante Web Service.
- Las guías tienen **vigencia temporal definida en horas** (configurable por tipo de producto y distancia).
- Las guías firmadas son **válidas legalmente** para transporte de combustibles a nivel nacional.
- La guía incluye tres secciones: información general (agentes, productos), información de transporte (vehículo, conductor, precintos), información de productos (volúmenes, precios).

### 7.6 Monitoreo y Cumplidos

**Monitoreo de Vehículos:**
- Subproceso que permite seguimiento de vehículos en tránsito en tiempo real.
- Georreferenciación mediante integración con sistemas GPS de transportadores.
- Alertas automáticas de desviación de rutas predefinidas.
- Control de tiempos de entrega vs. ventanas horarias configuradas.
- Notificación de entrada/salida a puntos de control geográficos.

**Cumplidos:**
- Documento que certifica la entrega física de combustible en las condiciones pactadas.
- Validado por el **Puesto de Control** (físico o virtual según configuración).
- Incluye: volúmenes efectivamente entregados, calidad del producto (densidad, temperatura), observaciones de incumplimiento.
- Generación automática por el sistema cuando aplica según configuración del agente.
- Firma digital del receptor y del transportador.

### 7.7 Precios y Volúmenes

**Registro de Precios:**
- Los agentes registran precios de venta por producto y planta de forma periódica.
- El sistema valida que los precios estén dentro de los rangos mínimos/máximos definidos por el MME.
- Histórico de precios por fecha, con gráficos de tendencia en BI.
- Alertas de precios fuera de rango para investigación del MME.

**Asignación de Precios Mínimos y Máximos:**
- El Operador Líder del MME define rangos de precios por producto y región.
- Los precios fuera de rango generan alertas inmediatas y bloqueos preventivos.
- Revisión periódica según fórmula de precios de referencia internacional.

**Volumen Máximo (Cupos):**
- Cupos de compra máximos por agente y producto (mensual/quincenal).
- Solicitudes de incremento de cupo con justificación técnica/económica.
- Reasignación de volúmenes entre agentes (ej: por renuncia de cupo).
- Control de consumo vs. cupo asignado con alertas de exceso.
- Cesión de cupos entre agentes del mismo tipo.

### 7.8 Declaración de Información

Los agentes deben declarar periódicamente (mensual/quincenal) la siguiente información:
- **Inventarios de combustibles:** Stock inicial, entradas, salidas, stock final por producto y tanque.
- **Compras y ventas:** Volúmenes comprados y vendidos por producto, precios promedio.
- **Importaciones:** Volúmenes importados, país de origen, costos.
- **Exportaciones:** Volúmenes exportados, país destino.
- **Producción (refinadores):** Volúmenes producidos por producto.
- **Movimientos entre instalaciones:** Transferencias internas.

**Modalidades de declaración:**
- **Formulario web:** Declaración individual en línea con validaciones en tiempo real.
- **Cargue masivo:** Archivo Excel con formato estándar para declaraciones de múltiples periodos.
- **Actualización:** Corrección de declaraciones enviadas con errores (con trazabilidad de cambios).
- **Validación:** Consistencia de datos (stock inicial + entradas - salidas = stock final).

### 7.9 Gestión de Usuarios y Perfiles

**Tipos de Usuario:**

| Tipo | Descripción | Permisos |
|------|-------------|----------|
| **Usuario Principal** | Administrador del agente, tiene acceso total | Todas las funciones del agente |
| **Usuario Secundario** | Usuario con permisos limitados, creado por el principal | Según asignación (órdenes, precios, consultas) |
| **Usuario Planta** | Usuario específico para operar en SIGDI desde una planta | Generación de guías, consulta de órdenes despachadas |

**Permisos configurables:**
- Crear órdenes de pedido (solicitante).
- Aceptar/despachar órdenes (proveedor).
- Registrar precios de venta.
- Declarar información operativa.
- Gestionar vehículos y conductores.
- Consultar reportes y estados.
- Administrar usuarios secundarios (solo principal).

---

## 8. INFRAESTRUCTURA TECNOLÓGICA

### 8.1 Arquitectura de Red

El SICOM opera sobre una infraestructura de red segmentada, redundante y de alta disponibilidad:

- **Conectividad Internet:** Múltiples proveedores (ETB, INTERNEXA) con enlaces independientes.
- **Enlaces dedicados:** Conectividad punto a punto hacia instalaciones críticas (Ministerio, centros de datos).
- **Redundancia:** Enlaces primarios y de respaldo con conmutación automática (failover < 30 segundos).
- **Segmentación:** VLANs por función (Web pública, Aplicaciones, Base de datos, Administración, Monitoreo).
- **Filtrado:** Firewalls perimetrales con reglas de acceso restrictivas (deny-all, permit-by-exception).

### 8.2 Seguridad Perimetral

| Componente | Tecnología | Función | Ubicación |
|------------|-----------|---------|-----------|
| **Firewall UTM** | Fortinet FGT2600F | Filtrado de tráfico, VPN site-to-site, IDS/IPS, antivirus | Perímetro de red |
| **WAF** | FortiWeb | Protección de aplicaciones web, anti-bot, anti-DDoS, reglas personalizadas | DMZ frente a servidores web |
| **SIEM** | FortiSIEM | Centralización de logs, correlación de eventos en tiempo real, alertas, dashboards | Centro de monitoreo |
| **Antivirus Endpoint** | Kaspersky Endpoint Security | Protección de endpoints corporativos, anti-ransomware, EDR | Todas las estaciones de trabajo |

### 8.3 WAF — Web Application Firewall

- **Tecnología:** FortiWeb (versión empresarial).
- **Modo de operación:** Reverse proxy transparente.
- **Funciones de seguridad:**
  - Inspección profunda de tráfico HTTP/HTTPS ( Layer 7).
  - Protección contra inyección SQL (SQLi) con reglas de validación de entrada.
  - Protección contra XSS (Cross-Site Scripting) con sanitización de salida.
  - Control de bots y crawlers maliciosos (lista negra dinámica).
  - Reglas personalizadas por aplicación (SICOM, SIGDI, BI, Portal).
  - Certificados SSL/TLS administrados centralmente (Let's Encrypt / DigiCert).
  - Rate limiting para prevención de abuso de APIs.

### 8.4 Balanceadores y ADC

- **Tecnología:** A10 Thunder ADC (Application Delivery Controller).
- **Funciones:**
  - Balanceo de carga L4 (TCP/UDP) y L7 (HTTP/HTTPS) con algoritmos avanzados (least connections, round-robin, weighted).
  - SSL Offloading: Terminación SSL en el balanceador para reducir carga en servidores backend.
  - Compresión de tráfico (GZIP/Brotli) para mejorar rendimiento.
  - Health checks de servidores backend (HTTP, TCP, ICMP) con eliminación automática de nodos fallidos.
  - Failover automático entre centros de datos (configuración activo-pasivo).

### 8.5 Bases de Datos

- **Motor principal:** Oracle Database (versión Enterprise con opciones de alta disponibilidad).
- **Esquemas principales:**
  - **Datos maestros:** Agentes, plantas, vehículos, productos, catálogos.
  - **Transaccional:** Órdenes de pedido, guías, declaraciones, precios, volúmenes.
  - **Histórico:** Auditoría de cambios, logs de acceso, versiones de documentos, respaldos mensuales.
- **Administradores:** DBA especializados en Oracle (certificados OCP).
- **Backups:**
  - Diarios incrementales (RMAN) con retención de 30 días.
  - Semanales completos (full backup) con retención de 12 semanas.
  - Mensuales archivados con retención de 2 años.
- **Replicación:** Standby físico en modo Data Guard para alta disponibilidad y disaster recovery.

### 8.6 Servidores y Virtualización

- **Plataforma de virtualización:** VMware vSphere (cluster de alta disponibilidad).
- **Servidores de aplicación:** Java EE (JBoss EAP / WebLogic Server) con clustering.
- **Servidores web:** Apache HTTP Server / Nginx (reverse proxy, caché estática).
- **Servidores BPM:** Bizagi Engine (cluster con balanceo interno).
- **Servidores BI:** SQL Server Analysis Services / Power BI Report Server.
- **Servidores de archivos:** NAS/SAN (Network Attached Storage / Storage Area Network) para documentos adjuntos con replicación.

### 8.7 DRP — Disaster Recovery Plan

**Objetivo:** Garantizar la continuidad del negocio en caso de desastre natural, técnico o de seguridad.

**Componentes del DRP:**
- **Procedimiento de Activación DR:** Documento formalizado con pasos detallados, responsables y tiempos.
- **Plan de Pruebas DR:** Ejecución periódica de simulacros (semestral como mínimo).
- **Sitio de Recuperación:** Infraestructura alterna en centro de datos secundario (replicación continua).
- **RPO (Recovery Point Objective):** Máximo tiempo de pérdida de datos aceptable: **< 4 horas**.
- **RTO (Recovery Time Objective):** Tiempo máximo para restaurar operación crítica: **< 8 horas**.
- **Backups en sitio alterno:** Replicación de datos críticos en tiempo real mediante Data Guard.

**Pruebas documentadas:**
- Ejecución de DRP Marzo 2025 (presentación con resultados y hallazgos).
- Validación de restauración de bases de datos (Oracle Data Guard).
- Validación de conectividad de aplicaciones en sitio alterno.
- Validación de disponibilidad de servicios críticos (SICOM, SIGDI, BI).
- Documentación de lecciones aprendidas y planes de mejora post-prueba.

---

## 9. SEGURIDAD DE LA INFORMACIÓN

### 9.1 Ethical Hacking y Pentesting

**Pruebas de seguridad ofensiva realizadas:**

| Tipo de Prueba | Fecha | Alcance | Resultado |
|----------------|-------|---------|-----------|
| **Ethical Hacking Externo** | Mayo 2025 (IDE-0020) | Pruebas de penetración desde Internet | Vulnerabilidades menores identificadas y corregidas |
| **Ethical Hacking Interno** | Mayo 2025 | Movimiento lateral, escalación de privilegios | Segmentación de red validada |
| **Pruebas de Seguridad Web** | Periódico | Aplicaciones web (SICOM, SIGDI, Portal) | Reglas WAF ajustadas |

**Metodología:**
- Reconocimiento de activos expuestos (OSINT, Shodan).
- Escaneo de puertos y servicios (Nmap, Masscan).
- Enumeración de tecnologías y versiones (WhatWeb, Wappalyzer).
- Pruebas de inyección (SQLi, XSS, CSRF, XXE, SSRF).
- Pruebas de autenticación y autorización (fuerza bruta, bypass, elevación de privilegios).
- Pruebas de configuración (SSL/TLS, headers de seguridad, cookies).
- Reporte ejecutivo con riesgos, impacto y recomendaciones.

### 9.2 Análisis de Vulnerabilidades

**Programa de gestión de vulnerabilidades:**

| Actividad | Frecuencia | Responsable |
|-----------|------------|-------------|
| Escaneo de vulnerabilidades (activos internos) | Mensual | Equipo de Seguridad |
| Escaneo de vulnerabilidades (activos externos) | Mensual | Equipo de Seguridad |
| Análisis de vulnerabilidades de software | Trimestral | Analistas de Seguridad |
| Retest de vulnerabilidades corregidas | Bajo demanda | Equipo de Seguridad |
| Informe ejecutivo de vulnerabilidades | Trimestral | Líder de Seguridad |

**Categorías de vulnerabilidades monitoreadas:**
- **Vulnerabilidades de software:** SICOM, Bizagi, sistemas operativos, middleware.
- **Vulnerabilidades de infraestructura:** Firewall, balanceadores, WAF, switches.
- **Vulnerabilidades de configuración:** SSL/TLS, políticas de contraseña, parches pendientes.
- **Vulnerabilidades de código:** Inyección SQL, XSS, CSRF, validación de entrada.

**Clasificación por criticidad:**
- **Crítica:** Explotación inmediata, compromiso total del sistema.
- **Alta:** Explotación probable, acceso a datos sensibles.
- **Media:** Explotación condicional, impacto limitado.
- **Baja:** Explotación difícil, impacto mínimo.

### 9.3 Gestión de Incidentes

- **Registro:** Todos los incidentes de seguridad se documentan en sistema de tickets (Aranda).
- **Clasificación:** Por severidad (Crítico, Alto, Medio, Bajo) y tipo (malware, intrusión, DDoS, filtración).
- **Respuesta:** Protocolo de respuesta a incidentes con tiempos definidos:
  - Crítico: < 1 hora de respuesta inicial.
  - Alto: < 4 horas de respuesta inicial.
  - Medio: < 8 horas de respuesta inicial.
  - Bajo: < 24 horas de respuesta inicial.
- **Escalamiento:** Comité Técnico de Seguridad para incidentes de severidad Crítico o Alto.

### 9.4 Comité de Seguridad

- **Frecuencia:** Sesiones mensuales (tercer martes de cada mes).
- **Participantes:** Líder Técnico, Arquitecto de Software, DBA, Especialistas de Seguridad, Líder Funcional, Representante del MME.
- **Temas tratados:**
  - Estado de vulnerabilidades abiertas y plan de remediación.
  - Incidentes de seguridad del mes (cantidad, severidad, tiempo de resolución).
  - Pruebas de pentesting programadas y resultados.
  - Actualizaciones de parches de seguridad (Microsoft, Oracle, Java, Bizagi).
  - Políticas de acceso y privilegios (revisiones trimestrales).
  - Auditorías de cumplimiento normativo y regulatorio.

---

## 10. OPERACIÓN Y SOPORTE

### 10.1 Mesa de Ayuda (N1 / N2)

**Nivel 1 (N1) — Primer nivel de atención:**
- Atención telefónica y por chat (horario extendido: lunes a viernes 6:00 a 20:00, sábados 8:00 a 14:00).
- Resolución de incidentes simples: reset de contraseñas, orientación en el uso de la plataforma, consulta de estados.
- Clasificación y categorización de tickets para análisis posterior.
- Escalamiento a N2 si no puede resolver en el primer contacto (tiempo máximo: 15 minutos).

**Nivel 2 (N2) — Especializado:**
- Resolución de incidentes técnicos complejos: errores de sistema, bugs, configuraciones.
- Configuración de agentes y plantas (creación, modificación, inhabilitación).
- Gestión de bugs del sistema con coordinación directa con desarrollo.
- Protocolos de atención documentados para cada tipo de incidente.
- Tiempo de respuesta objetivo: < 4 horas (SLA Medio).

### 10.2 Sistema de Tickets (Aranda)

- **Plataforma:** Aranda Service Desk (versión corporativa).
- **Funciones principales:**
  - Creación de tickets por agentes vía call center o portal de autogestión.
  - Asignación automática por categoría (funcional, técnico, seguridad, consulta).
  - Seguimiento de estado: Nuevo → Asignado → En proceso → Resuelto → Cerrado → Cancelado.
  - SLAs definidos por tipo de ticket (Crítico: 4h, Alto: 8h, Medio: 24h, Bajo: 72h).
  - Escalamiento automático por vencimiento de SLA (notificación a supervisor).
  - Base de conocimiento integrada con soluciones documentadas (FAQ, workaround).
- **Métricas:** ~1,900 casos atendidos mensualmente (dato enero 2026).

### 10.3 Centro de Contacto (WolKVOX)

- **Plataforma:** WolKVOX Contact Center (solución IP completa).
- **Canales:** Teléfono (líneas DID), correo electrónico (integración con Aranda).
- **Funciones operativas:**
  - IVR (respuesta de voz interactiva) con menús automatizados.
  - Distribución automática de llamadas (ACD) por habilidad y carga.
  - Grabación de llamadas (100% de interacciones, almacenamiento 90 días).
  - Monitoreo de agentes en tiempo real (supervisores escuchan y asesoran).
  - Reportes de productividad: llamadas atendidas, tiempo promedio, abandono, satisfacción.

### 10.4 Capacitaciones y Formación

**Programas de capacitación activos:**
- **Webinars mensuales:** Sesiones virtuales de 1 hora sobre nuevas funcionalidades y cambios normativos.
- **Microbits:** Videos cortos (2-5 minutos) tutoriales sobre procesos específicos.
- **Preturnos N1:** Capacitación mensual a agentes sobre temas recurrentes de soporte.
- **Gestión del conocimiento:** Documentación actualizada en repositorio central (Confluence / SharePoint).
- **Capacitaciones externas:** Agentes nuevos, entidades gubernamentales, SGI, funcionarios del MME.
- **Módulo de consultas:** Formación específica sobre consultas y reportes.
- **Videos "Aprende SICOM":** Contenido actualizado por tipo de agente (mayorista, minorista, industrial, transportador).

**Material disponible:**
- Manuales de usuario (PDF, versionados).
- Guías paso a paso con capturas de pantalla.
- Videos tutoriales (YouTube / Vimeo privado).
- Instructivos rápidos (tarjetas de referencia).
- Plantillas MME (formatos estándar).
- Evaluaciones trimestrales (certificación de competencias).

---

## 11. INTEGRACIONES Y APIs

### 11.1 Integraciones Principales

| Sistema | Tipo | Protocolo | Función | Frecuencia |
|---------|------|-----------|---------|------------|
| **Bizagi ↔ SICOM Web** | Bidireccional | SOAP / REST | Workflow engine y orquestación de procesos | Tiempo real |
| **SICOM ↔ SIGDI** | Bidireccional | Web Service | Generación y validación de guías digitales | Por evento (despacho) |
| **SICOM ↔ BI** | Unidireccional | ETL / Base de datos | Alimentación de cubos y tableros | Diaria (ETL nocturno) |
| **SICOM ↔ Aranda** | Bidireccional | API / Email | Gestión de tickets y casos de soporte | Tiempo real |
| **SICOM ↔ WolKVOX** | Bidireccional | CTI / API | Integración telefónica para call center | Tiempo real |
| **SICOM ↔ FortiSIEM** | Unidireccional | Syslog / API | Envío de logs de seguridad | Continuo (streaming) |
| **SICOM ↔ FortiWeb** | Bidireccional | HTTP/HTTPS | Protección de tráfico web | Tiempo real |
| **SICOM ↔ Servicios MME** | Bidireccional | Web Service | Validación de datos, consultas regulatorias | Bajo demanda |

### 11.2 APIs Externas y Servicios

- **Validación de NIT:** Conexión con servicios de validación de RUT/NIT de Colombia (DIAN / Registraduría).
- **Normalización de direcciones:** Servicio de geocodificación (Google Maps / OpenStreetMap) para estandarización de direcciones.
- **Validación de correos:** Servicio de verificación de email (MX lookup, validación de dominio).
- **Firma digital:** Servicio de firma electrónica integrado (Proveedor certificado por ONAC).
- **Notificaciones por correo:** SMTP corporativo con plantillas HTML personalizadas por tipo de evento.
- **Servicios de pago:** Integración con plataformas de pago para trámites (si aplica).

---

## 12. GLOSARIO TÉCNICO

| Término | Definición |
|---------|------------|
| **ACPM** | Aceite Combustible Para Motores (diésel corriente) |
| **Agente** | Persona natural o jurídica autorizada por el MME para operar en la cadena de combustibles |
| **Bizagi** | Plataforma de Business Process Management (BPM) usada en SICOM para orquestar procesos |
| **BPM** | Business Process Management — Gestión por Procesos de Negocio |
| **Código SICOM** | Código único de 6 dígitos asignado a cada agente autorizado (2 tipo + 4 consecutivo) |
| **Contingencia** | Plan temporal de abastecimiento ante eventualidades (desastres naturales, paros, etc.) |
| **Cumplido** | Documento que certifica la entrega de combustible en una orden de pedido |
| **DRP** | Disaster Recovery Plan — Plan de Recuperación ante Desastres |
| **EDS** | Estación de Servicio (Automotriz, Aviación, Marítima, Fluvial, Mixta, Privada, Pública) |
| **GC** | Gran Consumidor — Agente que consume grandes volúmenes de combustible |
| **GNCV** | Gas Natural Comprimido Vehicular — Combustible gaseoso gestionado en plataforma separada |
| **MME** | Ministerio de Minas y Energía de Colombia |
| **N1 / N2** | Nivel 1 (soporte básico) / Nivel 2 (soporte especializado) |
| **ONAC** | Organismo Nacional de Acreditación de Colombia |
| **OP** | Orden de Pedido — Solicitud de combustible entre agentes |
| **OPS** | Orden de Pedido Simple — Tipo más común de orden de pedido |
| **SIGDI** | Sistema de Información Guías Digitales de Transporte |
| **SIEM** | Security Information and Event Management — FortiSIEM en el caso del SICOM |
| **SLA** | Service Level Agreement — Acuerdo de Nivel de Servicio |
| **SOAP** | Simple Object Access Protocol — Protocolo de comunicación web services |
| **SOAT** | Seguro Obligatorio de Accidentes de Tránsito |
| **Surtidor** | Dispositivo con registro de volumen y precio del combustible en EDS |
| **WAF** | Web Application Firewall — FortiWeb en el caso del SICOM |

---

## 13. GOBERNANZA DEL PROYECTO Y CONTROL DE CAMBIOS

### 13.1 Comité de Control de Cambios (CCC)

El SICOM opera bajo una estricta gobernanza de cambios mediante el **Comité de Control de Cambios**, conformado por representantes del MME y del equipo técnico de INTERNEXA (operador actual).

**Frecuencia:** Sesiones periódicas (semanales para cambios urgentes, quincenales para evolutivos).

**Participantes oficiales:**
- Representantes del Ministerio de Minas y Energía (MME) — Funcionarios designados.
- Gerente / Director de Proyecto (INTERNEXA).
- Líder Técnico — Arquitectura y decisiones tecnológicas.
- Líder Funcional — Requerimientos y validaciones de negocio.
- Líder BI — Reportes, cubos, calidad del dato.
- Líder Scrum — Agile, sprints, backlog.
- Especialista Base de Datos — Modelo de datos, scripts, tuning.
- Analista de QA — Pruebas, regresión, calidad.
- Especialista Procesos BPM — Modelado Bizagi, reglas de negocio.
- Analistas Funcionales — Documentación, capacitación, soporte.
- Especialista Experiencia de Usuario — UX/UI, usabilidad.

### 13.2 Proceso de Cambios (RFC)

Todas las modificaciones al SICOM se gestionan mediante **Requests for Change (RFC)** con trazabilidad completa:

| Tipo de Cambio | Descripción | Aprobación | Ejemplo |
|----------------|-------------|------------|---------|
| **RFC Estándar** | Cambios planificados de bajo/medio impacto | Comité de Control de Cambios (voto mayoritario) | Ajuste de reporte BI |
| **RFC de Emergencia** | Cambios urgentes por fallos críticos | Aprobación previa por correo del MME + Formalización posterior en comité | Reinicio de servidores, hotfix |
| **Cambios Evolutivos** | Nuevas funcionalidades, mejoras, HU | Comité + Validación UAT + Firma MME | Nuevo módulo de contingencias |
| **Cambios BPM** | Modificaciones a procesos Bizagi | Comité + Equipo BPM + Pruebas de regresión | Ajuste flujo de aprobación |
| **Cambios BI** | Ajustes ETL, cubos, reportes | Comité + Equipo BI + Validación datos | Nuevo cubo de ventas |
| **Cambios SIGDI** | Mejoras al módulo de guías | Comité + Equipo SIGDI + Pruebas funcionales | Ajuste vigencia de guías |

**Ejemplos de RFCs documentados recientemente:**
- **RFC 249:** Ajuste ETL incremental de compras (HU 2194) — Tipo: BI — Diciembre 2025.
- **RFC 250:** Ajuste regla de negocio Orden de Pedido Simple (corrección límite de 20,000 galones) — Tipo: BPM — Diciembre 2025.
- **RFC 2026-269:** Reinicio controlado servidor Nuevo Sicom BPM (emergencia por saturación de memoria) — Tipo: Emergencia — Febrero 2026.
- **RFC 2026-270:** Reinicio controlado de nodos Sicom BPM (emergencia por acumulación de instancias) — Tipo: Emergencia — Febrero 2026.
- **RFC 2026-271:** Depuración de tablas propuestas por fabricante (limpieza de datos históricos) — Tipo: BD — Febrero 2026.
- **RFC 2026-272:** Cambios BPM (ajustes varios a flujos de aprobación) — Tipo: BPM — Febrero 2026.
- **RFC 2026-273:** Cambios evolutivos de BI (nuevos indicadores de calidad) — Tipo: BI — Febrero 2026.
- **RFC 2026-274:** Mejoras en SIGDI (optimización de generación de guías) — Tipo: SIGDI — Febrero 2026.

### 13.3 Políticas del Comité

- **Política de Freezing:** Períodos de congelamiento donde no se ejecutan cambios (cierres mensuales, períodos regulatorios críticos, festivos de alta demanda).
- **Política de Comunicación:** Protocolo de notificación a stakeholders ante cambios (agentes, entes de control, MME) con 48 horas de anticipación mínima.
- **Backup obligatorio:** Antes de cualquier cambio en BD o ETL se debe ejecutar backup completo con retención de 7 días.
- **Validación post-cambio:** BI + Equipo funcional deben validar resultados antes de cerrar el RFC.
- **Ventanas de ejecución:** Programadas para minimizar impacto operativo (generalmente: martes y jueves, 22:00 a 02:00).

---

## 14. MIGRACIÓN A GAS (PROYECTO EN CURSO)

### 14.1 Alcance de la Migración

El proyecto SICOM está expandiendo su alcance para incluir la gestión de **gas natural vehicular (GNV / GNCV)** además de los combustibles líquidos, consolidando en una única plataforma toda la cadena de combustibles del país.

**Roadmap:** Vigencia diciembre 2025 — junio 2026 (en progreso).

### 14.2 Componentes de la Migración

| Componente | Descripción | Estado |
|------------|-------------|--------|
| **Datos Maestros** | Modelo de datos, catálogos para productos de gas (GNV, GNCV) | En diseño |
| **Formularios** | Estructura de entrada, formularios web, reglas de negocio para gas | En desarrollo |
| **Transacciones** | Procesos operativos, validaciones, integraciones WS para gas | En backlog |
| **Consultas y Analítica** | KPIs, paneles, reportes regulatorios y operativos de gas | En backlog |
| **Alistamiento Producción** | Pruebas, despliegue, validación final | Pendiente |

### 14.3 Historias de Usuario (HU) — Backlog Detallado

**Implementadas en UAT (pruebas de usuario):**
- **HU 2045:** Habilitación de módulo de reasignación de casos para usuario principal del agente.
- **HU 2068:** Ajuste proceso de actualización de agentes GC (Gran Consumidor).
- **HU 2184:** Restricción de reportes de ventas en fechas futuras.

**En proceso de Firmas (depuración documental):**
- **HU 2185:** Formulario de actualización de agentes GAS.
- **HU 2349:** Módulo de actualización de agentes GAS.
- **HU 2362:** Actualizar agente campos GAS.
- **HU 2363:** Cargue masivo de vehículos para gas.

**Pendientes de levantar (proyectadas para Q2-Q3 2026):**
- Procesos BPM (7 HU estimadas).
- Formularios y Reglas de Negocio (5 HU estimadas).
- Web Services y Reportes (10 HU estimadas).

**Sin firma en depuración:**
- HU: Control de reporte de ventas EDS balance GAS.
- HU: Registro contrato suministro GNV.
- HU: Modelo de datos maestros GNCV.

### 14.4 Procesos BPM a Migrar (Java GCV / GNCV → BPM Bizagi)

Los procesos actuales de gas que operan en Java legado serán migrados a la plataforma BPM Bizagi para unificar la arquitectura con los combustibles líquidos:

- Registro de agentes GNCV.
- Órdenes de pedido de gas.
- Declaración de información GNCV.
- Control de volúmenes y cupos GNV.
- Guías de transporte para gas (si aplica según normativa).

> **Riesgo identificado:** La migración a gas está en backlog activo. El cierre de plataforma Java legacy debe sincronizarse con la disponibilidad de los nuevos procesos BPM para evitar discontinuidad operativa en el sector GNV.

---

## 15. INDICADORES Y REPORTES DE SERVICIO (ANS)

### 15.1 Acuerdo de Nivel de Servicio (ANS/SLA)

El SICOM opera bajo ANS contractuales medidos mensualmente con reportes formales al MME:

**Indicadores principales:**
- **Disponibilidad del sistema (% uptime):** Medido por monitoreo continuo (FortiSIEM + Nagios/Zabbix).
- **Tiempo de respuesta de aplicación:** Latencia promedio de las transacciones más frecuentes (crear orden, generar guía, consultar estado).
- **Resolución de incidentes (N1 / N2):** Tiempo promedio de resolución por nivel y categoría.
- **Cumplimiento de RFCs programados:** Porcentaje de cambios ejecutados en la ventana planificada.
- **Calidad del dato (% completitud, % exactitud):** Medido por el equipo de BI con metodología propia.

**Reportes documentados:**
- Reporte de ANS Diciembre 2025.
- Reporte de ANS Enero 2026.

### 15.2 Hallazgo Crítico — Disponibilidad Diciembre 2025

Según análisis del reporte de ANS Diciembre 2025:
- **Disponibilidad real:** 99.77%.
- **Disponibilidad comprometida contractualmente:** >99.98%.
- **Gap:** 0.21% por debajo del SLA (equivalente a ~94 minutos de indisponibilidad mensual adicional).

**Causas identificadas:**
- RFCs de emergencia que requirieron reinicios controlados de servidores BPM (memoria saturada, acumulación de instancias).
- Depuración de tablas históricas que consumió recursos de base de datos.
- Ajustes evolutivos en horarios no planificados por urgencia regulatoria.

**Acciones de mitigación:**
- Implementación de monitoreo proactivo de memoria en servidores BPM.
- Automatización de depuración de instancias completadas.
- Revisión de ventanas de mantenimiento para minimizar impacto.

---

## 16. RIESGOS Y CONTROLES

**Matriz de riesgos actualizada periódicamente** con identificación, evaluación y tratamiento:

| Riesgo | Probabilidad | Impacto | Estrategia | Responsable |
|--------|-------------|---------|------------|-------------|
| **Indisponibilidad del sistema** | Media | Crítico | Alta disponibilidad, DRP, monitoreo 24/7 | Líder Técnico |
| **Brecha de seguridad** | Media | Crítico | Pentesting, WAF, SIEM, parches, ethical hacking | Especialista Seguridad |
| **Cambio regulatorio no implementado** | Alta | Alto | Comité de Cambios, backlog ágil, sprints cortos | Líder Funcional |
| **Pérdida de datos** | Baja | Crítico | Backups, replicación, Data Guard, RPO < 4h | DBA |
| **Retraso en migración a gas** | Media | Alto | Roadmap detallado, sprints, pruebas UAT | Gerente Proyecto |
| **Fuga de información confidencial** | Baja | Crítico | Cifrado, control de acceso, auditoría, DLP | Líder Seguridad |
| **Incumplimiento ANS** | Media | Alto | Monitoreo continuo, capacidad, tuning | Líder Técnico |
| **Error humano en operación** | Alta | Medio | Capacitación, checklists, validaciones automáticas | Líder Funcional |

**Controles institucionales:**
- **Comité Técnico de Seguridad:** Sesiones mensuales de revisión de riesgos de seguridad.
- **Comité de Control de Cambios:** Gestión de riesgos asociados a modificaciones del sistema.
- **Pruebas de DRP:** Simulacros semestrales de recuperación ante desastres.
- **Pentesting semestral:** Pruebas de penetración por terceros independientes.
- **Monitoreo continuo:** FortiSIEM 24/7 con alertas automáticas.
- **Auditorías internas:** Trimestrales de procesos, calidad y seguridad.

---

## ANEXO A: HISTORIAL DE RFCs DOCUMENTADOS

| No. | Descripción | Tipo | Fecha | Responsable |
|-----|-------------|------|-------|-------------|
| RFC 249 | Ajuste ETL compras (HU 2194) | BI | Dic 2025 | Equipo BI |
| RFC 250 | Ajuste regla de negocio OPS (20,000 galones) | BPM | Dic 2025 | Equipo BPM |
| RFC 251 | — | — | Dic 2025 | — |
| RFC 2026-269 | Reinicio controlado servidor BPM (emergencia) | Emergencia | Feb 2026 | Líder Técnico |
| RFC 2026-270 | Reinicio controlado nodos BPM (emergencia) | Emergencia | Feb 2026 | Líder Técnico |
| RFC 2026-271 | Depuración tablas fabricante | BD | Feb 2026 | DBA |
| RFC 2026-272 | Cambios BPM (flujos de aprobación) | BPM | Feb 2026 | Equipo BPM |
| RFC 2026-273 | Cambios evolutivos BI (indicadores calidad) | BI | Feb 2026 | Equipo BI |
| RFC 2026-274 | Mejoras SIGDI (optimización guías) | SIGDI | Feb 2026 | Equipo SIGDI |

---

## ANEXO B: CONTROL DE CAMBIOS

| Versión | Fecha | Autor | Cambios |
|---------|-------|-------|---------|
| 1.0 | Mayo 2026 | ZEUS / Análisis Documental | Síntesis inicial del SICOM a partir de 48 documentos técnicos |
| 2.0 | Mayo 2026 | ZEUS / Reformateo Profesional | Reformateo siguiendo estándar de informes ejecutivos del MME. Mejora de fluidez, detalle técnico y estructura visual. Contenido fiel e íntegro al original. |

---

## ANEXO C: ACTIVOS DE INFRAESTRUCTURA SICOM

### IPs Internas (Red SICOM)

| No. | IP | Responsable | Servicio |
|-----|-----|-------------|----------|
| 1 | 192.168.76.131 | SICOM | Servidor aplicación |
| 2 | 192.168.76.132 | SICOM | Servidor aplicación |
| 3 | 192.168.76.247 | SICOM | Base de datos |
| 4 | 192.168.76.147 | SICOM | Servidor web |
| 5 | 192.168.76.200 | SICOM | Balanceador |
| 6 | 192.168.77.136 | SICOM | Servidor BPM |
| 7 | 192.168.76.157 | SICOM | Servidor BI |
| 8 | 192.168.76.145 | SICOM | Servidor de archivos |
| 9 | 192.168.76.146 | SICOM | Servidor de monitoreo |
| 10 | 192.168.76.232 | SICOM | Servidor de backup |
| 11 | 192.168.77.100 | SICOM | WAF |
| 12 | 192.168.77.101 | SICOM | Firewall |
| 13 | 192.168.76.254 | SICOM | Servidor de pruebas |
| 14 | 192.168.76.83 | SICOM | Servidor de desarrollo |
| 15 | 192.168.76.172 | SICOM | Servidor de integración |
| 16 | 192.168.77.160 | SICOM | Servidor de correo |
| 17 | 192.168.76.155 | SICOM | Servidor DNS |
| 18 | 192.168.76.161 | SICOM | Servidor de logs |
| 19 | 192.168.77.153 | SICOM | Servidor de replicación |
| 20 | 192.168.77.150 | SICOM | Servidor de contingencia |
| 21 | 192.168.77.151 | SICOM | Servidor de contingencia |
| 22 | 10.158.2.131 | SICOM | Enlace dedicado |
| 23 | 192.168.76.156 | SICOM | Servidor de administración |
| 24 | 192.168.76.129 | SICOM | Servidor de archivos históricos |
| 25 | 192.168.76.190 | SICOM | Servidor de aplicación secundario |
| 26 | 192.168.77.191 | SICOM | Servidor de base de datos secundario |
| 27 | 10.158.3.110 | SICOM | Enlace dedicado secundario |

**Total dispositivos analizados:** 54

### URLs Externas SICOM

| No. | URL | Servicio | Ambiente |
|-----|-----|----------|----------|
| 1 | https://www.sicom.gov.co/ | Portal Web | Producción |
| 2 | https://wss.sicom.gov.co/sicomdata/ | Web Service | Producción |
| 3 | https://eds.sicom.gov.co/eds/api/v1 | API EDS | Producción |
| 4 | https://bi.sicom.gov.co/OLAP/msmdpump.dll | BI OLAP | Producción |
| 5 | https://bi.sicom.gov.co/OLAP_PRUEBASDLLO/msmdpump.dll | BI Pruebas | Desarrollo |
| 6 | https://bi.sicom.gov.co/OLAP_GCV/msmdpump.dll | BI GCV | Producción |
| 7 | https://bi.sicom.gov.co/OLAP_ENTIDADEXT/msmdpump.dll | BI Entidades | Producción |
| 8 | https://bi.sicom.gov.co/OLAP_EXTERNO/msmdpump.dll | BI Externo | Producción |
| 9 | https://bi.sicom.gov.co/OLAP_PRUEBAS/msmdpump.dll | BI Pruebas | Pruebas |
| 10 | https://pruebabi.sicom.gov.co/ | Pruebas BI | Pruebas |
| 11 | https://portal.sicom.gov.co/SICOM | Portal | Producción |
| 12 | https://mesadeservicio.sicom.gov.co//USDKv8//#!/login/ | Mesa de Servicio | Producción |
| 13 | https://liquidos.sicom.gov.co/sicom/identificacionAction.do | Líquidos | Producción |
| 14 | https://gncv.sicom.gov.co/login | GNCV | Producción |
| 15 | https://bwss.sicom.gov.co/sicomdata/ | Web Service Backup | Contingencia |
| 16 | https://aprendesicom.sicom.gov.co/login/index.php | Capacitaciones | Producción |
| 17 | https://git.sicom.gov.co/users/sign_in | GitLab | Desarrollo |
| 18 | https://sigdi.sicom.gov.co/guias/ | SIGDI | Producción |
| 19 | https://pru.api.sicom.gov.co | API Pruebas | Pruebas |
| 20 | https://api.sicom.gov.co | API Producción | Producción |
| 21 | https://cubos.sicom.gov.co | Cubos BI | Producción |
| 22 | https://moduloconsultas.sicom.gov.co/Login | Consultas | Producción |
| 23 | https://sigdipruebas.sicom.gov.co/ | SIGDI Pruebas | Pruebas |
| 24 | https://uatsicomconsultas.sicom.gov.co/ | UAT Consultas | Pruebas |
| 25 | https://wsp.sicom.gov.co/ | Web Service Public | Producción |
| 26 | https://uatbpm.sicom.gov.co/UAT_TEST/ | UAT BPM | Pruebas |
| 27 | https://uatbpm.sicom.gov.co/ws/sicomdata | UAT BPM WS | Pruebas |

---

## ANEXO D: PROCEDIMIENTO DE GESTIÓN DE VULNERABILIDADES

**Responsable:** INTERNEXA S.A. (Operador del SICOM)

| Paso | Actividad | Descripción | Entregable |
|------|-----------|-------------|------------|
| 1 | Escaneo | Realizar escaneo a todos los dispositivos en la línea base mediante herramienta de análisis de vulnerabilidades según política establecida | Reporte de escaneo crudo |
| 2 | Evaluación | Evaluar y analizar resultados obtenidos y clasificar según criticidad (Crítica, Alta, Media, Baja) | Matriz de vulnerabilidades |
| 3 | Plan de Remediación | Generar plan de mitigación con fechas y responsables. En caso necesario escalar al proveedor/fabricante para encontrar solución de cierre | Plan de remediación |
| 4 | Retest | Realizar segundo escaneo para verificar cierre de vulnerabilidades reportadas | Reporte de retest |
| 5 | Verificación | Verificar resultados del Retest. Si no se cerraron, analizar si se requiere nuevo plan de mitigación o aceptación del riesgo | Acta de verificación |
| 6 | Informe Técnico | Generar informe técnico con detalles del análisis, evidencias y recomendaciones | Informe técnico PDF |
| 7 | Análisis de Riesgo | Efectuar análisis de riesgo para estimar probabilidad de materialización de evento no deseado | Matriz de riesgos |
| 8 | Informe Ejecutivo | Generar y presentar informe ejecutivo en formato Word para alta dirección y MME | Informe ejecutivo DOCX |

---

## ANEXO E: MÓDULO DE CONTINGENCIAS DE ABASTECIMIENTO

**Historia de Usuario:** HU-1531 — Configuración de Plantas Para Contingencias

**Objetivo:** Crear un módulo que permita realizar cambios temporales en los planes de abastecimiento habituales de una región o regiones específicas del país, garantizando que no se interrumpa el abastecimiento de combustible ante eventualidades (desastres naturales, paros, bloqueos de vías, emergencias).

**Reglas de Negocio Detalladas:**
- Se instancia un caso para cada mayorista que opere en la zona de contingencia.
- El módulo cuenta con filtros: Departamento, Municipio, Mayorista, Plantas asociadas.
- Los mayoristas mostrados son aquellos con contrato de suministro con EDS activas (Automotrices y Fluviales) del Departamento/Municipio seleccionado.
- Se presenta una colección de plantas asociadas al mayorista para desactivar la actual y activar la de contingencia.
- **Excepciones por ubicación:** En municipios donde EDS del casco urbano tienen plan diferente a las de zona rural, se maneja un check de excepción que abre colección de EDS del municipio y plantas asociadas.
- A las EDS solo se les configura **una planta de contingencia**, única visible al momento de realizar OPS.
- **Temporizador de contingencia:** Fecha de inicio + cantidad de días = fecha fin automática (hasta las 23:59 horas). La fecha fin no es editable manualmente.
- En caso de prórroga: la cantidad total de días debe ser superior a la contingencia inicial (ej: si fueron 10 días, la actualización debe ser 11 o más).
- Al terminar la contingencia, se restablece automáticamente la configuración de plantas del plan de abastecimiento definido originalmente.
- Si ingresa una EDS nueva durante el periodo de contingencia, el operador SICOM debe instanciar un caso para activarle la planta de contingencia.
- La actualización de casos instanciados permite ampliar días de contingencia mostrando el total acumulado.
- Se puede deshabilitar la contingencia antes del tiempo configurado mediante botón de deshabilitar (con confirmación y motivo).

**Criterios de Aceptación:**
- El usuario operador de SICOM puede configurar, activar y/o desactivar plantas de manera temporal para activar planes de contingencia de abastecimiento.
- El sistema controla automáticamente el tiempo de contingencia y restablece la configuración original al vencimiento.

---

## ANEXO F: DATASET DE CASOS ARANDA — ENERO 2026

**Total de casos analizados:** ~1,900 registros

**Categorías principales de incidentes reportados:**
- FALLA INGRESO A SIGDI (códigos de verificación no llegan, errores de autenticación).
- FALLA INGRESO A SICOM LÍQUIDOS (usuarios bloqueados, contraseñas vencidas).
- FALLA TRANSMISIÓN DATOS WEB SERVICE SICOM LÍQUIDOS (errores de comunicación entre sistemas).
- FALLA INGRESO A SICOM GNCV (problemas de autenticación en plataforma de gas).
- FALLA TRANSMISIÓN DATOS WEB SERVICE SICOM GNCV (integración GNCV con sistemas externos).

**Estados de casos:**
- **CANCELADO (Mayoría):** Casos mal registrados que se derivan a portal de Autogestión o que el agente resuelve por su cuenta.
- **CERRADO:** Casos resueltos por Grupo de Análisis SICOM (N2) con solución documentada.

**SLA aplicado:** MEDIO 24H (Tiempo máximo de atención: 24 horas hábiles).

**Canales de registro:**
- Portal Cliente (principal, 70% de casos).
- Call Center telefónico (30% de casos).

**Grupos de resolución:**
- **CALL CENTER (N1):** Primer nivel, atención telefónica, registro y clasificación.
- **INTERNEXA FUNCIONAL (N2):** Segundo nivel, análisis técnico, configuración, bugs, coordinación con desarrollo.

**Ejemplo de caso típico detallado:**
- **Caso 3562:** FALLA INGRESO A SIGDI — No llegaban códigos de verificación a correos electrónicos de plantas.
- **Fecha registro:** 2026-01-22.
- **Fecha cierre:** 2026-01-28 (6 días de atención, dentro del SLA Medio 24H acumulado).
- **Grupo resolutor:** INTERNEXA FUNCIONAL (N2).
- **Solución aplicada:** Ajuste en el sistema de notificaciones de correo para estabilizar operación y acceso en la plataforma. Reconfiguración de servidor SMTP y validación de listas de distribución.
- **Lección aprendida:** Los códigos de verificación de SIGDI dependen de la disponibilidad del servicio de correo. Se recomienda monitoreo proactivo de cola de correos.

---

## ANEXO G: SOLUCIÓN WORKAROUND MÓDULO ENCUESTAS

**Documento original:** Arq. Marcelo Tunarosa | ITX | Noviembre 2024

**Contexto:** Necesidad de publicar una encuesta para agentes minoristas (códigos 61, 62, 63) en el Nuevo SICOM BPM. La encuesta es obligatoria para diligenciar antes de acceder al sistema.

**Arquitectura de la solución:**
- **Ambiente Productivo:** Encuesta integrada en flujo BPM (evento de inicio obligatorio).
- **Ambiente UAT:** Pruebas de integración con usuarios de prueba.

**Solución General (Especialista BPM – Bizagi):**
- Colección de Postman para consumo de la API nativa de Bizagi (creación de instancias, consulta de estado, registro de respuestas).

**Solución Detallada (Especialista JAVA):**
- **Tabla:** `MAE_TBL_CODIGOVERIFICACION` — Almacena: ID, fecha generación, código SICOM, usuario, código verificación (6 dígitos), fecha expiración.
- **Tabla:** `MAE_TBL_ENCUESTA` — Almacena: ID, fecha registro, código SICOM, usuario, respuesta, valor, IP origen, sesión.
- **Front-end:** Formulario de encuesta con validación de campos obligatorios, listas desplegables y campos de texto.
- **Correo:** Plantilla HTML de notificación con código de verificación único, enviado al correo registrado del agente.
- **Integración:** La encuesta se presenta como tarea inicial en el flujo BPM antes de mostrar el home del agente.

---

## ANEXO H: LISTADO GENERAL DE REQUERIMIENTOS SICOM LÍQUIDOS

**Documento fuente:** Listado General de Requerimientos SICOM Líquidos — MME (Octubre 2025)

**Resumen ejecutivo de Historias de Usuario:**

| NÚMERO | NOMBRE | SISTEMA | ESTADO | ORIGEN | FUNCIONAL MME |
|--------|--------|---------|--------|--------|---------------|
| 344 | Validación Vehículos Comercializadores Industriales y EDS de Zona de Frontera | NUEVO SICOM LIQUIDOS | EN PRODUCCIÓN | Migración Java a Bizagi | DIANA RUIZ |
| 360 | Actualización de Cupos OPAI proceso ACOP | NUEVO SICOM LIQUIDOS | SIN FIRMA | Evolutivos / Rediseños | ANGIE KATHERINE MEJIA GONZALEZ |
| 1206 | Creación Jobs y Campos Comercializador Industrial | NUEVO SICOM LIQUIDOS | EN BACKLOG | Migración Java a Bizagi | PABLO TORRES |
| 1212 | Ajustes Comercializador Industrial – Excepciones y Direcciones Cliente Final | NUEVO SICOM LIQUIDOS | EN DESARROLLO | Migración Java a Bizagi | PABLO TORRES |
| 1993 | Cierre, Anulación y Rechazo Guía de OPP | SIGDI | EN DESARROLLO | Evolutivos / Rediseños | NICOLAS LEIVA |
| 1531 | Proceso de Configuración Contingencias (Plantas) | NUEVO SICOM LIQUIDOS | CERTIFICACION FUNCIONAL | Evolutivos / Rediseños | MAIDA EUNISE HERRERA |

**Estados de HU y su significado operativo:**
- **EN PRODUCCIÓN:** Desplegadas, operativas y disponibles para los agentes.
- **EN DESARROLLO:** En construcción activa por el equipo técnico. No disponibles para uso.
- **EN BACKLOG:** Pendientes de iniciar. Priorizadas pero sin asignación de sprint.
- **SIN FIRMA:** Requieren aprobación formal del MME (firma de funcionario designado).
- **PENDIENTE PASO A PRODUCCIÓN:** En pruebas finales (QA + UAT). Listas para despliegue previa aprobación.
- **CERTIFICACION FUNCIONAL:** En pruebas de certificación funcional con el MME.

**Funcionales MME asignados (equipo de requerimientos):**
- DIANA RUIZ
- ANGIE KATHERINE MEJIA GONZALEZ
- PABLO TORRES
- NICOLAS LEIVA
- MAIDA EUNISE HERRERA
- EMMA JIMENEZ
- JHON JAIRO
- NELLY RIOS
- NICOLAS CALDERÓN ACHURY
- DEYSI RODRIGUEZ BERRIO (Grupo Precios)
- HECTOR EMILIO MORENO
- JOSE DANIEL TULCAN

---

**Documento generado por análisis automatizado de la carpeta documental SICOM.**
**Fuentes principales:** M-126 (Procesos de Apoyo V6), M-127 (Procesos Core V5), M-128 (Procesos de Control V5), Manuales SIGDI (M-25, M-87, M-122, M-128, M-133), Guías SICOM, Informes de Seguridad (IDE-0020, Matriz Vulnerabilidades), Documentación de Infraestructura (FortiSIEM, Kaspersky, P-11, P-12), DRP (Procedimiento Activación DR, Pruebas DRP Marzo 2025), Call Center (G-01 Guía Aranda, DATA CASOS Aranda Enero 2026), BI/Calidad (Reportes ANS, Cubos), Desarrollo (Cronograma Vigencia 3 2025, Roadmap Migración Gas, HU), Gobernanza (Actas Comité Control Cambios), y ~40 documentos adicionales.

---

> **ZEUS** — Sistema de Inteligencia Empresarial INNOVADATACO  
> *Análisis documental profundo — SICOM Ministerio de Minas y Energía*  
> *Reformateo profesional v2.0 — Fiel e íntegro al contenido original*
