# REQUISITOS INICIALES — Protección Infantil Comunitaria

## Proyecto: 005 — Protección Infantil Comunitaria
**Código:** IDC_2026_05  
**Fecha:** 13 de junio de 2026  
**Versión:** 1.0  
**Autor:** ZEUS EOS (basado en SPEC-001 de ODIN)  
**Aprobador:** Jelkin Zair Carrillo Franco (CEO)

---

## 1. REQUISITOS FUNCIONALES DE ALTO NIVEL (EPICS)

### EPIC-001: Registro Anónimo de Reportes (Módulo 001)
**Estado:** ✅ Completado

| ID | Requisito | Descripción | Prioridad | Módulo |
|----|-----------|-------------|-----------|--------|
| RF-001 | Crear reporte | El sistema permite enviar un reporte con identificador y descripción | Alta | 001 |
| RF-002 | Adjuntar evidencia | El sistema permite adjuntar evidencia opcional (texto o imagen) | Media | 001 |
| RF-003 | Generar hash de confirmación | El sistema genera un hash único como prueba de envío | Alta | 001 |
| RF-004 | Garantizar anonimato | El sistema NO almacena IP, user-agent, cookies ni metadata | Alta | 001 |
| RF-005 | Rate limiting | El sistema limita a 5 reportes por hora por IP | Media | 001 |
| RF-006 | Health check | El sistema expone endpoint de verificación de estado | Baja | 001 |

### EPIC-002: Panel de Administración (Módulo 002)
**Estado:** ⬜ Pendiente

| ID | Requisito | Descripción | Prioridad | Módulo |
|----|-----------|-------------|-----------|--------|
| RF-007 | Autenticación de administradores | Login seguro para personal autorizado | Alta | 002 |
| RF-008 | Lista de reportes | Visualizar reportes recibidos con desencriptación | Alta | 002 |
| RF-009 | Filtrar y buscar reportes | Búsqueda por fecha, estado, tipo de evidencia | Media | 002 |
| RF-010 | Cambiar estado de reporte | Marcar como: nuevo, en revisión, escalado, cerrado | Alta | 002 |
| RF-011 | Exportar reportes | Generar CSV/JSON de reportes para autoridades | Media | 002 |
| RF-012 | Dashboard de métricas | Visualizar estadísticas: reportes por día, semana, mes | Baja | 002 |

### EPIC-003: Notificaciones a Autoridades (Módulo 003)
**Estado:** ⬜ Pendiente

| ID | Requisito | Descripción | Prioridad | Módulo |
|----|-----------|-------------|-----------|--------|
| RF-013 | Configurar autoridades | Registrar entidades receptoras (ICBF, Fiscalía, Policía) | Alta | 003 |
| RF-014 | Alerta automática por severidad | Notificar inmediatamente si reporte cumple criterios de urgencia | Alta | 003 |
| RF-015 | Resumen periódico | Enviar resumen diario/semanal de reportes a autoridades | Media | 003 |
| RF-016 | Canal de notificación | Email, API webhook, o dashboard compartido | Media | 003 |
| RF-017 | Confirmación de recepción | Autoridad marca como "recibido" en el sistema | Baja | 003 |

### EPIC-004: Inteligencia Artificial y Scoring (Módulo 004)
**Estado:** ⬜ Pendiente

| ID | Requisito | Descripción | Prioridad | Módulo |
|----|-----------|-------------|-----------|--------|
| RF-018 | Scoring de reportes | Calificar reporte por urgencia/peligrosidad (1-10) | Alta | 004 |
| RF-019 | Detección de patrones | Identificar identificadores reportados múltiples veces | Alta | 004 |
| RF-020 | Clustering geográfico | Agrupar reportes por zona geográfica (si aplica) | Media | 004 |
| RF-021 | Análisis de tendencias | Visualizar evolución temporal de reportes | Baja | 004 |
| RF-022 | Detección de spam/falsos | Marcar reportes sospechosos de spam | Media | 004 |

---

## 2. REQUISITOS NO FUNCIONALES (NFR)

| ID | Requisito | Categoría | Criterio | Prioridad | Módulo |
|----|-----------|-----------|----------|-----------|--------|
| RNF-001 | Encriptación AES-256-GCM en reposo | Seguridad | Datos sensibles encriptados | Alta | 001-004 |
| RNF-002 | Headers de seguridad OWASP | Seguridad | HSTS, CSP, X-Frame, etc. | Alta | 001-004 |
| RNF-003 | Cobertura de tests ≥ 80% | Calidad | pytest + vitest | Alta | 001-004 |
| RNF-004 | Tiempo de respuesta < 500ms | Performance | 95 percentile | Media | 001-004 |
| RNF-005 | Sin cookies de tracking | Privacidad | No cookies ni localStorage | Alta | 001-004 |
| RNF-006 | Sin metadata identificable | Privacidad | No IP, no user-agent | Alta | 001-004 |
| RNF-007 | Disponibilidad 99.9% | Operación | Uptime en producción | Media | 003-004 |
| RNF-008 | Escalabilidad horizontal | Arquitectura | Docker + load balancer | Media | 003-004 |
| RNF-009 | Accesibilidad WCAG 2.1 AA | UX | Compatible con lectores de pantalla | Media | 001-004 |
| RNF-010 | Multi-idioma (español inicial) | Internacionalización | Estructura para i18n | Baja | 002-004 |

---

## 3. REGLAS DE NEGOCIO

| ID | Regla | Descripción |
|----|-------|-------------|
| RN-001 | Identificador obligatorio | Todo reporte debe tener al menos un identificador reportado y una descripción. |
| RN-002 | Evidencia limitada | La evidencia opcional solo puede ser de tipo `text` o `image`. |
| RN-003 | Hash único | El hash de confirmación debe ser único y no vinculable al reportante. |
| RN-004 | Rate limit | No se debe permitir más de 5 reportes por hora desde la misma IP. |
| RN-005 | Anonimato absoluto | No se debe almacenar ni procesar IP, user-agent, cookies ni device metadata. |
| RN-006 | Autenticación admin | Solo usuarios autorizados pueden acceder al panel de administración (Módulo 002). |
| RN-007 | Severidad mínima para alerta | Solo reportes con scoring ≥ 7 generan alerta inmediata a autoridades (Módulo 003-004). |
| RN-008 | Retención de datos | Los reportes se conservan mínimo 5 años por requerimiento legal colombiano. |

---

## 4. RESTRICCIONES TÉCNICAS

| ID | Restricción | Justificación |
|----|-------------|---------------|
| RT-001 | Stack definido: React 19 + FastAPI + PostgreSQL | Consistencia técnica y replicabilidad |
| RT-002 | Encriptación: AES-256-GCM + DEK por campo | Seguridad industrial, anonimato garantizado |
| RT-003 | Tests obligatorios: ≥ 80% cobertura | Calidad y mantenibilidad |
| RT-004 | Docker para deploy | Portabilidad y reproducibilidad |
| RT-005 | OpenAPI auto-generado por FastAPI | Documentación API siempre actualizada |
| RT-006 | Sin dependencias de tracking | Privacidad por diseño |

---

## 5. DEPENDENCIAS ENTRE REQUISITOS

```
RF-001 (Crear reporte)
  ├── RF-002 (Evidencia) [opcional]
  ├── RF-003 (Hash) [automático]
  ├── RF-004 (Anonimato) [obligatorio]
  └── RF-005 (Rate limit) [obligatorio]

RF-007 (Auth admin)
  └── RF-008 (Lista reportes)
      ├── RF-009 (Filtrar)
      ├── RF-010 (Cambiar estado)
      └── RF-011 (Exportar)

RF-013 (Configurar autoridades)
  └── RF-014 (Alerta automática)
      └── RF-015 (Resumen periódico)

RF-018 (Scoring)
  └── RF-019 (Patrones)
      ├── RF-020 (Clustering)
      └── RF-022 (Detección spam)
```

---

## 6. CRITERIOS DE ACEPTACIÓN GLOBALES

- [x] Todos los tests pasan (pytest + vitest) — Módulo 001 ✅
- [x] Cobertura backend ≥ 80% — Módulo 001 ✅
- [x] Documentación OpenAPI disponible en `/docs` — Módulo 001 ✅
- [ ] Checklist de seguridad OWASP completado — Pendiente revisión ZEUS
- [ ] Jelkin aprueba el demo — Pendiente
- [ ] Diana valida cumplimiento legal — Pendiente
- [ ] Code review aprobado por ZEUS — En progreso
- [ ] Artefactos PM2 actualizados — En progreso

---

> *Documento generado por ZEUS — Innovadataco*
