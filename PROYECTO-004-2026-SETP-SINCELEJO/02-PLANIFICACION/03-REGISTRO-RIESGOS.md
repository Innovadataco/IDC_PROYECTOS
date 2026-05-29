# REGISTRO DE RIESGOS
## PROYECTO 004-2026-SETP-SINCELEJO

---

## 1. RIESGOS TÉCNICOS

| ID | Riesgo | Descripción | Probabilidad | Impacto | Estrategia | Acción Mitigación | Responsable | Estado |
|:--:|:-------|:------------|:------------:|:-------:|:-----------|:------------------|:------------|:------:|
| R1 | Demanda insuficiente | Pasajeros reales < 20.724/día proyectados | ALTA | CRÍTICO | Mitigar | Piloto gradual, ajuste frecuencias, campaña comunicaciones, descuento tarifas inicial | Metro Sabanas | Activo |
| R2 | Falla conectividad celular | 4G/5G insuficiente en Sincelejo para 46 buses | ALTA | ALTO | Mitigar | Redundancia 4G/5G + radio trunking en corredores principales, pruebas de señal previas | Proveedor tech | Activo |
| R3 | Ciberataque a recaudo | Ataque a SRC, robo datos, fraude transaccional | MEDIA | CRÍTICO | Mitigar | HSM/KMS, segmentación red, cifrado end-to-end, auditoría seguridad, pentesting anual | Proveedor tech | Activo |
| R4 | Interoperabilidad limitada | APIs cerradas, dificultad integración futura | MEDIA | MEDIO | Mitigar | Estándares abiertos REST/GraphQL/MQTT desde diseño, documentación APIs, contrato de interoperabilidad | INNOVADATACO | Activo |
| R5 | Obsolescencia tecnológica | Tecnología queda obsoleta en 3-5 años | MEDIA | MEDIO | Mitigar | Licencias perpetuas, arquitectura cloud-first, actualizaciones continuales, roadmap tecnológico 5 años | INNOVADATACO | Activo |
| R6 | Falla validadores | Validadores no funcionan en condiciones reales | BAJA | ALTO | Mitigar | Pruebas FAT rigurosas, garantía 3 años, stock repuestos, soporte 24/7 | Proveedor tech | Activo |
| R7 | Incompatibilidad flota-tech | Carrocería no compatible con equipos ITS | MEDIA | ALTO | Mitigar | Pre-alambrado desde fábrica, especificaciones integradas flota-tech, pruebas SAT conjuntas | Proveedor flota | Activo |
| R8 | Escasez proveedores ITS | Pocos oferentes en licitación | BAJA | MEDIO | Aceptar | RFI amplio, licitación nacional, plazo amplio para ofertas, flexibilidad técnica | Metro Sabanas | Activo |
| R9 | Dependencia cloud | Falla proveedor cloud (AWS/Azure/GCP) | BAJA | CRÍTICO | Mitigar | Multi-cloud o backup on-premise, SLA ≥ 99.9%, DR plan, data sovereignty | Proveedor tech | Activo |
| R10 | Precisión GPS baja | GPS > 10m error en zonas urbanas densas | MEDIA | MEDIO | Mitigar | GNSS multi-constelación, antenas externas, fusión sensores, mapas de precisión | Proveedor tech | Activo |

---

## 2. RIESGOS FINANCIEROS

| ID | Riesgo | Descripción | Probabilidad | Impacto | Estrategia | Acción Mitigación | Responsable | Estado |
|:--:|:-------|:------------|:------------:|:-------:|:-----------|:------------------|:------------|:------:|
| R11 | Inestabilidad FEST | Subsidio no garantizado o insuficiente | ALTA | ALTO | Mitigar | Acuerdo formal Nación-Municipio, fondo reserva 6 meses, tarifa social alternativa | Metro Sabanas | Activo |
| R12 | Sobrecosto tecnología | Implementación > $3.800M presupuesto | MEDIA | ALTO | Mitigar | Especificaciones claras, penalidades sobrecosto, contingencia 8%, control interventoría | Metro Sabanas | Activo |
| R13 | Rentabilidad operadores | Ingresos < costos operativos | ALTA | CRÍTICO | Mitigar | Modelo tarifario flexible, FEST robusto, eficiencia operativa, marketing para demanda | Metro Sabanas | Activo |
| R14 | Retraso pagos hitos | Metro Sabanas no paga a tiempo | MEDIA | MEDIO | Mitigar | Facturación clara, certificaciones rápidas, fondo rotativo, cláusulas mora | Metro Sabanas | Activo |
| R15 | Cambio TRM | Si pago en USD, tipo de cambio fluctúa | BAJA | MEDIO | Transferir | Contrato en COP, cláusula TRM si USD, seguro cambiario | Metro Sabanas | Activo |
| R16 | Costos energía | Subsidio combustible/energía no sostenible | MEDIA | MEDIO | Mitigar | Flota GNV/eléctrica, eficiencia energética, contrato a largo plazo | Operador | Activo |

---

## 3. RIESGOS OPERATIVOS

| ID | Riesgo | Descripción | Probabilidad | Impacto | Estrategia | Acción Mitigación | Responsable | Estado |
|:--:|:-------|:------------|:------------:|:-------:|:-----------|:------------------|:------------|:------:|
| R17 | Retraso adquisición flota | 46 buses no listos para instalar tech | MEDIA | ALTO | Mitigar | Cronograma integrado flota-tech, hitos sincronizados, penalidades retraso, patio temporal | Metro Sabanas | Activo |
| R18 | Resistencia mototaxismo | Bloqueos, intimidación, competencia desleal | ALTA | MEDIO | Mitigar | Programa gestión motocicletas, diálogo social, integración gradual, comunicación ciudadana | Metro Sabanas + Operador | Activo |
| R19 | Falta conductores | No se consiguen 100+ conductores calificados | MEDIA | ALTO | Mitigar | Escuela conductores SETP, incentivos salariales, convenio SENA, certificación | Operador | Activo |
| R20 | Fallas mantenimiento | Buses fuera servicio > 10% | MEDIA | MEDIO | Mitigar | Talleres propios, convenio carrocera, stock repuestos, preventivo programado | Operador | Activo |
| R21 | Accidentes operacionales | Incidentes con pasajeros o terceros | MEDIA | ALTO | Mitigar | Seguro obligatorio, capacitación seguridad, cámaras videovigilancia, protocolos emergencia | Operador | Activo |
| R22 | Clima adversos | Lluvias, inundaciones afectan operación | ALTA | MEDIO | Aceptar | Plan contingencia climático, rutas alternas, comunicación usuarios, seguro | Operador | Activo |
| R23 | Vandalismo | Daño equipos a bordo, paraderos | MEDIA | MEDIO | Mitigar | Cámaras, botón pánico, seguro, diseño antivandalismo, patrullaje | Operador | Activo |

---

## 4. RIESGOS LEGALES Y REGULATORIOS

| ID | Riesgo | Descripción | Probabilidad | Impacto | Estrategia | Acción Mitigación | Responsable | Estado |
|:--:|:-------|:------------|:------------:|:-------:|:-----------|:------------------|:------------|:------:|
| R24 | Cambio normativo | Nuevo decreto modifica SETP | BAJA | ALTO | Transferir | Monitoreo legislativo, cláusulas contractuales de ajuste, abogado especializado | INNOVADATACO | Activo |
| R25 | Revocatoria permiso | Nivel de servicio D por 3 meses consecutivos | BAJA | CRÍTICO | Mitigar | Monitoreo KPIs, planes mejoramiento, interventoría estricta, cumplimiento D. 1079/2015 | Operador | Activo |
| R26 | Incumplimiento Decreto 482 | Sanciones por no cumplir condiciones | MEDIA | ALTO | Mitigar | Checklist cumplimiento, auditoría interna, asesoría jurídica, documentación | Metro Sabanas | Activo |
| R27 | Reclamos usuarios | PQRS masivos, demandas colectivas | MEDIA | MEDIO | Mitigar | App PQRS, call center, defensor del usuario, conciliación, seguro | Metro Sabanas | Activo |
| R28 | Protección datos | Violación Ley 1581 de 2012 (datos personales) | MEDIA | ALTO | Mitigar | Política datos, consentimiento informado, cifrado, auditoría, DPO designado | Proveedor tech | Activo |
| R29 | Propiedad intelectual | Disputas sobre software, mapping, datos | BAJA | MEDIO | Transferir | Contrato claro de propiedad, cláusulas IP, transferencia completa a Metro Sabanas | INNOVADATACO | Activo |

---

## 5. RIESGOS ESTRATÉGICOS

| ID | Riesgo | Descripción | Probabilidad | Impacto | Estrategia | Acción Mitigación | Responsable | Estado |
|:--:|:-------|:------------|:------------:|:-------:|:-----------|:------------------|:------------|:------:|
| R30 | Cambio gobierno municipal | Nuevo alcalde no apoya SETP | MEDIA | ALTO | Mitigar | Acuerdo interinstitucional, CONPES, compromiso multianual, visibilidad social | Metro Sabanas | Activo |
| R31 | Competencia privada | App tipo Uber/Didi entran al mercado | MEDIA | MEDIO | Aceptar | Diferenciación servicio público, integración, tarifas competitivas, calidad | Metro Sabanas | Activo |
| R32 | Reputación INNOVADATACO | Falla proyecto daña marca | BAJA | CRÍTICO | Mitigar | Calidad documentación, supervisión, honestidad en evaluaciones, respaldo legal | INNOVADATACO | Activo |
| R33 | Dependencia proveedor único | Vendor lock-in tecnológico | MEDIA | ALTO | Mitigar | Estándares abiertos, datos propiedad Metro Sabanas, contrato salida, interoperabilidad | INNOVADATACO | Activo |

---

## 6. PLAN DE CONTINGENCIAS

| Riesgo | Plan de Contingencia | Gatillo | Responsable |
|:-------|:--------------------|:--------|:------------|
| R1 (Demanda) | Si < 50% demanda en 6 meses: reducir frecuencias, activar FEST, campaña agresiva | 3 meses operación | Metro Sabanas |
| R2 (Conectividad) | Si falla 4G: activar radio trunking, WiFi paraderos, comunicación manual | 2 fallas semana | Proveedor tech |
| R3 (Ciberataque) | Si ataque: aislar sistema, activar DR, notificar autoridades, restaurar backup | Detección ataque | Proveedor tech |
| R11 (FEST) | Si no hay FEST: ajuste tarifa técnica, negociación con Nación, reducir servicio | 3 meses sin pago | Metro Sabanas |
| R17 (Flota) | Si retraso flota: adelantar tech centro control, capacitación, simuladores | 1 mes retraso | Metro Sabanas |
| R18 (Mototaxismo) | Si bloqueos: diálogo mesa de concertación, policía, medios, integración gradual | 1 bloqueo | Metro Sabanas |

---

## 7. RESERVA DE CONTINGENCIA

| Tipo | % del Presupuesto | Valor (COP) | Uso |
|:-----|:-----------------|------------:|:----|
| Reserva técnica | 8% | ~$303.500.556 | Riesgos técnicos, sobrecostos |
| Reserva de gestión | 5% | ~$189.687.848 | Riesgos de proyecto, ajustes |
| **TOTAL** | **13%** | **~$493.188.404** | |

---

## 8. MONITOREO DE RIESGOS

| Frecuencia | Actividad | Responsable |
|:-----------|:----------|:------------|
| Diaria | Revisión issues técnicos, alertas | ZEUS / Proveedor |
| Semanal | Actualización registro riesgos | ZEUS |
| Quincenal | Revisión umbrales, tendencias | Jelkin + ZEUS |
| Mensual | Reporte riesgos a Metro Sabanas | Jelkin |
| Bajo demanda | CCB para riesgos críticos | Jelkin + Diana Baquero + Oscar Viana |

---

**Documento generado por ZEUS — Agente IA Estratégico INNOVADATACO**
**Fecha:** 2026-05-29
**Versión:** 1.0

---

> **"ZEUS online. La empresa está operando."** ⚡
