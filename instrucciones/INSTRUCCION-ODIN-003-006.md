# INSTRUCCION-ODIN-003-006.md
**Proyecto:** PROYECTO-005: Semáforo de Confianza (Protección Infantil)  
**Módulos:** 003, 004, 005, 006 — Módulos Finales  
**Actividad:** ACT-003-006 — Implementación Módulos 3-6  
**Auditoría base:** ACTA-VALIDACION-ODIN-002-v2.md  
**Asignado:** ODIN (CEO IA Dev)  
**Aprobador:** Jelkin Zair Carrillo Franco (CEO)  
**Fecha instrucción:** 2026-06-14 11:53 CST (Shanghai) / 10:53 (Bogotá)  
**Estado:** APROBADA ✅

---

## 1. CONTEXTO

**ACT-002 VALIDADO CON HALLAZGOS.** 2 hallazgos menores pendientes (TI-002.3 nginx cache, tests).

**Jelkin ordena:** ODIN avanza con Módulos 3, 4, 5 y 6 simultáneamente. No esperar corrección de hallazgos del Módulo 2.

**Nota:** Los hallazgos del Módulo 2 se corrigen en paralelo (ACT-002-CORRECCION) o después.

---

## 2. RESUMEN DE MÓDULOS

| Módulo | Nombre | Tasks | Complejidad | Dependencias |
|--------|--------|-------|-------------|--------------|
| 003 | IA Triage | ~40 | 🔴 Alta | Módulo 001 (reportes) |
| 004 | Clustering y Perfil | ~28 | 🟡 Media | Módulo 002 (consulta) |
| 005 | Panel Admin | ~38 | 🟡 Media | Módulos 001-004 |
| 006 | Pasarela Institucional | ~35 | 🔴 Alta | Módulos 001-005 |
| **TOTAL** | | **~141** | | |

---

## 3. ORDEN RECOMENDADO DE IMPLEMENTACIÓN

Aunque Jelkin autoriza paralelismo, ZEUS recomienda este orden por dependencias:

```
Módulo 003 (IA Triage) → Módulo 004 (Clustering) → Módulo 005 (Panel Admin) → Módulo 006 (Pasarela)
```

**Razón:**
- Módulo 003 genera scores que Módulo 004 consume
- Módulo 004 genera perfiles que Módulo 005 muestra
- Módulo 005 administra alertas que Módulo 6 envía

**Pero:** Jelkin tiene autoridad absoluta. Si ODIN quiere paralelismo, puede hacerlo.

---

## 4. ESPECIFICACIONES POR MÓDULO

### 4.1 MÓDULO 003: IA Triage (~40 tasks)

**Objetivo:** Clasificación automática de reportes con NLP y detección de grooming.

**Tasks clave:**
- Dataset: 1,500 ejemplos sintéticos (español colombiano)
- Modelo: Logistic Regression + Random Forest ensemble
- Métrica: AUC-ROC ≥ 0.80
- Fairness: Disparidad < 10% entre subgrupos
- Explicabilidad: SHAP values para scores > 0.7
- Endpoint: POST /api/analyze/{report_id} (async)
- Tiempo: < 500ms inferencia

**Commit esperado:** `feat(ia): TML-003.1..TML-003.23, TB-003.1..TB-003.8`

---

### 4.2 MÓDULO 004: Clustering y Perfil (~28 tasks)

**Objetivo:** Perfiles de identificadores, detección de redes, geoprocesamiento.

**Tasks clave:**
- Geocodificación: MaxMind GeoLite2 (local)
- Modelo: Profile + ProfileUpdate
- Algoritmo: Clustering por ciudades/países (is_network)
- Cache: Redis TTL 1h
- Endpoints: GET /api/profile/{hash}, /api/networks
- Frontend: Panel admin con mapa y timeline
- Background jobs: Recálculo de perfiles

**Commit esperado:** `feat(clustering): TCL-004.1..TCL-004.11, TB-004.1..TB-004.10`

---

### 4.3 MÓDULO 005: Panel Admin (~38 tasks)

**Objetivo:** Dashboard de administración con autenticación, métricas, audit trail.

**Tasks clave:**
- Auth: JWT + bcrypt + 2FA TOTP
- Roles: admin, supervisor, reviewer, viewer
- Dashboard: Cards + gráficos (doughnut, línea)
- Reportes: Tabla con filtros, paginación, desencriptación
- Audit trail: Cada acción registrada (login, decrypt, status change)
- Export: JSON + PDF (branding Innovadataco)
- Configuración: Umbrales de alerta, gestión de usuarios

**Commit esperado:** `feat(admin): TA-005.1..TA-005.9, TF-005.1..TF-005.24`

---

### 4.4 MÓDULO 006: Pasarela Institucional (~35 tasks)

**Objetivo:** Integración con autoridades (ICBF, Fiscalía, Policía), alertas automáticas, API gateway.

**Tasks clave:**
- Modelos: Institution, Alert, Digest
- Formatos: JSON, PDF, NCMEC CyberTipline v2 (XML)
- Alertas: Email automático por severidad (cron)
- Digest: Diario, semanal, mensual (08:00)
- API Gateway: Auth por API key, rate limiting 100/hr
- TLS 1.3 obligatorio
- Retry: 3 intentos con backoff exponencial

**Commit esperado:** `feat(pasarela): TB-006.1..TB-006.32`

---

## 5. REGLAS DE EJECUCIÓN

### R-001: 1 commit por módulo o por task
ODIN puede agrupar commits por módulo (no necesita 1 por task como en Módulo 002).
Formato: `feat(<scope>): <módulo> — <descripción>`

Ejemplos:
```
feat(ia): Módulo 003 — dataset sintético y modelo baseline
feat(clustering): Módulo 004 — geocodificación y modelo Profile
feat(admin): Módulo 005 — auth JWT + dashboard
feat(pasarela): Módulo 006 — alertas y API gateway
```

### R-002: Push por módulo completo
Cada vez que ODIN termine un módulo, hace push.
**No esperar a terminar los 4 módulos para hacer push.**

### R-003: Declarar "LISTO PARA VALIDACIÓN" por módulo
ODIN declara listo cuando un módulo está completo. ZEUS valida módulo por módulo.

### R-004: No tocar IDC_PROYECTOS
ODIN solo trabaja en el repo `Desarrollos`. ZEUS maneja `IDC_PROYECTOS`.

### R-005: Timestamp obligatorio
ODIN registra fecha/hora de fin de cada módulo.

### R-006: Rama correcta
ODIN trabaja en `feature/v2-fullstack`. Si hay conflicto, resolver.

---

## 6. DEFINICIÓN DE TERMINADO (DoD) POR MÓDULO

### Módulo 003 (IA Triage)
- [ ] Dataset de 1,500 ejemplos generado
- [ ] Modelo entrenado con AUC-ROC ≥ 0.80
- [ ] Fairness audit: disparidad < 10%
- [ ] Red-teaming: 0 falsos negativos de alto riesgo
- [ ] Endpoint /api/analyze/{report_id} funcional (async)
- [ ] SHAP explicabilidad para scores > 0.7
- [ ] Tests unitarios ≥ 80% cobertura
- [ ] Tiempo inferencia < 500ms
- [ ] ADR-003 aprobado

### Módulo 004 (Clustering)
- [ ] Geocodificación funcional (MaxMind GeoLite2)
- [ ] Modelo Profile implementado
- [ ] Algoritmo de clustering (is_network)
- [ ] Cache Redis para perfiles
- [ ] Endpoints de perfil protegidos (admin)
- [ ] Panel admin con mapa y timeline
- [ ] Tests E2E con Playwright
- [ ] ADR-004 aprobado

### Módulo 005 (Panel Admin)
- [ ] Auth JWT + 2FA funcional
- [ ] Dashboard con métricas y gráficos
- [ ] Lista de reportes con filtros y paginación
- [ ] Desencriptación con razón (audit trail)
- [ ] Export JSON + PDF
- [ ] Gestión de usuarios y roles
- [ ] Tests E2E: login → dashboard → reporte → decrypt → logout
- [ ] ADR-005 aprobado

### Módulo 006 (Pasarela)
- [ ] Modelos Institution, Alert, Digest
- [ ] Formatos JSON, PDF, NCMEC XML
- [ ] Alertas automáticas por severidad (cron)
- [ ] Digest diario/semanal/mensual
- [ ] API Gateway con auth por API key
- [ ] TLS 1.3 obligatorio
- [ ] Retry 3 intentos con backoff
- [ ] Tests de integración con mock SMTP y NCMEC
- [ ] ADR-006 aprobado

---

## 7. EJEMPLO DE FLUJO

```bash
# 1. Asegurarse de estar en rama correcta
git checkout feature/v2-fullstack

# 2. Implementar Módulo 003 (IA Triage)
# ... trabajo ...
git add -A
git commit -m "feat(ia): Módulo 003 — IA Triage completo"
git push origin feature/v2-fullstack

# 3. Declarar "LISTO PARA VALIDACIÓN MÓDULO 003"

# 4. ZEUS valida, genera acta

# 5. Implementar Módulo 004 (Clustering)
# ... trabajo ...
git add -A
git commit -m "feat(clustering): Módulo 004 — Clustering y Perfil completo"
git push origin feature/v2-fullstack

# 6. Declarar "LISTO PARA VALIDACIÓN MÓDULO 004"
# ... y así sucesivamente ...
```

---

## 8. CONSECUENCIAS

**Si ODIN implementa los 4 módulos:**
→ ZEUS valida módulo por módulo → ACTAs de validación → Merge a main → PROYECTO-005 COMPLETO

**Si ODIN no implementa o introduce errores:**
→ ZEUS rechaza → ACTAs de corrección → ODIN re-corrige

**Sin validación de todos los módulos, no hay release de PROYECTO-005.**

---

## 9. FORMATO DE DECLARACIÓN DE FIN POR MÓDULO

Cuando ODIN termine un módulo, debe escribir EXACTAMENTE:

```
MÓDULO [XXX] — LISTO PARA VALIDACIÓN

Fecha/hora fin: [YYYY-MM-DD HH:MM] [Zona horaria]
Tasks completados: [X/Y]
Commits:
- [hash] — [mensaje]

Tests ejecutados:
- Unitarios: [X] tests, [X%] cobertura
- Integración: [X] tests
- E2E: [X] tests

Notas: [cualquier nota relevante]
```

---

## 10. FIRMA

| Rol | Nombre | Firma | Fecha |
|-----|--------|-------|-------|
| CEO | Jelkin Zair Carrillo Franco | ✅ Aprobado | 2026-06-14 |
| PMO | ZEUS | ✅ Generado | 2026-06-14 |
| Dev | ODIN | [Pendiente] | — |

---

> **"Cuatro módulos, una misión: proteger a los menores con tecnología de clase mundial."**
> **Jelkin Zair Carrillo Franco — CEO**

---

**Instrucción generada:** 2026-06-14 11:53 CST (Shanghai) / 10:53 (Bogotá)  
**Próxima acción:** ODIN lee instrucción → inicia Módulo 003 → push por módulo → ZEUS valida  
**Estado:** APROBADA — Esperando ejecución por ODIN
