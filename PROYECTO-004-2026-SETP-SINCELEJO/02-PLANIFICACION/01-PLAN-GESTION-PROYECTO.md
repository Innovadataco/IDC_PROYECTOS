# PLAN DE GESTIÓN DEL PROYECTO
## PROYECTO 004-2026-SETP-SINCELEJO

---

## 1. PLAN DE GESTIÓN DEL ALCANCE

### 1.1 EDT / WBS — Estructura de Desglose del Trabajo

```
PROYECTO 004-2026-SETP-SINCELEJO
│
├── 1.0 INICIO
│   ├── 1.1 Revisión documentación base
│   ├── 1.2 Análisis normativo (Decreto 482/2023, 1079/2015)
│   ├── 1.3 Identificación interesados
│   ├── 1.4 Acta de constitución
│   └── 1.5 Caso de negocio
│
├── 2.0 PLANIFICACIÓN
│   ├── 2.1 Diseño arquitectura ITS (5 capas)
│   ├── 2.2 Especificaciones técnicas SRC
│   ├── 2.3 Especificaciones técnicas SGCF
│   ├── 2.4 Especificaciones técnicas SIU
│   ├── 2.5 Especificaciones técnicas SST
│   ├── 2.6 Presupuesto detallado CAPEX/OPEX
│   ├── 2.7 Cronograma implementación 15 meses
│   ├── 2.8 Modelo de contratación y hitos de pago
│   ├── 2.9 Plan de riesgos
│   └── 2.10 Plan de calidad y pruebas (FAT/SAT)
│
├── 3.0 EJECUCIÓN (ACOMPAÑAMIENTO)
│   ├── 3.1 Soporte licitación tecnología
│   ├── 3.2 Evaluación técnica ofertas
│   ├── 3.3 Negociación con proveedor seleccionado
│   ├── 3.4 Interventoría técnica (opcional)
│   └── 3.5 Ajustes especificaciones según ofertas
│
├── 4.0 CIERRE
│   ├── 4.1 Entrega documentación final
│   ├── 4.2 Transferencia de conocimiento
│   ├── 4.3 Capacitación METRO SABANAS
│   ├── 4.4 Lecciones aprendidas
│   └── 4.5 Acta de cierre
│
└── 5.0 ENTREGABLES
    ├── 5.1 Arquitectura ITS de referencia
    ├── 5.2 Especificaciones técnicas contratación
    ├── 5.3 Presupuesto y cronograma
    ├── 5.4 Propuesta de modelo de negocio
    └── 5.5 Informe de riesgos y mitigaciones
```

### 1.2 Diccionario EDT (Resumen)

| Código | Elemento | Descripción | Responsable |
|:-------|:---------|:------------|:------------|
| 1.1 | Revisión documentación | Análisis 7 entregables + estudios previos + RFI | ZEUS |
| 2.1 | Arquitectura ITS | Diseño 5 capas: campo, comm, procesamiento, app, presentación | ZEUS |
| 2.2 | Espec. SRC | Validadores, Mifare/QR/EMV, clearing, compensación | ZEUS |
| 2.3 | Espec. SGCF | GPS, control rutas, alertas, videovigilancia | ZEUS |
| 2.4 | Espec. SIU | App móvil, web, pantallas paraderos, predictor | ZEUS |
| 2.5 | Espec. SST | SAM/HSM, cifrado, autenticación, certificaciones EMV | ZEUS |
| 2.6 | Presupuesto | CAPEX/OPEX detallado, impuestos, contingencias | ZEUS |
| 2.7 | Cronograma | 15 meses (9 ejecución + 6 liquidación), hitos | ZEUS |
| 3.1 | Soporte licitación | Acompañamiento proceso selección, PQs, evaluación | Jelkin + ZEUS |
| 4.2 | Transferencia conocimiento | Manuales, capacitación, documentación operación | ZEUS |

---

## 2. PLAN DE GESTIÓN DEL CRONOGRAMA

### 2.1 Cronograma Resumen (3 meses estructuración INNOVADATACO)

| Fase | Duración | Inicio | Fin | Hitos |
|:-----|:---------|:-------|:----|:------|
| **FASE 1: Diagnóstico** | 2 semanas | 2026-06-01 | 2026-06-15 | M1: Diagnóstico aprobado |
| **FASE 2: Diseño** | 4 semanas | 2026-06-16 | 2026-07-15 | M2: Arquitectura ITS aprobada |
| **FASE 3: Estructuración** | 4 semanas | 2026-07-16 | 2026-08-30 | M3: Especificaciones entregadas |
| **FASE 4: Acompañamiento** | 2 semanas | 2026-09-01 | 2026-09-15 | M4: Soporte licitación iniciado |
| **Cierre** | 2 semanas | 2026-09-16 | 2026-09-30 | M5: Proyecto cerrado |

### 2.2 Dependencias Clave
- Diseño arquitectura (2.1) depende de diagnóstico (1.1)
- Especificaciones técnicas (2.2-2.5) dependen de arquitectura (2.1)
- Presupuesto (2.6) depende de especificaciones (2.2-2.5)
- Modelo contratación (2.8) depende de presupuesto (2.6)

---

## 3. PLAN DE GESTIÓN DE COSTOS

### 3.1 Presupuesto INNOVADATACO (Estructuración)

| Concepto | Valor (COP) | Nota |
|:---------|------------:|:-----|
| **Diagnóstico** | $20.000.000 | Revisión documentación, gap analysis |
| **Diseño arquitectura ITS** | $37.500.000 | 5 capas, diagramas, especificaciones |
| **Estructuración técnica** | $32.500.000 | TDRs, modelo contratación, cronograma |
| **Acompañamiento licitación** | $20.000.000 | Soporte PQs, evaluación, negociación |
| **Contingencia (10%)** | $11.000.000 | Riesgos, ajustes, imprevistos |
| **TOTAL** | **$121.000.000** | 3 meses de trabajo |

### 3.2 Presupuesto Referencia METRO SABANAS (Tecnología fase 1)

| Concepto | Valor (COP) | Nota |
|:---------|------------:|:-----|
| **Presupuesto oficial máximo** | $3.793.756.953 | Estudios previos 2023 |
| **Equipos a bordo (46 buses)** | ~$1.500.000.000 | Validadores, cámaras, routers, consolas |
| **Centro de control** | ~$200.000.000 | TVs, PCs, mobiliario, UPS, switch |
| **Software SaaS (licencias)** | ~$800.000.000 | SRC, SGCF, SIU, SST, cloud hosting |
| **Implementación y servicios** | ~$600.000.000 | Gerencia, parametrización, capacitación |
| **Seguridad y medios de pago** | ~$400.000.000 | SAM/HSM, 20.000 tarjetas, app móvil |
| **Contingencia** | ~$293.756.953 | 8% del total |

---

## 4. PLAN DE GESTIÓN DE RIESGOS

### 4.1 Registro de Riesgos (Inicial)

| ID | Riesgo | Categoría | Prob. | Impacto | Estrategia | Acción Mitigación | Responsable |
|:--:|:-------|:----------|:-----:|:-------:|:-----------|:------------------|:------------|
| R1 | Demanda insuficiente (< 20.724 pax/día) | Financiero | ALTA | CRÍTICO | Mitigar | Piloto gradual, ajuste frecuencias, campaña comunicaciones | Metro Sabanas |
| R2 | Falla conectividad celular 4G/5G | Técnico | ALTA | ALTO | Mitigar | Redundancia 4G/5G + radio trunking corredores | Proveedor tech |
| R3 | Ciberataque a recaudo | Técnico | MEDIA | CRÍTICO | Mitigar | HSM/KMS, segmentación red, auditoría seguridad | Proveedor tech |
| R4 | Retraso adquisición flota | Operativo | MEDIA | ALTO | Mitigar | Cronograma integrado, hitos sincronizados | Metro Sabanas |
| R5 | Interoperabilidad limitada futura | Técnico | MEDIA | MEDIO | Mitigar | APIs abiertas, estándares desde diseño | INNOVADATACO |
| R6 | Inestabilidad FEST | Financiero | ALTA | ALTO | Mitigar | Acuerdo financiación estable Nación-Municipio | Metro Sabanas |
| R7 | Escasez proveedores ITS | Técnico | BAJA | MEDIO | Aceptar | Licitación nacional, RFI amplio | Metro Sabanas |
| R8 | Resistencia mototaxismo | Social | ALTA | MEDIO | Mitigar | Programa gestión motocicletas, integración | Metro Sabanas |
| R9 | Obsolescencia tecnológica | Técnico | MEDIA | MEDIO | Mitigar | Licencias perpetuas, actualización continua | INNOVADATACO |
| R10 | Cambio normativo | Legal | BAJA | ALTO | Transferir | Monitoreo legislativo, cláusulas contractuales | INNOVADATACO |

### 4.2 Umbrales de Riesgo

| Métrica | Umbral |
|:--------|:-------|
| Presupuesto | ± 10% del presupuesto oficial |
| Plazo | ± 2 semanas del cronograma |
| Calidad | ≥ 95% cumplimiento especificaciones |
| Satisfacción | ≥ 4.5/5 encuesta cliente |

---

## 5. PLAN DE GESTIÓN DE LA CALIDAD

### 5.1 Métricas de Calidad

| Criterio | Métrica | Meta | Método Verificación |
|:---------|:--------|:----:|:--------------------|
| Precisión recaudo | % transacciones correctas | ≥ 99.5% | Pruebas FAT/SAT |
| Disponibilidad sistema | % uptime | ≥ 99.9% | Monitoreo 24/7 |
| Precisión GPS | metros error | ± 10m | Pruebas campo |
| Conteo pasajeros | % fiabilidad | ≥ 97% | Pruebas comparación |
| Tiempo respuesta app | segundos | < 3s | Pruebas carga |
| Cobertura comunicación | % rutas con señal | ≥ 95% | Mapeo señal |

### 5.2 Plan de Pruebas

| Tipo | Descripción | Responsable | Etapa |
|:-----|:------------|:------------|:------|
| FAT | Factory Acceptance Test — validación fábrica | Proveedor + Interventor | Pre-instalación |
| SAT | Site Acceptance Test — validación sitio | Proveedor + Interventor | Post-instalación |
| Pruebas integración | SRC + SGCF + SIU + SST funcionando juntos | Proveedor + Metro Sabanas | Puesta marcha |
| Pruebas carga | 20.724 transacciones/día simuladas | Proveedor | Puesta marcha |
| Pruebas seguridad | Pentesting, vulnerabilidades | Auditor externo | Pre-operación |

---

## 6. PLAN DE GESTIÓN DE COMUNICACIONES

### 6.1 Estructura de Comunicación

| Reunión | Frecuencia | Participantes | Formato | Responsable |
|:--------|:-----------|:--------------|:--------|:------------|
| Reunión proyecto | Semanal | Jelkin + ZEUS + Diana (INNOVADATACO) | Virtual | Jelkin |
| Reunión cliente | Semanal | Jelkin + Diana Baquero + Ericia | Presencial/Virtual | Jelkin |
| Informe avance | Quincenal | Todos los interesados | Documento | ZEUS |
| Comité cambios | Bajo demanda | Jelkin + Diana Baquero + Oscar Viana | Presencial | Jelkin |
| Reunión Alcaldía | Mensual | Jelkin + Secretario Movilidad | Presencial | Jelkin |

### 6.2 Canales de Comunicación

| Canal | Uso | Frecuencia |
|:------|:----|:-----------|
| Correo electrónico | Formal, documentos, actas | Diario |
| Telegram (grupo proyecto) | Rápido, decisiones, alertas | Diario |
| Google Drive | Documentos, versiones, evidencias | Continuo |
| GitHub (este repo) | Gestión proyecto, seguimiento | Continuo |
| Reuniones presenciales | Decisiones críticas, cierres | Según necesidad |

---

## 7. PLAN DE GESTIÓN DE ADQUISICIONES

### 7.1 Proceso de Contratación (Referencia)

| Etapa | Descripción | Duración Estimada |
|:------|:------------|:------------------|
| 1. Estudios previos | Justificación, presupuesto, pliegos | 2-3 meses |
| 2. Publicación | Pliego condiciones, convocatoria | 1 mes |
| 3. Evaluación | Ofertas técnicas y financieras | 1-2 meses |
| 4. Negociación | Ajustes, adiciones, OTROSÍ | 2-3 semanas |
| 5. Firma | Contrato, garantías, pólizas | 2-3 semanas |
| 6. Ejecución | 9 meses + 6 liquidación | 15 meses |

### 7.2 Forma de Pago (Hitos)

| Hito | % | Condición | Valor Estimado (COP) |
|:----:|:-:|:----------|:--------------------:|
| 1 | 20% | Licencias, capacitación, parametrización, piloto escritorio | ~$758.751.391 |
| 2 | 20% | Montaje piloto escritorio kit completo | ~$758.751.391 |
| 3 | 20% | Entrega equipos en oficinas Metro Sabanas | ~$758.751.391 |
| 4 | 30% | Puesta operación recaudo + control flota | ~$1.138.127.086 |
| 5 | 10% | Instalación equipos a bordo | ~$379.375.695 |

---

## 8. PLAN DE GESTIÓN DE RECURSOS

### 8.1 Equipo INNOVADATACO

| Rol | Nombre | Dedicación | Responsabilidades |
|:----|:-------|:-----------|:------------------|
| Director Proyecto | Jelkin Zair Carrillo Franco | 50% | Relación cliente, decisiones, aprobaciones |
| Asesor Jurídica | Diana Marcela Cáceres Valderrama | 20% | Revisión normativa, riesgos legales |
| Asesor Tecnología | ZEUS (Agente IA) | 100% | Análisis, diseño, documentación, seguimiento |
| Consultor externo (opcional) | Por definir | Según necesidad | Especialista ITS, validación técnica |

### 8.2 Recursos Cliente (Metro Sabanas)

| Rol | Nombre | Dedicación | Responsabilidades |
|:----|:-------|:-----------|:------------------|
| Gerente proyecto | Diana Carolina Baquero | 30% | Coordinación, aprobaciones, información |
| Representante legal | Oscar Iván Viana | 10% | Aprobaciones legales, firmas |
| Asesora operaciones | Ericia Barrios | 20% | Requerimientos operativos, validación |
| Interventoría | Por definir | 100% | Supervisión, control, certificación |

---

## 9. PLAN DE GESTIÓN DE CAMBIOS

### 9.1 Proceso de Control de Cambios

```
1. Solicitud de cambio → Formato estándar
2. Análisis de impacto → Alcance, tiempo, costo, calidad, riesgos
3. Decisión CCB (Change Control Board) → Jelkin + Diana Baquero + Oscar Viana
4. Aprobación / Rechazo / Diferido
5. Implementación aprobada
6. Verificación y cierre
```

### 9.2 CCB (Comité Control Cambios)

| Rol | Nombre | Voto |
|:----|:-------|:----:|
| Presidente | Jelkin Zair Carrillo Franco | Aprobador |
| Miembro | Diana Carolina Baquero Tobías | Aprobador |
| Miembro | Oscar Iván Viana Gómez | Aprobador |
| Asesor técnico | ZEUS / INNOVADATACO | Consultivo |

---

## 10. CRITERIOS DE CIERRE

| Criterio | Descripción | Verificación |
|:---------|:------------|:-------------|
| Documentación completa | Todos los entregables aprobados | Checklist EDT |
| Transferencia conocimiento | Personal Metro Sabanas capacitado | Actas capacitación |
| Satisfacción cliente | Encuesta ≥ 4.5/5 | Encuesta formal |
| Sin pendientes críticos | Issues resueltos o transferidos | Registro issues |
| Lecciones aprendidas | Documento aprobado | Acta cierre |
| Aprobación formal | Acta de cierre firmada | Firma de partes |

---

**Documento generado por ZEUS — Agente IA Estratégico INNOVADATACO**
**Fecha:** 2026-05-29
**Versión:** 1.0

---

> **"ZEUS online. La empresa está operando."** ⚡
