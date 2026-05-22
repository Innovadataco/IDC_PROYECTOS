# PLAN DE IMPLEMENTACIÓN — EMPALME SICOM

## 1. ESTRATEGIA DE DESPLIEGUE

El empalme SICOM sigue una estrategia de **"Operación en Sombra + Corte Controlado"**:

1. Fase 0-1: Gobierno + Inventario (sin tocar producción)
2. Fase 2: Validación de accesos y backups (sin tocar producción)
3. Fase 3: Shadowing (observar operación real)
4. Fase 4: Replicación en ambiente CI2 (paralelo)
5. Fase 5: Corte controlado (30 junio, ventana 00:00-20:00)
6. Fase 6: Operación CI2 con monitoreo intensivo

## 2. CRONOGRAMA DEL CORTE (30 junio 2026)

| Hora | Actividad | Responsable | Duración |
|------|-----------|-------------|----------|
| 00:00 | Inicio ventana de corte | Jelkin + INTERNEXA + CI2 | — |
| 00:00-02:00 | Detención graceful servicios INTERNEXA | SysAdmin INTERNEXA | 2h |
| 02:00-04:00 | Migración final de datos | DBA CI2 + INTERNEXA | 2h |
| 04:00-06:00 | Activación servicios en CI2 | SysAdmin CI2 | 2h |
| 06:00-08:00 | Validación servicios críticos | QA CI2 | 2h |
| 08:00-10:00 | Pruebas de integración | Devs CI2 | 2h |
| 10:00-12:00 | Pruebas Call Center y mesa de servicio | Call Center + Mesa CI2 | 2h |
| 12:00-14:00 | Monitoreo intensivo y ajustes | Monitoreo CI2 | 2h |
| 14:00-16:00 | Validación con usuarios clave MME | Usuarios MME | 2h |
| 16:00-18:00 | Documentación incidencias | Jelkin | 2h |
| 18:00 | **Decisión: GO / NO-GO** | Jelkin + Luis + Elizabeth | — |
| 18:00-20:00 | Activación completa o Rollback | Jelkin + INTERNEXA | 2h |
| 20:00-00:00 | Monitoreo post-corte | Equipo CI2 | 4h |
