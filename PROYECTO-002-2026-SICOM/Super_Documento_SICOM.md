# SICOM — SUPER DOCUMENTO TÉCNICO Y FUNCIONAL
**Sistema de Información de Combustibles Líquidos Derivados del Petróleo**
**Ministerio de Minas y Energía — Colombia**

---

**Versión:** 1.0 (Síntesis documental)  
**Fecha de análisis:** Mayo 2026  
**Fuente:** Carpeta documental SICOM (Google Drive) — 48 documentos técnicos analizados  
**Alcance:** Arquitectura de procesos, funcionalidades, módulos, actores, infraestructura, seguridad y operación

---

## TABLA DE CONTENIDOS

1. [Resumen Ejecutivo](#1-resumen-ejecutivo)
2. [Visión General del SICOM](#2-visión-general-del-sicom)
3. [Marco Normativo](#3-marco-normativo)
4. [Arquitectura de Procesos](#4-arquitectura-de-procesos)
   - 4.1 Macroproceso de Combustibles Líquidos
   - 4.2 Procesos de Apoyo
   - 4.3 Procesos Principales (Core)
   - 4.4 Procesos de Control
5. [Módulos del Sistema](#5-módulos-del-sistema)
   - 5.1 Portal Web SICOM (Home)
   - 5.2 SIGDI — Sistema de Información Guías Digitales de Transporte
   - 5.3 BPM Bizagi
   - 5.4 BI — Business Intelligence / Calidad del Dato
   - 5.5 Call Center / Mesa de Ayuda
   - 5.6 Portal de Autogestión
6. [Actores, Roles y Responsables](#6-actores-roles-y-responsables)
   - 6.1 Agentes de la Cadena
   - 6.2 Roles del Ministerio (MME)
   - 6.3 Equipo Operativo SICOM
7. [Funcionalidades Detalladas](#7-funcionalidades-detalladas)
   - 7.1 Gestión de Agentes
   - 7.2 Gestión de Plantas
   - 7.3 Gestión de Vehículos
   - 7.4 Órdenes de Pedido
   - 7.5 Guías Digitales (SIGDI)
   - 7.6 Monitoreo y Cumplidos
   - 7.7 Precios y Volúmenes
   - 7.8 Declaración de Información
   - 7.9 Gestión de Usuarios y Perfiles
8. [Infraestructura Tecnológica](#8-infraestructura-tecnológica)
   - 8.1 Arquitectura de Red
   - 8.2 Seguridad Perimetral
   - 8.3 WAF — Web Application Firewall
   - 8.4 Balanceadores y ADC
   - 8.5 Bases de Datos
   - 8.6 Servidores y Virtualización
   - 8.7 DRP — Disaster Recovery Plan
9. [Seguridad de la Información](#9-seguridad-de-la-información)
   - 9.1 Ethical Hacking y Pentesting
   - 9.2 Análisis de Vulnerabilidades
   - 9.3 Gestión de Incidentes
   - 9.4 Comité de Seguridad
10. [Operación y Soporte](#10-operación-y-soporte)
    - 10.1 Mesa de Ayuda (N1 / N2)
    - 10.2 Sistema de Tickets (Aranda)
    - 10.3 Centro de Contacto (WolKVOX)
    - 10.4 Capacitaciones y Formación
11. [Integraciones y APIs](#11-integraciones-y-apis)
12. [Integraciones y APIs](#11-integraciones-y-apis)
13. [Gobernanza del Proyecto y Control de Cambios](#13-gobernanza-del-proyecto-y-control-de-cambios)
    - 13.1 Comité de Control de Cambios
    - 13.2 Proceso de Cambios (RFC)
    - 13.3 Políticas del Comité
14. [Migración a Gas](#14-migración-a-gas)
    - 14.1 Alcance de la Migración
    - 14.2 Componentes de la Migración
    - 14.3 Historias de Usuario (HU)
    - 14.4 Procesos BPM a Migrar
15. [Indicadores y Reportes de Servicio (ANS)](#15-indicadores-y-reportes-de-servicio-ans)
16. [Riesgos y Controles](#16-riesgos-y-controles)
17. [Glosario](#12-glosario)
18. [Anexo A: Historial de RFCs](#anexo-a-historial-de-rfcs-documentados)
19. [Anexo B: Control de Cambios](#anexo-b-control-de-cambios)

---

## 1. RESUMEN EJECUTIVO

El **SICOM** (Sistema de Información de Combustibles Líquidos Derivados del Petróleo) es la plataforma tecnológica del Ministerio de Minas y Energía de Colombia encargada de organizar, controlar y sistematizar la comercialización, distribución, transporte y almacenamiento de combustibles líquidos derivados del petróleo, alcohol carburante y biodiesel a nivel nacional.

El sistema integra a todos los agentes de la cadena de distribución en una única plataforma de información, gestionando desde la creación de agentes y sus plantas, hasta la generación de órdenes de pedido, guías digitales de transporte, monitoreo de vehículos, registro de precios, control de volúmenes y declaración de información operativa.

El SICOM está construido sobre una arquitectura BPM (Business Process Management) usando **Bizagi**, con múltiples módulos integrados: portal web, SIGDI (guías digitales), BI (Business Intelligence), call center, portal de autogestión, y está respaldado por una infraestructura de alta disponibilidad con medidas de seguridad de nivel empresarial.

---

## 2. VISIÓN GENERAL DEL SICOM

### 2.1 Definición

> **SICOM** es el Sistema de Información de la Cadena de Distribución de Combustibles Líquidos Derivados del Petróleo del Ministerio de Minas y Energía, el cual integra a los agentes de la cadena a nivel nacional en un solo sistema de información y mediante el cual se organiza, controla y sistematiza la comercialización, distribución, transporte y almacenamiento de combustibles líquidos derivados del petróleo, alcohol carburante y biodiesel.

### 2.2 Tipos de Combustibles Gestionados

- Gasolina motor (extra, corriente, oxigenada)
- Combustibles de aviación (avgas, jet fuel)
- Queroseno
- Diésel extra / diésel de bajo azufre
- Diésel corriente (ACPM)
- Diésel marino / fluvial
- Combustible para quemadores industriales (fuel oil / combustóleo)
- Alcohol carburante
- Biodiesel

### 2.3 Tipos de Agentes de la Cadena

| Tipo de Agente | Descripción |
|----------------|-------------|
| **Refinador** | Procesa crudo para producir combustibles |
| **Importador** | Importa combustibles al país |
| **Almacenador** | Opera instalaciones de almacenamiento |
| **Distribuidor Mayorista** | Distribuye al por mayor mediante plantas de abastecimiento |
| **Transportador** | Transporta combustibles |
| **Distribuidor Minorista** | Opera estaciones de servicio (EDS) o comercializadores industriales |
| **Gran Consumidor** | Consume grandes volúmenes de combustible |

### 2.4 Tipos de Estaciones de Servicio (EDS)

- **EDS Automotriz**: Surtidores fijos para vehículos automotores
- **EDS Aviación**: Combustibles para aeronaves
- **EDS Marítima**: Combustibles para embarcaciones
- **EDS Fluvial**: Combustibles para transporte fluvial
- **EDS Mixta**: Combustibles líquidos y gaseosos
- **EDS Privada**: Exclusiva para flota propia de una empresa
- **EDS Pública**: Abierta al público general
- **EDS Dedicada**: Solo un tipo de combustible

### 2.5 Plataformas del SICOM

| Plataforma | URL / Acceso | Función |
|------------|-------------|---------|
| **Portal Web SICOM (Home)** | https://www.sicom.gov.co | Portal principal de gestión |
| **Nuevo SICOM** | Plataforma evolutiva del sistema | Optimización UX y nuevos módulos |
| **SIGDI** | https://sigdi.sicom.gov.co/guias/ | Guías digitales de transporte |
| **Portal de Autogestión** | Integrado en SICOM | Registro de casos y solicitudes |
| **Bizagi (BPM)** | Motor de procesos | Workflow engine |

---

## 3. MARCO NORMATIVO

El SICOM opera bajo el siguiente marco normativo principal:

| Norma | Descripción |
|-------|-------------|
| **Decreto 1073 de 2015** | Decreto Único del Sector Minas y Energía. Normativa principal que regula el SICOM. |
| **Decreto 1135 de 2022** | Modificaciones y actualizaciones al régimen de combustibles. |
| **Resolución SIGDI 40483 de 2023** | Regula el Sistema de Información de Guías Digitales de Transporte. |
| **Resolución 0242 de 2019** | Marco regulatorio de operación. |
| **Decreto 1120 de 2021** | Disposiciones sobre comercialización de combustibles. |

---

## 4. ARQUITECTURA DE PROCESOS

El SICOM está diseñado sobre una arquitectura de procesos BPMN (Business Process Model and Notation), implementada en la plataforma **Bizagi**. Los procesos se dividen en tres grandes grupos:

### 4.1 Macroproceso de Combustibles Líquidos

El macroproceso describe el flujo end-to-end de la cadena de suministro de combustibles líquidos, desde la creación de agentes hasta la generación de órdenes de pedido, despacho, transporte y cierre.

```
[Agente] → [Creación/Validación] → [Orden de Pedido] → [Despacho] → [Transporte/SIGDI] → [Cierre/Cumplido] → [Monitoreo]
```

### 4.2 Procesos de Apoyo (M-126)

Los procesos de apoyo alimentan y soportan los procesos principales de generación de órdenes de pedido.

| Proceso | Descripción | Responsable |
|---------|-------------|-------------|
| **Crear Agente** | Registro de nuevo agente en el portal web. Incluye validación por dos roles del MME. Genera código SICOM de 6 dígitos. | Agente + MME |
| **Validar Información** | Subproceso reusable de validación de datos por funcionarios del MME (Responsable Funcional + Coordinador). | MME |
| **Actualizar Agente** | Modificación de datos del agente ya existente. Incluye subproceso de validación. | Agente + MME |
| **Gestión de Usuarios** | Creación, modificación, inactivación de usuarios principales y secundarios por agente. | Agente + Administrador |
| **Gestión de Acuerdos y Productos** | Configuración de acuerdos comerciales y catálogo de productos entre agentes. | Agente |
| **Gestión de Plantas** | Creación y actualización de plantas de abastecimiento asociadas a cada agente. Incluye EDS automotriz, aviación, marítima, fluvial, industrial. | Agente + MME |
| **Gestión de Vehículos** | Registro de vehículos autorizados para transporte de combustibles. | Agente |
| **Validación Documentos Vehículo** | Verificación de SOAT, pólizas, revisión técnico-mecánica, licencias de conducción. | Sistema (Jobs automáticos) |
| **Gestión de Mezclas** | Configuración de mezclas de combustibles (gasolina corriente oxigenada, extra oxigenada). | Agente + MME |

#### Reglas de Negocio Clave — Crear Agente

- No se permite crear una razón social con el mismo NIT/RUT existente.
- Un NIT puede tener múltiples códigos SICOM asociados.
- El código SICOM tiene 6 dígitos: 2 primeros = tipo de agente, 4 últimos = consecutivo.
- Las direcciones se normalizan automáticamente.
- Correos electrónicos y páginas web se validan automáticamente.
- Si la EDS es operada por propietario, los datos son no editables; si es arrendatario, permite edición.
- Solo se permite adjuntar documentos en PDF.
- Duración de validación: 60 días.

### 4.3 Procesos Principales / Core (M-127)

Los procesos principales gestionan la generación y ejecución de órdenes de pedido.

| Proceso | Descripción | Actores |
|---------|-------------|---------|
| **Orden de Pedido Simple (OPS)** | Tipo más común. Permite solicitar múltiples productos. Genera cumplido si aplica. Posibilidad de devoluciones en aceptación, despacho y cierre. | Agente Solicitante → Agente Proveedor → Puesto de Control |
| **Orden de Pedido Programada** | Órdenes con programación temporal recurrente. | Agente |
| **Orden de Pedido Anticipada Individual** | Solicitud anticipada por un agente individual. | Agente |
| **Orden de Pedido Anticipada por Nominación** | Solicitud anticipada con nominación de volúmenes. | Agente + MME |
| **Orden de Pedido de Transferencia** | Transferencia de combustibles entre instalaciones del mismo agente. | Agente |
| **Gestión de Solicitudes OP Programada** | Administración de solicitudes de órdenes programadas. | Agente + MME |
| **Gestión de Despachos OP Anticipada Individual** | Control de despachos para órdenes anticipadas individuales. | Agente Proveedor |
| **Gestión de Despachos OP Anticipada Nominal** | Control de despachos para órdenes anticipadas por nominación. | Agente Proveedor |
| **Cargue Masivo de Entregas** | Proceso batch para cargar múltiples entregas simultáneamente. | Agente + Sistema |
| **Actualizar Órdenes de Pedido** | Modificación de órdenes existentes. | Agente |
| **Recepción Guía Digital** | Subproceso de recepción y validación de guías digitales de transporte. | Agente + SIGDI |
| **Monitoreo de Vehículos** | Subproceso de seguimiento de vehículos en tránsito. | Sistema + Agente |

#### Flujo de Orden de Pedido Simple

```
1. Agente Solicitante CREA la orden de pedido
2. Sistema GENERA y envía resultado del cumplido (si aplica)
3. Sistema CARGA vehículos del proveedor
4. Agente Proveedor ACEPTA la orden
   → Si rechaza: notifica rechazo, fin del proceso
5. Agente Proveedor DESPACHA la orden
   → Si rechaza: notifica rechazo, fin del proceso
6. Subproceso: RECEPCIÓN GUÍA DIGITAL
7. Subproceso: MONITOREO VEHÍCULOS
8. Puesto de Control VALIDA Y REGISTRA cumplido
9. Agente Solicitante DILIGENCIA cumplimiento de requisitos
10. Agente/Cierre CIERRA la orden de pedido
```

#### Estados de una Orden de Pedido

- Solicitud
- Aceptada
- Despachada
- En tránsito (monitoreo)
- Cumplido validado
- Cerrada
- Rechazada
- Anulada

### 4.4 Procesos de Control (M-128)

Los procesos de control permiten al Ministerio regular y supervisar la operación de los agentes.

| Proceso | Descripción | Responsable |
|---------|-------------|-------------|
| **Inhabilitar Agente** | Desactivación total de agente, plantas y usuarios asociados. | Operador Líder MME |
| **Notificar Vigencia Documentos** | Alertas automáticas por vencimiento de documentos de agentes/plantas/vehículos. | Sistema (Jobs) |
| **Registro de Precios** | Ingreso de precios de combustibles por agentes. | Agente |
| **Asignación Precios Mínimos y Máximos** | Fijación de rangos de precios por parte del MME. | MME |
| **Asignación Volumen Máximo** | Definición de cupos máximos de compra por agente/producto. | MME |
| **Gestión Solicitudes Volumen Máximo** | Administración de solicitudes de incremento de cupos. | Agente + MME |
| **Asignación/Reasignación Volúmenes Máximos** | Reasignación de cupos entre agentes o productos. | MME |
| **Declaración de Información** | Reporte periódico de operaciones por parte de los agentes. | Agente |
| **Cargue Masivo Declaración** | Carga batch de declaraciones de información. | Agente |
| **Actualizar Declaración** | Corrección de declaraciones enviadas. | Agente |
| **Bloqueo/Desbloqueo Agentes** | Control de acceso temporal por incumplimiento o vencimiento de documentos. | Sistema (Jobs automáticos) + Operador Líder |

#### Jobs Automáticos de Control (Cron Jobs)

| Job | Función | Frecuencia |
|-----|---------|------------|
| **JobAlerVencPoliVehi** | Alerta vencimiento póliza vehicular | Diaria |
| **JobValDocsAg** | Validación documentos agente | Diaria |
| **JobValDocsPlan** | Validación documentos planta | Diaria |

---

## 5. MÓDULOS DEL SISTEMA

### 5.1 Portal Web SICOM (Home)

Es el punto de entrada principal para todos los agentes de la cadena.

**Funcionalidades:**
- Autenticación con usuario y contraseña
- Registro de nuevos agentes (solicitud de creación)
- Gestión de órdenes de pedido
- Consulta de estados de agente
- Actualización de documentos vencidos
- Asociación de vehículos
- Creación de usuarios secundarios
- Inactivación de usuarios secundarios
- Registro de precios
- Declaración de información
- Portal de autogestión para radicación de casos

### 5.2 SIGDI — Sistema de Información Guías Digitales de Transporte

SIGDI es el módulo encargado de la generación de guías digitales de transporte para las órdenes de pedido despachadas en SICOM.

**Funcionalidades principales:**

| Función | Descripción |
|---------|-------------|
| **Generación de Guías** | Creación automática de guía digital a partir de orden de pedido en estado "despachado" |
| **Código de Autorización** | Número de 15 dígitos generado automáticamente por SICOM para cada orden |
| **Número de Guía** | Consecutivo de 16 dígitos (inicia con 6 dígitos del código SICOM) |
| **Verificación de Firma** | Validación de autenticidad mediante código enviado por correo electrónico |
| **Registro de Manifiesto** | Ingreso de precintos, código de manifiesto y empresa transportadora |
| **Previsualización** | Vista previa de guía en PDF con marca de agua "diligenciamiento" (sin vigencia) |
| **Firma Digital** | Firma electrónica de la guía con fecha/hora de salida, vigencia, marca de agua "vigente" |
| **Histórico de Guías** | Registro de todas las guías generadas por día |
| **Reporte de Novedades** | Notificación de ajustes realizados en SICOM sobre guías vigentes |
| **Actualización de Firma** | Carga de firma en formato imagen (PNG, JPEG, JPG) o dibujo manual |
| **Aprobación de Firma** | El administrador del sistema aprueba las firmas cargadas |

**Flujo SIGDI:**

```
1. Orden de pedido en SICOM → Estado "Despachado"
2. Planta ingresa a SIGDI con usuario/clave de SICOM
3. Verificación de firma (código por correo)
4. Ingreso de código de autorización (15 dígitos)
5. Sistema carga datos de la orden (NO EDITABLES)
6. Registro de manifiesto y precintos
7. Registro de guía → Botones "Previsualizar" y "Firmar"
8. Previsualización: PDF sin firma, sin vigencia, marca de agua "diligenciamiento"
9. Firma: Sistema valida actualizaciones en SICOM, firma digital, genera guía vigente
10. Guía firmada: PDF con firma, fecha/hora salida, vigencia (horas), marca "vigente"
11. Correo electrónico de confirmación al agente
12. Histórico disponible para descarga e impresión
```

**Nota clave:** Los datos de la guía NO son editables en SIGDI. Si requieren cambio, se debe ajustar la orden de pedido en SICOM y devolverla al estado "despachado".

### 5.3 BPM Bizagi

Bizagi es el motor de workflows que orquesta todos los procesos del SICOM.

**Características:**
- Procesos modelados en BPMN 2.0
- Subprocesos reusables (ej: "Validar Información")
- Tareas de servicio (scripts automáticos)
- Tareas de usuario (asignación por roles)
- Compuertas exclusivas de divergencia
- Eventos de inicio por mensaje (SOAP)
- Eventos intermedios de anulación y devolución
- Duraciones configurables por actividad
- Notificaciones automáticas por correo electrónico

### 5.4 BI — Business Intelligence / Calidad del Dato

El módulo de BI proporciona inteligencia de negocio y control de calidad del dato.

**Componentes:**
- Cubos OLAP para análisis multidimensional
- Tableros de control (dashboards)
- Reportes de calidad del dato
- Seguimiento quincenal de calidad
- Matrices de competencias y seguimiento
- Informes trimestrales al MME

**Tipos de reportes:**
- Calidad del dato por agente
- Calidad del dato por proceso
- Estadísticas de cumplimiento
- Alertas de inconsistencias

### 5.5 Call Center / Mesa de Ayuda

**Infraestructura:**
- **Plataforma:** WolKVOX (centro de contacto)
- **Sistema de tickets:** Aranda (gestión de casos)
- **Niveles de atención:** N1 (primer nivel) / N2 (especializado)

**Funciones:**
- Atención telefónica a agentes de la cadena
- Gestión de casos y tickets de soporte
- Protocolos de atención por tipo de incidente
- Grabación de llamadas (registro mensual)
- Informes mensuales de casos atendidos
- Escalamiento a N2 para casos técnicos complejos

### 5.6 Portal de Autogestión

Plataforma para que los agentes gestionen sus propios casos sin intervención del call center.

**Funciones:**
- Radicación de casos
- Seguimiento de solicitudes
- Consulta de estado de trámites
- Actualización de datos de planta para SIGDI
- Registro de correo electrónico de planta (requerido para SIGDI)

---

## 6. ACTORES, ROLES Y RESPONSABLES

### 6.1 Agentes de la Cadena

| Rol | Función en SICOM |
|-----|-----------------|
| **Agente Solicitante** | Crea órdenes de pedido, solicita productos |
| **Agente Proveedor** | Acepta y despacha órdenes de pedido |
| **Puesto de Control** | Valida y registra cumplidos de órdenes |
| **Distribuidor Mayorista** | Opera plantas de abastecimiento |
| **Distribuidor Minorista** | Opera estaciones de servicio (EDS) |
| **Gran Consumidor** | Solicita volúmenes mayores |
| **Transportador** | Registra vehículos y manifiestos |

### 6.2 Roles del Ministerio (MME)

| Rol | Función |
|-----|---------|
| **Responsable Funcional MME** | Valida información de agentes (1er validador) |
| **Coordinador MME** | Aprueba/Rechaza creación de agentes (2do validador) |
| **Operador Líder** | Inhabilita agentes, asigna precios/volúmenes, bloqueos |
| **Administrador del Sistema** | Gestión de firmas SIGDI, configuración general |
| **Profesional de Calidad** | Control de calidad del dato, auditorías |
| **Profesional de Operación Estadística** | Análisis estadístico, reportes |

### 6.3 Equipo Operativo SICOM

El equipo que opera y mantiene el SICOM está compuesto por roles técnicos y funcionales:

#### Área Funcional

| Rol | Responsabilidad |
|-----|---------------|
| **Líder Funcional** | Dirección estratégica del sistema, toma de decisiones funcionales |
| **Analistas Funcionales** | Levantamiento de requerimientos, diseño de procesos, pruebas funcionales |
| **Formadores** | Capacitación a agentes, creación de material didáctico |
| **Profesional de Operación Estadística** | Análisis de datos, reportes estadísticos |
| **Profesional de Calidad** | Aseguramiento de calidad, auditorías de procesos |
| **Coordinador Call Center** | Dirección del centro de contacto |
| **Agente de Calidad** | Control de calidad en atención del call center |

#### Área Técnica

| Rol | Responsabilidad |
|-----|---------------|
| **Líder Técnico** | Dirección técnica del proyecto, arquitectura de solución |
| **Arquitecto de Software** | Diseño de arquitectura de aplicaciones, estándares técnicos |
| **Desarrolladores Java** | Desarrollo backend, integraciones, APIs |
| **Desarrolladores BPM (Bizagi)** | Modelado e implementación de procesos en Bizagi |
| **Especialistas BI** | Diseño de cubos, tableros, ETL, calidad del dato |
| **Ingenieros de Pruebas (QA)** | Pruebas funcionales, automatizadas, regresión |
| **Administrador de Base de Datos** | Gestión de BD, tuning, backups, replicación |
| **Especialistas en Inteligencia de Negocios** | Análisis de negocio, modelos predictivos |

---

## 7. FUNCIONALIDADES DETALLADAS

### 7.1 Gestión de Agentes

**Crear Agente:**
- Registro desde portal web externo
- Diligenciamiento de datos básicos: NIT, razón social, tipo de agente, dirección, contacto
- Adjuntos obligatorios según tipo de agente (PDF únicamente)
- Normalización automática de direcciones
- Validación de estructura de correos y páginas web
- Cálculo automático de dígito de verificación del NIT
- Workflow de validación en Bizagi (Responsable Funcional + Coordinador)
- Duración máxima de validación: 60 días
- Generación automática de código SICOM y credenciales
- Notificación por correo electrónico con memorando de aprobación

**Actualizar Agente:**
- Modificación de datos del agente existente
- Reutilización del subproceso "Validar Información"
- Control de versiones de documentos

**Inhabilitar Agente:**
- Desactivación completa del agente, plantas y usuarios asociados
- Notificación automática al agente
- Job automático de validación de documentos vencidos

**Bloqueo/Desbloqueo:**
- Bloqueo automático por documentos vencidos (Jobs diarios)
- Desbloqueo manual por Operador Líder

### 7.2 Gestión de Plantas

Tipos de plantas según el agente:
- Planta de abastecimiento (distribuidor mayorista)
- EDS Automotriz
- EDS Aviación
- EDS Marítima
- EDS Fluvial
- EDS Privada
- EDS Pública
- EDS Mixta
- Comercializador Industrial
- Instalación de Gran Consumidor

**Funcionalidades:**
- Creación de planta con datos georreferenciados
- Asociación a agente propietario o arrendatario
- Configuración de productos habilitados por planta
- Gestión de documentos de la planta
- Inhabilitación automática en cascada con el agente

### 7.3 Gestión de Vehículos

**Datos del vehículo:**
- Placa, tipo de vehículo, capacidad
- SOAT (vigencia)
- Póliza de seguro (vigencia)
- Revisión técnico-mecánica
- Licencia de conducción del conductor

**Validaciones automáticas:**
- Job diario de alerta de vencimiento de póliza vehicular (JobAlerVencPoliVehi)
- Bloqueo de vehículo si documentos vencidos
- Asociación a agente transportador

### 7.4 Órdenes de Pedido

**Tipos de Orden de Pedido:**

| Tipo | Descripción | Uso Principal |
|------|-------------|---------------|
| **Simple** | Solicitud estándar de uno o más productos | Mayoría de transacciones |
| **Programada** | Órdenes con programación temporal recurrente | Suministro continuo |
| **Anticipada Individual** | Solicitud anticipada por agente individual | Planificación |
| **Anticipada por Nominación** | Solicitud anticipada con volúmenes nominados | Control de cupos |
| **Transferencia** | Movimiento entre instalaciones del mismo agente | Reubicación de inventario |

**Estados del Flujo:**
1. Solicitud → 2. Aceptación → 3. Despacho → 4. Tránsito → 5. Cumplido → 6. Cierre

**Devoluciones posibles:**
- Devolución a solicitud (desde aceptación)
- Devolución en despacho
- Anulación total (evento intermedio "Anular OPS")

**Notificaciones automáticas:**
- Creación de orden
- Aceptación/Rechazo
- Despacho
- Cierre
- Anulación

### 7.5 Guías Digitales (SIGDI)

Ver sección 5.2 para detalle completo.

Puntos clave adicionales:
- Las guías se generan SOLO para órdenes en estado "Despachado"
- Los precios se registran en SICOM y se reflejan en SIGDI
- El cierre de OPS genera automáticamente la guía
- Las guías tienen vigencia temporal definida en horas
- Las guías firmadas son válidas para transporte de combustibles a nivel nacional
- La guía incluye: información general, información de transporte, información de productos

### 7.6 Monitoreo y Cumplidos

**Monitoreo de Vehículos:**
- Subproceso que permite seguimiento de vehículos en tránsito
- Georreferenciación (integración con sistemas GPS)
- Alertas de desviación de rutas
- Control de tiempos de entrega

**Cumplidos:**
- Documento que certifica la entrega de combustible
- Validado por el Puesto de Control
- Incluye volúmenes entregados, calidad del producto, observaciones
- Generación automática por el sistema cuando aplica

### 7.7 Precios y Volúmenes

**Registro de Precios:**
- Los agentes registran precios de venta por producto y planta
- El sistema valida que estén dentro de los rangos mínimos/máximos definidos por el MME
- Histórico de precios por fecha

**Asignación de Precios Mínimos y Máximos:**
- El Operador Líder del MME define rangos de precios por producto
- Los precios fuera de rango generan alertas y bloqueos

**Volumen Máximo:**
- Cupos de compra máximos por agente y producto
- Solicitudes de incremento de cupo
- Reasignación de volúmenes entre agentes
- Control de consumo vs. cupo asignado

### 7.8 Declaración de Información

Los agentes deben declarar periódicamente:
- Inventarios de combustibles
- Compras y ventas
- Importaciones
- Exportaciones
- Producción (refinadores)
- Movimientos entre instalaciones

**Modalidades:**
- Declaración individual por formulario web
- Cargue masivo por archivo Excel
- Actualización de declaraciones enviadas
- Validación de consistencia de datos

### 7.9 Gestión de Usuarios y Perfiles

**Tipos de Usuario:**

| Tipo | Descripción |
|------|-------------|
| **Usuario Principal** | Usuario administrador del agente, tiene acceso total |
| **Usuario Secundario** | Usuario con permisos limitados, creado por el principal |
| **Usuario Planta** | Usuario específico para operar en SIGDI desde una planta |

**Permisos:**
- Crear órdenes de pedido
- Aceptar/despachar órdenes
- Registrar precios
- Declarar información
- Gestionar vehículos
- Consultar reportes

---

## 8. INFRAESTRUCTURA TECNOLÓGICA

### 8.1 Arquitectura de Red

El SICOM opera sobre una infraestructura de red segmentada y redundante:

- **Conectividad Internet:** Múltiples proveedores (ETB, INTERNEXA)
- **Enlaces dedicados:** Conectividad punto a punto hacia instalaciones críticas
- **Redundancia:** Enlaces primarios y de respaldo
- **Segmentación:** VLANs por función (Web, App, DB, Admin)

### 8.2 Seguridad Perimetral

| Componente | Tecnología | Función |
|------------|-----------|---------|
| **Firewall UTM** | Fortinet FGT2600F | Filtrado de tráfico, VPN, IDS/IPS |
| **WAF** | FortiWeb | Protección de aplicaciones web, anti-bot, anti-DDoS |
| **SIEM** | FortiSIEM | Centralización de logs, correlación de eventos, alertas |
| **Antivirus Endpoint** | Kaspersky | Protección de endpoints corporativos |

### 8.3 WAF — Web Application Firewall

- **Tecnología:** FortiWeb
- **Funciones:**
  - Inspección de tráfico HTTP/HTTPS
  - Protección contra inyección SQL
  - Protección contra XSS (Cross-Site Scripting)
  - Control de bots y crawlers maliciosos
  - Reglas personalizadas por aplicación
  - Certificados SSL/TLS administrados

### 8.4 Balanceadores y ADC

- **Tecnología:** A10 Thunder ADC
- **Funciones:**
  - Balanceo de carga L4/L7
  - SSL Offloading
  - Compresión de tráfico
  - Health checks de servidores backend
  - Failover automático

### 8.5 Bases de Datos

- **Motor principal:** Oracle Database
- **Esquemas:**
  - Datos maestros (agentes, plantas, vehículos)
  - Transaccional (órdenes de pedido, guías, declaraciones)
  - Histórico (auditoría, logs, versiones)
- **Administradores:** DBA especializados en Oracle
- **Backups:** Diarios incrementales, semanales completos
- **Replicación:** Standby para alta disponibilidad

### 8.6 Servidores y Virtualización

- **Plataforma:** VMware / Hyper-V (según certificaciones)
- **Servidores de aplicación:** Java EE (JBoss/WebLogic)
- **Servidores web:** Apache / Nginx
- **Servidores BPM:** Bizagi Engine
- **Servidores BI:** SQL Server Analysis Services / Power BI (según evidencias)
- **Servidores de archivos:** NAS/SAN para documentos adjuntos

### 8.7 DRP — Disaster Recovery Plan

**Objetivo:** Garantizar la continuidad del negocio en caso de desastre.

**Componentes:**
- **Procedimiento de Activación DR:** Documento formalizado con pasos detallados
- **Plan de Pruebas DR:** Ejecución periódica de simulacros
- **Sitio de Recuperación:** Infraestructura alterna para operación crítica
- **RPO (Recovery Point Objective):** Máximo tiempo de pérdida de datos aceptable
- **RTO (Recovery Time Objective):** Tiempo máximo para restaurar operación
- **Backups en sitio alterno:** Replicación de datos críticos

**Pruebas realizadas:**
- Ejecución de DRP Marzo 2025 (documentado en presentación)
- Validación de restauración de bases de datos
- Validación de conectividad de aplicaciones
- Validación de disponibilidad de servicios críticos

---

## 9. SEGURIDAD DE LA INFORMACIÓN

### 9.1 Ethical Hacking y Pentesting

**Pruebas realizadas:**
- **Ethical Hacking Externo:** Mayo 2025 (IDE-0020)
  - Pruebas de penetración desde Internet
  - Identificación de vectores de ataque externos
  - Evaluación de WAF, firewalls y exposición de servicios
- **Ethical Hacking Interno:** Evaluación de seguridad interna
  - Pruebas de movimiento lateral
  - Escalación de privilegios
  - Evaluación de segmentación de red

### 9.2 Análisis de Vulnerabilidades

**Informes generados:**
- Análisis de vulnerabilidades primer semestre 2025
- Matriz de vulnerabilidades SICOM (actualizada mensualmente)
- Clasificación por criticidad: Crítica, Alta, Media, Baja

**Categorías de vulnerabilidades monitoreadas:**
- Vulnerabilidades de software (SICOM, Bizagi, SO)
- Vulnerabilidades de infraestructura (firewall, balanceadores)
- Vulnerabilidades de configuración (SSL/TLS, políticas de contraseña)
- Vulnerabilidades de código (inyección SQL, XSS, CSRF)

### 9.3 Gestión de Incidentes

- **Registro:** Todos los incidentes de seguridad se documentan
- **Clasificación:** Por severidad y tipo
- **Respuesta:** Protocolo de respuesta a incidentes con tiempos definidos
- **Escalamiento:** Comité Técnico de Seguridad

### 9.4 Comité de Seguridad

- **Frecuencia:** Sesiones mensuales
- **Participantes:** Líder Técnico, Arquitecto de Software, DBA, Especialistas de Seguridad, Líder Funcional
- **Temas:**
  - Estado de vulnerabilidades
  - Incidentes de seguridad
  - Pruebas de pentesting
  - Actualizaciones de parches
  - Políticas de acceso
  - Auditorías de cumplimiento

---

## 10. OPERACIÓN Y SOPORTE

### 10.1 Mesa de Ayuda (N1 / N2)

**Nivel 1 (N1):**
- Atención telefónica y por chat
- Resolución de incidentes simples
- Reset de contraseñas
- Orientación en el uso de la plataforma
- Escalamiento a N2 si no puede resolver

**Nivel 2 (N2):**
- Resolución de incidentes técnicos complejos
- Configuración de agentes y plantas
- Gestión de bugs del sistema
- Coordinación con desarrollo
- Protocolos de atención documentados

### 10.2 Sistema de Tickets (Aranda)

- **Plataforma:** Aranda Service Desk
- **Funciones:**
  - Creación de tickets por agentes (vía call center o autogestión)
  - Asignación automática por categoría
  - Seguimiento de estado (nuevo, en proceso, resuelto, cerrado)
  - SLAs definidos por tipo de ticket
  - Escalamiento automático por vencimiento de SLA
  - Base de conocimiento integrada

### 10.3 Centro de Contacto (WolKVOX)

- **Plataforma:** WolKVOX Contact Center
- **Canales:** Teléfono, correo electrónico
- **Funciones:**
  - IVR (respuesta de voz interactiva)
  - Distribución automática de llamadas (ACD)
  - Grabación de llamadas
  - Monitoreo de agentes en tiempo real
  - Reportes de productividad

### 10.4 Capacitaciones y Formación

**Programas de capacitación:**
- Webinars mensuales (2025-2026)
- Microbits (videos cortos tutoriales)
- Preturnos N1 (capacitación mensual a agentes)
- Gestión del conocimiento (documentación actualizada)
- Capacitaciones externas (agentes, entidades gubernamentales, SGI, MME)
- Módulo de consultas (formación específica)
- Videos "Aprende SICOM" (contenido actualizado por tipo de agente)

**Material disponible:**
- Manuales de usuario
- Guías paso a paso
- Videos tutoriales
- Instructivos
- Plantillas MME
- Evaluaciones trimestrales

---

## 11. INTEGRACIONES Y APIs

### 11.1 Integraciones Principales

| Sistema | Tipo | Función |
|---------|------|---------|
| **Bizagi ↔ SICOM Web** | SOAP / REST | Workflow engine |
| **SICOM ↔ SIGDI** | Web Service | Generación y validación de guías |
| **SICOM ↔ BI** | ETL / Base de datos | Alimentación de cubos y tableros |
| **SICOM ↔ Aranda** | API / Email | Gestión de tickets |
| **SICOM ↔ WolKVOX** | CTI | Integración telefónica |
| **SICOM ↔ FortiSIEM** | Syslog / API | Envío de logs de seguridad |
| **SICOM ↔ FortiWeb** | HTTP/HTTPS | Protección de tráfico web |
| **SICOM ↔ Servicios MME** | Web Service | Validación de datos, consultas |

### 11.2 APIs Externas

- **Validación de NIT:** Conexión con servicios de validación de RUT/NIT de Colombia
- **Normalización de direcciones:** Servicio de geocodificación
- **Validación de correos:** Servicio de verificación de email
- **Firma digital:** Servicio de firma electrónica integrado
- **Notificaciones por correo:** SMTP integrado con plantillas

---

## 12. GLOSARIO

| Término | Definición |
|---------|------------|
| **ACPM** | Aceite Combustible Para Motores (diésel corriente) |
| **Agente** | Persona natural o jurídica autorizada por el MME para operar en la cadena de combustibles |
| **Bizagi** | Plataforma de Business Process Management (BPM) usada en SICOM |
| **BPM** | Business Process Management — Gestión por Procesos de Negocio |
| **Código SICOM** | Código único de 6 dígitos asignado a cada agente autorizado |
| **Contingencia** | Plan temporal de abastecimiento ante eventualidades |
| **Cumplido** | Documento que certifica la entrega de combustible en una orden de pedido |
| **DRP** | Disaster Recovery Plan — Plan de Recuperación ante Desastres |
| **EDS** | Estación de Servicio |
| **GC** | Gran Consumidor |
| **GNCV** | Gas Natural Comprimido Vehicular |
| **MME** | Ministerio de Minas y Energía de Colombia |
| **N1 / N2** | Nivel 1 / Nivel 2 de soporte técnico |
| **ONAC** | Organismo Nacional de Acreditación de Colombia |
| **OP** | Orden de Pedido |
| **OPS** | Orden de Pedido Simple |
| **SIGDI** | Sistema de Información Guías Digitales de Transporte |
| **SIEM** | Security Information and Event Management |
| **SLA** | Service Level Agreement — Acuerdo de Nivel de Servicio |
| **SOAP** | Simple Object Access Protocol — Protocolo de comunicación web |
| **SOAT** | Seguro Obligatorio de Accidentes de Tránsito |
| **Surtidor** | Dispositivo con registro de volumen y precio del combustible |
| **WAF** | Web Application Firewall |

---

## 13. GOBERNANZA DEL PROYECTO Y CONTROL DE CAMBIOS

### 13.1 Comité de Control de Cambios

El SICOM opera bajo una estricta gobernanza de cambios mediante el **Comité de Control de Cambios** (CCC), conformado por representantes del MME y del equipo técnico de INTERNEXA.

**Frecuencia:** Sesiones periódicas (semanales/quincenales)

**Participantes típicos:**
- Representantes del Ministerio de Minas y Energía (MME)
- Gerente / Director de Proyecto (INTERNEXA)
- Líder Técnico
- Líder Funcional
- Líder BI
- Líder Scrum
- Especialista Base de Datos
- Analista de QA
- Especialista Procesos BPM
- Analistas Funcionales
- Especialista Experiencia de Usuario

### 13.2 Proceso de Cambios (RFC)

Todas las modificaciones al SICOM se gestionan mediante **Requests for Change (RFC)**:

| Tipo de Cambio | Descripción | Aprobación |
|----------------|-------------|------------|
| **RFC Estándar** | Cambios planificados de bajo/medio impacto | Comité de Control de Cambios |
| **RFC de Emergencia** | Cambios urgentes por fallos críticos | Aprobación previa por correo del MME + Formalización posterior en comité |
| **Cambios Evolutivos** | Nuevas funcionalidades, mejoras | Comité + Validación UAT |
| **Cambios BPM** | Modificaciones a procesos Bizagi | Comité + Equipo BPM |
| **Cambios BI** | Ajustes ETL, cubos, reportes | Comité + Equipo BI |
| **Cambios SIGDI** | Mejoras al módulo de guías | Comité + Equipo SIGDI |

**Ejemplos de RFCs documentados:**
- RFC 249: Ajuste ETL incremental de compras (HU 2194)
- RFC 250: Ajuste regla de negocio Orden de Pedido Simple (corrección límite de 20,000 galones)
- RFC 2026-269: Reinicio controlado servidor Nuevo Sicom BPM (emergencia)
- RFC 2026-270: Reinicio controlado de nodos Sicom BPM (emergencia)
- RFC 2026-271: Depuración de tablas propuestas por fabricante
- RFC 2026-272: Cambios BPM
- RFC 2026-273: Cambios evolutivos de BI
- RFC 2026-274: Mejoras en SIGDI

### 13.3 Políticas del Comité

- **Política de Freezing:** Períodos de congelamiento donde no se ejecutan cambios (generalmente durante cierres mensuales o períodos críticos)
- **Política de Comunicación:** Protocolo de notificación a stakeholders ante cambios
- **Backup obligatorio:** Antes de cualquier cambio en BD o ETL
- **Validación post-cambio:** BI + Equipo funcional deben validar
- **Ventanas de ejecución:** Programadas para minimizar impacto operativo

---

## 14. MIGRACIÓN A GAS (PROYECTO EN CURSO)

### 14.1 Alcance de la Migración

El proyecto SICOM está expandiendo su alcance para incluir la gestión de **gas natural vehicular (GNV / GNCV)** además de los combustibles líquidos.

**Roadmap:** Vigencia diciembre 2025 — junio 2026

### 14.2 Componentes de la Migración

| Componente | Descripción |
|------------|-------------|
| **Datos Maestros** | Modelo de datos, catálogos para productos de gas |
| **Formularios** | Estructura de entrada, formularios web, reglas de negocio |
| **Transacciones** | Procesos operativos, validaciones, integraciones WS |
| **Consultas y Analítica** | KPIs, paneles, reportes regulatorios, reportes operativos |
| **Alistamiento Producción** | Pruebas, despliegue, validación final |

### 14.3 Historias de Usuario (HU) — Backlog

**Implementadas en UAT:**
- HU 2045: Habilitación de módulo de reasignación de casos para usuario principal del agente
- HU 2068: Ajuste proceso de actualización de agentes GC (Gran Consumidor)
- HU 2184: Restricción de reportes de ventas en fechas futuras

**Depuradas en proceso de Firmas:**
- HU 2185: Formulario de actualización de agentes GAS
- HU 2349: Módulo de actualización de agentes GAS
- HU 2362: Actualizar agente campos GAS
- HU 2363: Cargue masivo de vehículos

**Pendientes de levantar (proyectadas):**
- Procesos (7 HU)
- Formularios y Reglas de Negocio (5 HU)
- Web Services y Reportes (10 HU)

**Sin firma en depuración:**
- HU: Control de reporte de ventas EDS balance GAS
- HU: Registro contrato suministro
- HU: Modelo de datos

### 14.4 Procesos BPM a Migrar (Java GCV / GNCV → BPM Bizagi)

Los procesos actuales de gas que operan en Java serán migrados a la plataforma BPM Bizagi para unificar la arquitectura con los combustibles líquidos.

---

## 15. INDICADORES Y REPORTES DE SERVICIO (ANS)

### 15.1 Acuerdo de Nivel de Servicio (ANS/SLA)

El SICOM opera bajo ANS contractuales medidos mensualmente:

**Reportes de ANS mensuales:**
- Reporte de ANS Diciembre 2025
- Reporte de ANS Enero 2026

**Indicadores típicos:**
- Disponibilidad del sistema (% uptime)
- Tiempo de respuesta de aplicación
- Resolución de incidentes (N1 / N2)
- Cumplimiento de RFCs programados
- Calidad del dato (% completitud, % exactitud)

---

## 16. RIESGOS Y CONTROLES

**Matriz de riesgos actualizada periódicamente** con identificación de:
- Riesgos técnicos (infraestructura, disponibilidad)
- Riesgos de seguridad (vulnerabilidades, brechas)
- Riesgos funcionales (cambios regulatorios, bugs)
- Riesgos de proyecto (cronograma, recursos)

**Controles:**
- Comité Técnico de Seguridad (mensual)
- Comité de Control de Cambios
- Pruebas de DRP periódicas
- Pentesting semestral
- Monitoreo continuo (FortiSIEM)

---

## ANEXO A: HISTORIAL DE RFCs DOCUMENTADOS

| No. | Descripción | Tipo | Fecha |
|-----|-------------|------|-------|
| RFC 249 | Ajuste ETL compras (HU 2194) | BI | Dic 2025 |
| RFC 250 | Ajuste regla de negocio OPS (20,000 galones) | BPM | Dic 2025 |
| RFC 251 | — | — | Dic 2025 |
| RFC 2026-269 | Reinicio controlado servidor BPM | Emergencia | Feb 2026 |
| RFC 2026-270 | Reinicio controlado nodos BPM | Emergencia | Feb 2026 |
| RFC 2026-271 | Depuración tablas fabricante | BD | Feb 2026 |
| RFC 2026-272 | Cambios BPM | BPM | Feb 2026 |
| RFC 2026-273 | Cambios evolutivos BI | BI | Feb 2026 |
| RFC 2026-274 | Mejoras SIGDI | SIGDI | Feb 2026 |

---

## ANEXO B: CONTROL DE CAMBIOS

| Versión | Fecha | Autor | Cambios |
|---------|-------|-------|---------|
| 1.0 | Mayo 2026 | ZEUS / Análisis Documental | Síntesis inicial del SICOM a partir de 48 documentos técnicos de la carpeta operativa |

---

**Documento generado por análisis automatizado de la carpeta documental SICOM.**
**Fuentes principales:** M-126 (Procesos de Apoyo V6), M-127 (Procesos Core V5), M-128 (Procesos de Control V5), Manuales SIGDI, Guías SICOM, Informes de Seguridad, Documentación de Infraestructura, DRP, Actas de Comités de Control de Cambios, Roadmap de Migración a Gas, y ~40 documentos adicionales.



---

## ANEXO C: ACTIVOS DE INFRAESTRUCTURA SICOM

### IPs Internas (Red SICOM)

| No. | IP | Responsable |
|-----|-----|-------------|
| 1 | 192.168.76.131 | SICOM |
| 2 | 192.168.76.132 | SICOM |
| 3 | 192.168.76.247 | SICOM |
| 4 | 192.168.76.147 | SICOM |
| 5 | 192.168.76.200 | SICOM |
| 6 | 192.168.77.136 | SICOM |
| 7 | 192.168.76.157 | SICOM |
| 8 | 192.168.76.145 | SICOM |
| 9 | 192.168.76.146 | SICOM |
| 10 | 192.168.76.232 | SICOM |
| 11 | 192.168.77.100 | SICOM |
| 12 | 192.168.77.101 | SICOM |
| 13 | 192.168.76.254 | SICOM |
| 14 | 192.168.76.83 | SICOM |
| 15 | 192.168.76.172 | SICOM |
| 16 | 192.168.77.160 | SICOM |
| 17 | 192.168.76.155 | SICOM |
| 18 | 192.168.76.161 | SICOM |
| 19 | 192.168.77.153 | SICOM |
| 20 | 192.168.77.150 | SICOM |
| 21 | 192.168.77.151 | SICOM |
| 22 | 10.158.2.131 | SICOM |
| 23 | 192.168.76.156 | SICOM |
| 24 | 192.168.76.129 | SICOM |
| 25 | 192.168.76.190 | SICOM |
| 26 | 192.168.77.191 | SICOM |
| 27 | 10.158.3.110 | SICOM |

**Total dispositivos analizados:** 54

### URLs Externas SICOM

| No. | URL | Servicio |
|-----|-----|----------|
| 1 | https://www.sicom.gov.co/ | Portal Web |
| 2 | https://wss.sicom.gov.co/sicomdata/ | Web Service |
| 3 | https://eds.sicom.gov.co/eds/api/v1 | API EDS |
| 4 | https://bi.sicom.gov.co/OLAP/msmdpump.dll | BI OLAP |
| 5 | https://bi.sicom.gov.co/OLAP_PRUEBASDLLO/msmdpump.dll | BI Pruebas |
| 6 | https://bi.sicom.gov.co/OLAP_GCV/msmdpump.dll | BI GCV |
| 7 | https://bi.sicom.gov.co/OLAP_ENTIDADEXT/msmdpump.dll | BI Entidades |
| 8 | https://bi.sicom.gov.co/OLAP_EXTERNO/msmdpump.dll | BI Externo |
| 9 | https://bi.sicom.gov.co/OLAP_PRUEBAS/msmdpump.dll | BI Pruebas |
| 10 | https://pruebabi.sicom.gov.co/ | Pruebas BI |
| 11 | https://portal.sicom.gov.co/SICOM | Portal |
| 12 | https://mesadeservicio.sicom.gov.co//USDKv8//#!/login/ | Mesa de Servicio |
| 13 | https://liquidos.sicom.gov.co/sicom/identificacionAction.do | Líquidos |
| 14 | https://gncv.sicom.gov.co/login | GNCV |
| 15 | https://bwss.sicom.gov.co/sicomdata/ | Web Service Backup |
| 16 | https://aprendesicom.sicom.gov.co/login/index.php | Capacitaciones |
| 17 | https://git.sicom.gov.co/users/sign_in | GitLab |
| 18 | https://sigdi.sicom.gov.co/guias/ | SIGDI |
| 19 | https://pru.api.sicom.gov.co | API Pruebas |
| 20 | https://api.sicom.gov.co | API Producción |
| 21 | https://cubos.sicom.gov.co | Cubos BI |
| 22 | https://moduloconsultas.sicom.gov.co/Login | Consultas |
| 23 | https://sigdipruebas.sicom.gov.co/ | SIGDI Pruebas |
| 24 | https://uatsicomconsultas.sicom.gov.co/ | UAT Consultas |
| 25 | https://wsp.sicom.gov.co/ | Web Service Public |
| 26 | https://uatbpm.sicom.gov.co/UAT_TEST/ | UAT BPM |
| 27 | https://uatbpm.sicom.gov.co/ws/sicomdata | UAT BPM WS |

---

## ANEXO D: PROCEDIMIENTO DE GESTIÓN DE VULNERABILIDADES

**Responsable:** INTERNEXA S.A.

| Paso | Actividad | Descripción |
|------|-----------|-------------|
| 1 | Escaneo | Realizar escaneo a todos los dispositivos en la línea base mediante herramienta de análisis de vulnerabilidades según política establecida |
| 2 | Evaluación | Evaluar y analizar resultados obtenidos y clasificar según criticidad |
| 3 | Plan de Remediación | Generar plan de mitigación. En caso necesario escalar al proveedor/fabricante para encontrar solución de cierre |
| 4 | Retest | Realizar segundo escaneo para verificar cierre |
| 5 | Verificación | Verificar resultados del Retest. Si no se cerraron, analizar si se requiere nuevo plan de mitigación |
| 6 | Informe Técnico | Generar informe técnico con detalles del análisis |
| 7 | Análisis de Riesgo | Efectuar análisis de riesgo para estimar probabilidad de materialización de evento no deseado |
| 8 | Informe Ejecutivo | Generar y presentar informe ejecutivo en formato Word |

---

## ANEXO E: MÓDULO DE CONTINGENCIAS DE ABASTECIMIENTO

**Historia de Usuario:** HU-1531 — Configuración de Plantas Para Contingencias

**Objetivo:** Crear un módulo que permita realizar cambios temporales en los planes de abastecimiento habituales de una región o regiones específicas del país, garantizando que no se interrumpa el abastecimiento de combustible ante eventualidades.

**Reglas de Negocio:**
- Se instancia un caso para cada mayorista que opere en la zona de contingencia
- El módulo cuenta con filtros: Departamento, Municipio, Mayorista, Plantas asociadas
- Los mayoristas mostrados son aquellos con contrato de suministro con EDS activas (Automotrices y Fluviales) del Departamento/Municipio seleccionado
- Se presenta una colección de plantas asociadas al mayorista para desactivar la actual y activar la de contingencia
- **Excepciones por ubicación:** En municipios donde EDS del casco urbano tienen plan diferente a las de zona rural, se maneja un check de excepción que abre colección de EDS del municipio y plantas asociadas
- A las EDS solo se les configura **una planta de contingencia**, única visible al momento de realizar OPS
- **Temporizador de contingencia:** Fecha de inicio + cantidad de días = fecha fin automática (hasta las 23:59 horas). La fecha fin no es editable
- En caso de prórroga: la cantidad total de días debe ser superior a la contingencia inicial (ej: si fueron 10 días, la actualización debe ser 11 o más)
- Al terminar la contingencia, se restablece automáticamente la configuración de plantas del plan de abastecimiento definido
- Si ingresa una EDS nueva durante el periodo de contingencia, el operador SICOM debe instanciar un caso para activarle la planta de contingencia
- La actualización de casos instanciados permite ampliar días de contingencia mostrando el total
- Se puede deshabilitar la contingencia antes del tiempo configurado mediante botón de deshabilitar

**Criterios de Aceptación:**
- El usuario operador de SICOM puede configurar, activar y/o desactivar plantas de manera temporal para activar planes de contingencia de abastecimiento

---

## ANEXO F: DATASET DE CASOS ARANDA — ENERO 2026

**Total de casos analizados:** ~1,900 registros

**Categorías principales de incidentes:**
- FALLA INGRESO A SIGDI
- FALLA INGRESO A SICOM LÍQUIDOS
- FALLA TRANSMISIÓN DATOS WEB SERVICE SICOM LÍQUIDOS
- FALLA INGRESO A SICOM GNCV
- FALLA TRANSMISIÓN DATOS WEB SERVICE SICOM GNCV

**Estados de casos:**
- CANCELADO (Mayoría — casos mal registrados que se derivan a portal de Autogestión)
- CERRADO (Casos resueltos por Grupo de Análisis SICOM)

**SLA aplicado:** MEDIO 24H (Tiempo máximo de atención: 24 horas)

**Canales de registro:** Portal Cliente (principal), Call Center

**Grupos de resolución:**
- CALL CENTER (N1)
- INTERNEXA FUNCIONAL (N2)

**Ejemplo de caso típico:**
- Caso 3562: FALLA INGRESO A SIGDI — No llegaban códigos de verificación a correos
- Fecha registro: 2026-01-22
- Fecha cierre: 2026-01-28 (6 días)
- Grupo resolutor: INTERNEXA FUNCIONAL
- Solución: Ajuste en el sistema para estabilizar operación y acceso en la plataforma

---

## ANEXO G: SOLUCIÓN WORKAROUND MÓDULO ENCUESTAS

**Documento:** Arq. Marcelo Tunarosa | ITX | Noviembre 2024

**Contexto:** Necesidad de publicar una encuesta para agentes minoristas (61, 62, 63) en el Nuevo SICOM BPM. Obligatoria para diligenciar antes de acceder al sistema.

**Arquitectura:**
- Ambiente Productivo: Encuesta integrada en flujo BPM
- Ambiente UAT: Pruebas de integración

**Solución General (Especialista BPM – Bizagi):**
- Colección de Postman para consumo de la API nativa de Bizagi

**Solución Detallada (Especialista JAVA):**
- Tabla: `MAE_TBL_CODIGOVERIFICACION` — Almacena: ID, fecha generación, código SICOM, usuario, código verificación
- Tabla: `MAE_TBL_ENCUESTA` — Almacena: ID, fecha registro, código SICOM, usuario, respuesta, valor, IP origen
- Front-end: Formulario de encuesta con validación
- Correo: Plantilla de notificación con código de verificación

---

**Documento generado por análisis automatizado de la carpeta documental SICOM.**
**Fuentes principales:** M-126 (Procesos de Apoyo V6), M-127 (Procesos Core V5), M-128 (Procesos de Control V5), Manuales SIGDI, Guías SICOM, Informes de Seguridad, Documentación de Infraestructura, DRP, Actas de Comités de Control de Cambios, Roadmap de Migración a Gas, Matriz de Vulnerabilidades, Dataset Aranda, y ~40 documentos adicionales.



## ANEXO H: LISTADO GENERAL DE REQUERIMIENTOS SICOM LÍQUIDOS

**Documento:** Listado General de Requerimientos SICOM Líquidos — MME (Octubre 2025)

**Resumen de Historias de Usuario:**

| NÚMERO | NOMBRE | SISTEMA | ESTADO | ORIGEN | FUNCIONAL MME |
|--------|--------|---------|--------|--------|---------------|
| 344 | Validación Vehículos Comercializadores Industriales y EDS de Zona de Frontera | NUEVO SICOM LIQUIDOS | EN PRODUCCIÓN | Migración Java a Bizagi | DIANA RUIZ |
| 360 | Actualización de Cupos OPAI proceso ACOP | NUEVO SICOM LIQUIDOS | SIN FIRMA | Evolutivos / Rediseños | ANGIE KATHERINE MEJIA GONZALEZ |
| 1206 | Creación Jobs y Campos Comercializador Industrial | NUEVO SICOM LIQUIDOS | EN BACKLOG | Migración Java a Bizagi | PABLO TORRES |
| 1212 | Ajustes Comercializador Industrial – Excepciones y Direcciones Cliente Final | NUEVO SICOM LIQUIDOS | EN DESARROLLO | Migración Java a Bizagi | PABLO TORRES |
| 1993 | Cierre, Anulación y Rechazo Guía de OPP | SIGDI | EN DESARROLLO | Evolutivos / Rediseños | NICOLAS LEIVA |
| 1531 | Proceso de Configuración Contingencias (Plantas) | NUEVO SICOM LIQUIDOS | CERTIFICACION FUNCIONAL | Evolutivos / Rediseños | MAIDA EUNISE HERRERA |

**Estados de HU:**
- **EN PRODUCCIÓN:** Desplegadas y operativas
- **EN DESARROLLO:** En construcción
- **EN BACKLOG:** Pendientes de iniciar
- **SIN FIRMA:** Requieren aprobación formal del MME
- **PENDIENTE PASO A PRODUCCIÓN:** En pruebas finales

**Funcionales MME asignados:**
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
**Fuentes principales:** M-126 (Procesos de Apoyo V6), M-127 (Procesos Core V5), M-128 (Procesos de Control V5), Manuales SIGDI, Guías SICOM, Informes de Seguridad, Documentación de Infraestructura, DRP, Actas de Comités de Control de Cambios, Roadmap de Migración a Gas, Matriz de Vulnerabilidades, Dataset Aranda, Listado General de Requerimientos, y ~40 documentos adicionales.

---

> **ZEUS** — Sistema de Inteligencia Empresarial INNOVADATACO  
> *Análisis documental profundo — SICOM Ministerio de Minas y Energía*
