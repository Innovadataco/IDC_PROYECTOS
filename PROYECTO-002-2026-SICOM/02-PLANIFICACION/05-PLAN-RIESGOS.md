# PLAN DE RIESGOS — EMPALME SICOM

## 1. METODOLOGÍA

Identificación → Análisis (Probabilidad × Impacto) → Respuesta → Monitoreo

## 2. REGISTRO DE RIESGOS

| ID | Riesgo | Probabilidad | Impacto | Estrategia | Mitigación | Responsable | Fecha Límite |
|----|--------|--------------|---------|------------|------------|-------------|--------------|
| R1 | INTERNEXA no entrega documentación completa | ALTA | CRÍTICO | Mitigar | Solicitud formal con plazos, escalamiento a MME | Jelkin | 02 jun |
| R2 | INTERNEXA no facilita acceso a plataformas | ALTA | CRÍTICO | Mitigar | Carta formal, NDAs firmados, escalamiento | Jelkin | 04 jun |
| R3 | Código fuente incompleto o sin documentación | MEDIA | CRÍTICO | Mitigar | Validación temprana, checklist, pruebas compilación | Líder Técnico | 08 jun |
| R4 | Backups corruptos o irreversibles | MEDIA | CRÍTICO | Mitigar | Validación inmediata, prueba restore, backup alterno | DBA | 08 jun |
| R5 | Equipo CI2 no alcanza competencias requeridas | MEDIA | ALTO | Mitigar | Shadowing intensivo, capacitación adicional | Jelkin | 20 jun |
| R6 | Fallo en corte de migración | BAJA | CRÍTICO | Mitigar | Plan rollback, ventana extendida, equipo 7×24 | Jelkin | 30 jun |
| R7 | Incumplimiento de ANS en primer mes | MEDIA | ALTO | Transferir | Monitoreo intensivo, planes de choque | Monitoreo | 31 jul |
| R8 | Pérdida de conocimiento por rotación de personal | MEDIA | ALTO | Mitigar | Documentación continua, shadowing cruzado | Jelkin | Continuo |
| R9 | Cambios de alcance no documentados | MEDIA | ALTO | Mitigar | Gestión de cambios formal, actas, trazabilidad | Jelkin | Continuo |
| R10 | Problemas de licenciamiento | BAJA | ALTO | Mitigar | Inventario temprano, verificación propiedad | Legal | 01 jun |
| R11 | Brecha de seguridad durante transición | BAJA | CRÍTICO | Mitigar | Controles duales, monitoreo, NDAs, auditoría | Seguridad | Continuo |
| R12 | Retraso en cronograma por dependencias externas | ALTA | ALTO | Mitigar | Seguimiento diario, buffer, escalamiento temprano | Jelkin | Continuo |

## 3. UMBRALES DE RIESGO

| Nivel | Umbral | Acción |
|-------|--------|--------|
| 🔴 Crítico | Prob × Imp = Crítico | Escalar a Luis + Elizabeth |
| 🟡 Alto | Prob × Imp = Alto | Plan de acción inmediato |
| 🟢 Medio | Prob × Imp = Medio | Monitoreo semanal |
