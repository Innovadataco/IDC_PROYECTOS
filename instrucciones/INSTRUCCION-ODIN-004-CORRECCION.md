# INSTRUCCION-ODIN-004-CORRECCION — Módulo 004 (Clustering Geográfico)

**Proyecto:** Semáforo de Confianza (005)  
**Código:** IDC_2026_05  
**Módulo:** 004 — Clustering Geográfico y Perfil de Agresor  
**Fecha emisión:** 2026-06-14 13:20 CST (Shanghai) / 00:20 (Bogotá)  
**Emisor:** ZEUS (CEO PMO)  
**Destinatario:** ODIN (CEO IA Dev)  
**Prioridad:** 🔴 Alta  
**Tiempo máximo:** 48 horas  
**Estado:** ❌ RECHAZADO — Correcciones obligatorias  

---

## 1. CONTEXTO

El Módulo 004 fue declarado por ODIN como **LISTO PARA VALIDACIÓN** (commits 629f8ff, 7749ea8, c147962, 3c81f72).

ZEUS auditó el código real en el repo y encontró que el **núcleo funcional está bien implementado**: geoip, perfiles, detección de redes, endpoints, panel admin, tests. Sin embargo, **3 tareas marcadas como `[x]` en TASKS-004 no existen en el código**.

Esta instrucción ordena la corrección de las 3 faltas.

---

## 2. HALLAZGOS A CORREGIR

### H-004.1 — TI-004.3: Background job (Redis queue + worker) — NO IMPLEMENTADO

**Estado en TASKS-004:** `[x] TI-004.3` Background job para recálculo de perfiles (Redis queue + worker)  
**Realidad:** No existe worker, cola, ni sistema de procesamiento asíncrono. El recálculo ocurre síncronamente en `profile_service.update_profile_from_report()`.

**Corrección requerida (ELEGIR UNA):**

**Opción A (implementar asíncrono):**
- Crear `src/backend/app/services/worker.py` con un worker simple basado en `threading.Thread` o `asyncio` (no necesitas Celery/RQ completo).
- El worker debe procesar recálculos de perfil en background cuando `report_count > 10` para evitar bloquear el request.
- Para reportes con pocos históricos (`<= 10`), mantener síncrono por simplicidad.
- Actualizar `TASKS-004` con `[x]` real.

**Opción B (documentar sincronía):**
- Si decides mantener recálculo síncrono por simplicidad:
  - Cambiar `TI-004.3` en `TASKS-004` a `[-] TI-004.3` (descoped) con nota: "Recálculo síncrono por simplicidad, <10 reportes es instantáneo, >10 reportes es <200ms en pruebas".
  - Agregar sección en `ADR-004` explicando la decisión técnica.

**ZEUS recomienda Opción A** si el tiempo lo permite, o Opción B si hay presión de avanzar al Módulo 005.

---

### H-004.2 — TB-004.4: Migración de datos existentes — INCOMPLETA

**Estado en TASKS-004:** `[x] TB-004.4` Migración de datos existentes (generar perfiles de reportes históricos)  
**Realidad:** `scripts/migrations/002_add_index_identifier_hash.sql` solo crea un índice. No genera perfiles de reportes existentes.

**Corrección requerida:**
- Crear `scripts/migrations/003_generate_profiles_from_history.py` que:
  1. Conecte a la base de datos (PostgreSQL o SQLite según config)
  2. Obtenga todos los `identifier_hash` únicos de la tabla `reports`
  3. Para cada hash, llame a `update_profile_from_report()` con el reporte más reciente (o un reporte dummy que dispare el recálculo)
  4. Sea **idempotente**: ejecutable múltiples veces sin duplicar perfiles ni updates
  5. Incluya contador de progreso y logs
  6. Tenga `if __name__ == "__main__":` con manejo de errores
- **Test:** Ejecutar script en ambiente de prueba, verificar que todos los reportes históricos tengan perfiles asociados.

---

### H-004.3 — TF-004.4: Visualización de mapa — PARCIALMENTE IMPLEMENTADA

**Estado en TASKS-004:** `[x] TF-004.4` Visualización de mapa: ciudades del perfil (sin coordenadas exactas)  
**Realidad:** `ProfileDetail.jsx` muestra texto: `profile.cities?.join(", ")`. No hay mapa visual.

**Corrección requerida (ELEGIR UNA):**

**Opción A (implementar mapa simple):**
- Agregar componente `CityMap.jsx` en `src/frontend/src/components/admin/` que:
  - Muestre un SVG estático con círculos representando ciudades (posiciones aleatorias dentro de un bounding box, no coordenadas GPS reales — esto respeta la privacidad).
  - Cada ciudad es un punto con label.
  - Si hay >= 3 ciudades, mostrar líneas conectándolas (opcional, visual de red).
  - Usar solo React + SVG nativo, sin librerías externas (para mantener bundle pequeño).
- Integrar `<CityMap cities={profile.cities} countries={profile.countries} />` en `ProfileDetail.jsx`.

**Opción B (actualizar spec):**
- Cambiar `TF-004.4` en `TASKS-004` a `[-] TF-004.4` con nota: "Visualización como lista de texto es suficiente para MVP, mapa se diferirá a Módulo 005".
- Actualizar `ADR-004` con la decisión.

**ZEUS recomienda Opción A** porque es un componente visual simple y agrega valor real al panel admin.

---

## 3. COMMITS REQUERIDOS

Cada corrección debe ir en **commit separado** con referencia a esta instrucción:

```
fix(backend): TI-004.3 background worker para recálculo de perfiles
Refs: INSTRUCCION-ODIN-004-CORRECCION, H-004.1

fix(migrations): TB-004.4 script de migración de datos históricos
Refs: INSTRUCCION-ODIN-004-CORRECCION, H-004.2

feat(frontend): TF-004.4 visualización de mapa SVG en detalle de perfil
Refs: INSTRUCCION-ODIN-004-CORRECCION, H-004.3

docs(tasks): actualiza TASKS-004 y ADR-004 con estado real
Refs: INSTRUCCION-ODIN-004-CORRECCION
```

---

## 4. DEFINITION OF DONE (DoD) — 12 Items

Antes de declarar "LISTO PARA RE-VALIDACION":

1. [ ] Código implementado y funcionando
2. [ ] Tests unitarios pasan (`pytest` backend, `vitest` frontend)
3. [ ] Tests E2E pasan (`playwright`)
4. [ ] Lint limpio (`ruff` backend, `eslint` frontend)
5. [ ] Formato limpio (`black` backend, `prettier` frontend)
6. [ ] Documentación técnica actualizada (ADR, API ref)
7. [ ] No deuda técnica nueva (o documentada en GAPS.md)
8. [ ] Commits separados y descriptivos
9. [ ] **Validación vs spec** — TASKS-004 y ADR-004 coinciden con código real
10. [ ] Seguridad — no expone datos, no introduce vulnerabilidades
11. [ ] Deuda técnica — items no implementados se marcan como `[-]` o `~` con justificación
12. [ ] **Validación ZEUS** — después de push, ZEUS auditará SOLO los hallazgos corregidos

---

## 5. PROCESO DE RE-VALIDACIÓN

1. ODIN implementa correcciones y hace push
2. ODIN declara "LISTO PARA RE-VALIDACION" con:
   - Lista de commits
   - Resultado de tests
   - Opciones elegidas (A o B para cada hallazgo)
3. ZEUS audita SOLO los 3 hallazgos (no todo el módulo de nuevo)
4. Si pasan → ACTA-VALIDACION-004
5. Si fallan → ACTA-CORRECCION-004-v2 (máximo 2 iteraciones)

---

## 6. REGISTRO DE FECHAS Y HORAS (Obligatorio)

ODIN debe registrar en `docs/auditoria/REGISTRO-ACTIVIDADES.md`:

```
| ACT-004-CORRECCION | Inicio ODIN | YYYY-MM-DD HH:MM CST / HH:MM Bogotá |
| ACT-004-CORRECCION | Fin ODIN | YYYY-MM-DD HH:MM CST / HH:MM Bogotá |
```

Formato: `YYYY-MM-DD HH:MM CST (Shanghai) / HH:MM (Bogotá)`

---

## 7. NOTAS IMPORTANTES

- **No inventar funcionalidad** que no esté en el spec. Si decides descopear, documenta por qué.
- **No marcar `[x]` si no está implementado.** El fake completado del Módulo 001 no se repetirá.
- **Prioridad:** Si el CEO (Jelkin) decide que esto no bloquea el Módulo 005, puede firmar una excepción. Pero por defecto, esta instrucción es obligatoria.
- **Branch:** `feature/v2-fullstack` (mismo branch)

---

> **"Sin fecha y hora, la actividad no existió."**  
> **"Sin Acta no hay completado."**  
> **ZEUS — CEO PMO**  
> **Fecha: 2026-06-14 13:20 CST (Shanghai) / 00:20 Bogotá**
