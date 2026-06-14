# INSTRUCCION-ODIN-004-EXCEPCION — Autorización para Avanzar Módulos 5 y 6

**Proyecto:** Semáforo de Confianza (005)  
**Código:** IDC_2026_05  
**Fecha emisión:** 2026-06-14 23:35 CST (Shanghai) / 10:35 (Bogotá)  
**Emisor:** Jelkin Zair Carrillo Franco (CEO Innovadataco)  
**Destinatario:** ODIN (CEO IA Dev)  
**Vía:** ZEUS (CEO PMO)  
**Prioridad:** 🔴 Alta  
**Estado:** ✅ EXCEPCIÓN FIRMADA  

---

## 1. DECISIÓN DEL CEO

**Jelkin Zair Carrillo Franco autoriza explícitamente a ODIN para avanzar con el desarrollo de los Módulos 5 y 6 del Proyecto 005, SIN esperar la validación formal del Módulo 004.**

Esta decisión overrides la INSTRUCCION-ODIN-004-CORRECCION emitida por ZEUS el 2026-06-14 13:20 CST.

---

## 2. RAZÓN DE LA EXCEPCIÓN

- El core funcional del Módulo 004 está implementado y operativo (geoip, perfiles, redes, endpoints, panel admin, tests).
- Las 3 correcciones pendientes (H-004.1, H-004.2, H-004.3) son deuda técnica menor que no bloquea la funcionalidad core.
- La prioridad empresarial es avanzar rápido en los módulos 5 y 6 para tener un MVP completo del Semáforo de Confianza.
- Las correcciones del Módulo 004 se abordarán en paralelo o posteriormente, según disponibilidad.

---

## 3. ALCANCE AUTORIZADO

ODIN está autorizado para:

| Módulo | Descripción | Spec | Tasks |
|--------|-------------|------|-------|
| 005 | Panel Admin Institucional | `specs/005-panel-admin/spec.md` | `specs/005-panel-admin/tasks.md` |
| 006 | Pasarela Institucional | `specs/006-pasarela-institucional/spec.md` | `specs/006-pasarela-institucional/tasks.md` |

**Branch:** `feature/v2-fullstack` (mismo branch del Módulo 004)

---

## 4. CONDICIONES DE LA EXCEPCIÓN

1. **Las 3 correcciones del Módulo 004 se documentan como deuda técnica** en `docs/DEUDAS-TECNICAS-004.md` (ODIN debe crear este archivo).
2. **No se declara el Módulo 004 como "COMPLETADO"** hasta que ZEUS valide las correcciones. Permanece en estado `⚠️ VALIDADO CON EXCEPCIÓN`.
3. **ODIN debe seguir el DoD de 12 items** para los Módulos 5 y 6.
4. **ZEUS auditará los Módulos 5 y 6 con el mismo rigor**, sin excepciones.
5. **Si se detecta fake completado en 5 o 6**, no habrá excepción — se rechaza y se corrige antes de cualquier avance.

---

## 5. DEUDA TÉCNICA DEL MÓDULO 004 (Pendiente)

| Hallazgo | Descripción | Prioridad | Estado |
|----------|-------------|-----------|--------|
| H-004.1 | TI-004.3 — Background job (Redis queue + worker) | Media | 🟡 Diferido |
| H-004.2 | TB-004.4 — Migración de datos históricos | Media | 🟡 Diferido |
| H-004.3 | TF-004.4 — Visualización de mapa SVG | Baja | 🟡 Diferido |

**Fecha límite para resolver deuda técnica:** 2026-06-21 (una semana).

---

## 6. FIRMA

**Autorizado por:** Jelkin Zair Carrillo Franco  
**Fecha:** 2026-06-14 23:35 CST (Shanghai) / 10:35 (Bogotá)  
**Método:** Vía ZEUS (mensaje de chat con confirmación explícita)  

> **"Procede ODIN. Avanza con 5 y 6. La deuda técnica del 4 queda registrada pero no bloquea."**

---

## 7. REGISTRO EN SINCRONIZACIÓN-MAESTRA

Esta excepción queda registrada en `SINCRONIZACION-MAESTRA.md` con timestamp y autorización.

---

> **ZEUS — CEO PMO**  
> **Fecha: 2026-06-14 23:35 CST (Shanghai) / 10:35 Bogotá**  
> **Excepción firmada por el CEO. Proceda.**
