# Registro de Incidencias — PROYECTO-005
**Proyecto:** Protección Infantil (Semáforo de Confianza)  
**Fecha:** 14 de junio de 2026  
**Auditor:** ZEUS

---

## INC-001: Declaración Incorrecta de Estado del Módulo 001

| Campo | Valor |
|-------|-------|
| **ID** | INC-001 |
| **Fecha detección** | 2026-06-14 |
| **Severidad** | 🔴 Crítica |
| **Estado** | Abierta |
| **Responsable** | ODIN |
| **Descripción** | ODIN declaró el Módulo 001 como "COMPLETADO" en spec.md, plan.md, tasks.md y README.md cuando el código real solo está al 65%. 12 de 27 tasks marcadas ✅ no están implementadas en código. |
| **Impacto** | CEO toma decisiones estratégicas basadas en información falsa. Riesgo de avanzar al Módulo 002 con base inestable. |
| **Causa raíz** | No hay proceso de validación formal. ODIN no tiene DoD checklist. No hay revisión por ZEUS antes de declarar "completado". |
| **Acción correctiva** | 1. Corregir estado de documentación a "65% — En corrección" 2. Implementar DoD checklist obligatorio 3. Implementar Acta de Validación firmada por ZEUS |
| **Deadline** | Inmediato |
| **Evidencia** | `docs/auditoria/ACTA-CORRECCION-ODIN-001.md` |

---

## INC-002: Bug de Seguridad — Rate Limiting Incorrecto

| Campo | Valor |
|-------|-------|
| **ID** | INC-002 |
| **Fecha detección** | 2026-06-14 |
| **Severidad** | 🔴 Crítica |
| **Estado** | Abierta |
| **Responsable** | ODIN |
| **Descripción** | Rate limiting configurado con ventana de 1 minuto (5 req/min) en lugar de 1 hora (5 req/hr) como exige SPEC-001 §8. Además, la IP del cliente se usa en texto plano como clave de rate limit, violando el principio de anonimato. |
| **Impacto** | Un atacante puede enviar 300 reportes/hora en lugar de 5. La IP queda en texto plano en Redis/memoria, comprometiendo anonimato del reportante. |
| **Causa raíz** | Error de implementación. No se verificó el spec durante el desarrollo. No hay test de verificación de rate limit. |
| **Acción correctiva** | 1. Cambiar `RateLimitItemPerMinute(5)` → `RateLimitItemPerHour(5)` 2. Hashear IP con SHA-256 antes de usar como clave 3. Añadir test de verificación |
| **Deadline** | 1 día |
| **Evidencia** | `app/services/rate_limit.py`, `app/routers/reportes.py` |

---

## INC-003: Modelo de Datos Incompleto

| Campo | Valor |
|-------|-------|
| **ID** | INC-003 |
| **Fecha detección** | 2026-06-14 |
| **Severidad** | 🔴 Crítica |
| **Estado** | Abierta |
| **Responsable** | ODIN |
| **Descripción** | El modelo `Report` no incluye campos que SPEC-001 exige: `category`, `consent_location`, `city`, `country`, `evidence_media_url`. El timestamp no se trunca a franjas de 6 horas. |
| **Impacto** | Bloquea Módulo 003 (IA Triage necesita categorías) y Módulo 004 (Clustering necesita geolocalización). |
| **Causa raíz** | Modelo implementado antes de leer spec completo. No hay migración de datos planificada. |
| **Acción correctiva** | 1. Diseñar nuevo modelo con todos los campos 2. Crear migración Alembic 3. Actualizar schemas, routers, tests 4. Documentar en ADR si hay cambio de arquitectura |
| **Deadline** | 2 días |
| **Evidencia** | `app/models.py`, `app/schemas.py`, `specs/001-registro-anonimo/spec.md` §7 |

---

## INC-004: Frontend No Cumple con SPEC-001

| Campo | Valor |
|-------|-------|
| **ID** | INC-004 |
| **Fecha detección** | 2026-06-14 |
| **Severidad** | 🔴 Crítica |
| **Estado** | Abierta |
| **Responsable** | ODIN |
| **Descripción** | `ReportForm.jsx` es un MVP de texto que no incluye: selector de categorías (6 opciones), upload de archivos con drag & drop, strip EXIF, honeypot field, review step, copiar hash al portapapeles, página de error dedicada. |
| **Impacto** | UX pobre. No cumple con el flujo de usuario definido en SPEC-001 §2. Funcionalidad core incompleta. |
| **Causa raíz** | Frontend desarrollado como MVP rápido sin seguir spec detallado. No hay proceso de validación de UI vs. spec. |
| **Acción correctiva** | 1. Rehacer formulario con todos los componentes del spec 2. Dividir en sub-componentes 3. Tests E2E para cada componente |
| **Deadline** | 3 días |
| **Evidencia** | `src/frontend/src/components/ReportForm.jsx`, `specs/001-registro-anonimo/spec.md` §2 |

---

## INC-005: Infraestructura Incompleta

| Campo | Valor |
|-------|-------|
| **ID** | INC-005 |
| **Fecha detección** | 2026-06-14 |
| **Severidad** | 🟡 Media |
| **Estado** | Abierta |
| **Responsable** | ODIN |
| **Descripción** | Docker Compose no incluye PostgreSQL, Redis, ni Nginx. No hay TLS 1.3. Dockerfile es single-stage. SQLite por defecto en .env.example. |
| **Impacto** | No es deployable a producción. SQLite por defecto puede usarse accidentalmente en prod. No hay clustering de Redis para rate limit. |
| **Causa raíz** | Infraestructura postergada. No hay ambiente de staging configurado. |
| **Acción correctiva** | 1. Añadir PostgreSQL, Redis, Nginx a docker-compose 2. Configurar Nginx con access_log off 3. Crear Dockerfile multi-stage 4. Cambiar .env.example a PostgreSQL 5. Validación de ambiente (rechazar SQLite en prod) |
| **Deadline** | 2 días |
| **Evidencia** | `docker-compose.yml`, `Dockerfile`, `.env.example` |

---

## INC-006: Sin Documentación de Avances y Metodología

| Campo | Valor |
|-------|-------|
| **ID** | INC-006 |
| **Fecha detección** | 2026-06-14 |
| **Severidad** | 🟡 Media |
| **Estado** | Abierta |
| **Responsable** | ODIN |
| **Descripción** | No hay lecciones aprendidas, bitácora de avances, registro de decisiones, template de PR, checklist de calidad. ODIN trabaja sin metodología documentada. |
| **Impacto** | Trabajo opaco. No hay trazabilidad. No se aprende de errores. No hay proceso de revisión. ZEUS no puede auditar sin documentación. |
| **Causa raíz** | No hay template de metodología en el repo. No se exigió documentación de avances desde el inicio. |
| **Acción correctiva** | 1. Crear `METODOLOGIA-ODIN.md` 2. Crear `LECCIONES-001.md` 3. Crear bitácora de avances 4. Crear template de PR 5. Crear checklist de DoD |
| **Deadline** | 1 día |
| **Evidencia** | Estructura de repo — carpeta `docs/` solo tiene ADRs |

---

## INC-007: Dependencia Fantasma (slowapi)

| Campo | Valor |
|-------|-------|
| **ID** | INC-007 |
| **Fecha detección** | 2026-06-14 |
| **Severidad** | 🟢 Baja |
| **Estado** | Abierta |
| **Responsable** | ODIN |
| **Descripción** | `slowapi>=0.1.9` está en `requirements.txt` pero no se usa en el código. Se usa `limits` directamente. |
| **Impacto** | Dependencia no auditada. Riesgo de vulnerabilidades no detectadas. |
| **Acción correctiva** | Eliminar `slowapi` de `requirements.txt` |
| **Deadline** | 30 minutos |
| **Evidencia** | `requirements.txt`, `app/services/rate_limit.py` |

---

## 📊 Resumen de Incidencias

| Severidad | Cantidad | Estado |
|-----------|----------|--------|
| 🔴 Crítica | 4 | 4 abiertas |
| 🟡 Media | 2 | 2 abiertas |
| 🟢 Baja | 1 | 1 abierta |
| **Total** | **7** | **7 abiertas** |

---

> **Auditor:** ZEUS | **Fecha:** 14 de junio de 2026  
> **ZEUS online. Las incidencias están registradas.** ⚡
