# CRONOGRAMA — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. RESUMEN DE FASES Y HORAS

| Fase | Módulo | Fecha | Duración | Horas | Estado | Dependencias |
|------|--------|-------|----------|-------|--------|--------------|
| 1 | 001 Registro Anónimo | Junio 2026 | 4 semanas | 40h | ✅ Completado | — |
| 2 | 002 Consulta Semáforo | Julio 2026 | 4 semanas | 36h | ⬜ Nuevo | 001 |
| 3 | 003 IA Triage | Agosto 2026 | 4 semanas | 48h | ⬜ Nuevo | 001, 002 |
| 4 | 004 Clustering + Perfil | Septiembre 2026 | 4 semanas | 54h | ⬜ Nuevo | 001, 002, 003 |
| 5 | 005 Panel Admin | Octubre 2026 | 4 semanas | 50h | ⬜ Nuevo | 001-004 |
| 6 | 006 Pasarela Institucional | Noviembre 2026 | 4 semanas | 48h | ⬜ Nuevo | 001-005 |
| 7 | Producción + Piloto | Diciembre 2026 | 4 semanas | 78h | ⬜ Nuevo | 001-006 |
| **Total** | | **Junio-Diciembre 2026** | **28 semanas** | **354h** | | |

---

## 2. CRONOGRAMA DETALLADO (GANTT Simplificado)

```
                    Jun   Jul   Ago   Sep   Oct   Nov   Dic
Módulo 001 (40h)    ████
Módulo 002 (36h)          ████
Módulo 003 (48h)                ████
Módulo 004 (54h)                      ████
Módulo 005 (50h)                            ████
Módulo 006 (48h)                                  ████
Producción (78h)                                        ████
```

---

## 3. FASE 1: REGISTRO ANÓNIMO (COMPLETADO)

**Fechas:** 1-30 de junio 2026
**Duración:** 4 semanas
**Horas:** 40h (ODIN)
**Estado:** ✅ Completado

### Hitos

| Hito | Fecha | Descripción | Estado |
|------|-------|-------------|--------|
| 1.1 | Semana 1 | Scaffold frontend (React 19 + Vite + Tailwind) + PWA config | ✅ |
| 1.2 | Semana 2 | Formulario de reporte + upload evidencia multimedia | ✅ |
| 1.3 | Semana 3 | Backend API + encriptación AES-256-GCM + rate limiting | ✅ |
| 1.4 | Semana 4 | Tests + Docker + documentación SPEC/ADR | ✅ |

### Entregables
- [x] Formulario PWA funcional (mobile-first)
- [x] POST /api/v1/reportes endpoint
- [x] Encriptación AES-256-GCM por campo
- [x] Rate limiting 5/hr por IP
- [x] Evidence multimedia: strip EXIF, thumbnail, encriptación
- [x] Health check endpoint
- [x] Tests unitarios + integración (≥80% cobertura)
- [x] Docker + Docker Compose
- [x] SPEC-001, ADR-001, ADR-002

---

## 4. FASE 2: CONSULTA SEMÁFORO (NUEVO)

**Fechas:** 1-31 de julio 2026
**Duración:** 4 semanas
**Horas:** 36h (ODIN)
**Estado:** ⬜ Nuevo
**Dependencias:** Fase 1 completada

### Hitos

| Hito | Fecha | Descripción | Horas | Dependencia |
|------|-------|-------------|-------|-------------|
| 2.1 | Semana 1 | Diseñar UI de consulta + input universal | 4h | — |
| 2.2 | Semana 1 | Implementar normalización de identificadores | 4h | — |
| 2.3 | Semana 2 | Implementar endpoint GET /api/validate/{identifier} | 3h | TB-001.2 |
| 2.4 | Semana 2 | Implementar algoritmo de semáforo (4 colores) | 3h | — |
| 2.5 | Semana 2 | Diseñar cards de resultado (verde/amarillo/rojo/negro) | 4h | — |
| 2.6 | Semana 3 | Implementar página de resultado + botón "Reportar" | 4h | TF-001.3 |
| 2.7 | Semana 3 | Implementar rate limiting 10/hr para consulta | 2h | TB-001.6 |
| 2.8 | Semana 3 | PWA: página principal como consulta | 2h | TF-001.2 |
| 2.9 | Semana 4 | Tests unitarios + integración | 6h | — |
| 2.10 | Semana 4 | Landing page + SEO básico | 4h | — |
| 2.11 | Semana 4 | Registro de Stripe para pagos (MVP: gratuito) | 4h | — |

### Entregables
- [ ] Página principal como buscador de confianza
- [ ] Normalización de identificadores (E.164, email, @, URL)
- [ ] Algoritmo de semáforo (verde/amarillo/rojo/negro)
- [ ] Endpoint GET /api/validate/{identifier} funcional
- [ ] PWA funcional con consulta como landing
- [ ] Tests ≥80% cobertura
- [ ] SPEC-002, PLAN-002, TASKS-002

---

## 5. FASE 3: IA TRIAGE (NUEVO)

**Fechas:** 1-31 de agosto 2026
**Duración:** 4 semanas
**Horas:** 48h (ODIN)
**Estado:** ⬜ Nuevo
**Dependencias:** Fase 1 y 2 completadas

### Hitos

| Hito | Fecha | Descripción | Horas | Dependencia |
|------|-------|-------------|-------|-------------|
| 3.1 | Semana 1 | Generar dataset sintético 1,500 ejemplos (español) | 8h | — |
| 3.2 | Semana 1 | Implementar preprocesamiento NLP (spaCy) | 4h | — |
| 3.3 | Semana 2 | Implementar feature extraction (TF-IDF + embeddings) | 6h | — |
| 3.4 | Semana 2 | Implementar lexicon de grooming | 4h | — |
| 3.5 | Semana 2 | Entrenar clasificador (LR + RF ensemble) | 6h | 3.1-3.4 |
| 3.6 | Semana 3 | Calibrar probabilidad (Platt scaling) | 2h | 3.5 |
| 3.7 | Semana 3 | Implementar fairness audit | 4h | 3.5 |
| 3.8 | Semana 3 | Implementar red-teaming | 4h | 3.5 |
| 3.9 | Semana 3 | Implementar explicabilidad SHAP | 4h | 3.5 |
| 3.10 | Semana 4 | Endpoint POST /api/analyze/{report_id} (async) | 3h | TB-001.2 |
| 3.11 | Semana 4 | Integrar análisis automático al recibir reporte | 2h | 3.10 |
| 3.12 | Semana 4 | Model card + evaluation report | 3h | 3.5-3.9 |
| 3.13 | Semana 4 | Tests unitarios + integración | 6h | — |

### Entregables
- [ ] Dataset sintético 1,500 ejemplos etiquetados
- [ ] Modelo NLP ensemble (LR + RF) con AUC-ROC ≥0.80
- [ ] Fairness audit: disparidad <10% entre subgrupos
- [ ] Red-teaming: 0 falsos negativos de alto riesgo
- [ ] SHAP explicabilidad integrada
- [ ] Endpoint async /api/analyze/{report_id}
- [ ] Model card + evaluation report
- [ ] Tests ≥80% cobertura
- [ ] SPEC-003, PLAN-003, TASKS-003, ADR-003

---

## 6. FASE 4: CLUSTERING + PERFIL (NUEVO)

**Fechas:** 1-30 de septiembre 2026
**Duración:** 4 semanas
**Horas:** 54h (ODIN)
**Estado:** ⬜ Nuevo
**Dependencias:** Fase 1, 2, 3 completadas

### Hitos

| Hito | Fecha | Descripción | Horas | Dependencia |
|------|-------|-------------|-------|-------------|
| 4.1 | Semana 1 | Implementar geocodificación (MaxMind GeoLite2) | 6h | — |
| 4.2 | Semana 1 | Implementar modelo Profile (SQLAlchemy) | 3h | TB-001.2 |
| 4.3 | Semana 1 | Implementar modelo ProfileUpdate (audit) | 3h | 4.2 |
| 4.4 | Semana 2 | Implementar algoritmo de clustering | 4h | — |
| 4.5 | Semana 2 | Implementar endpoint GET /api/profile/{hash} | 4h | 4.2 |
| 4.6 | Semana 2 | Implementar endpoint GET /api/networks | 3h | 4.5 |
| 4.7 | Semana 3 | Implementar recálculo automático de perfil | 4h | 4.2, TB-003.4 |
| 4.8 | Semana 3 | Implementar índice en identifier_hash | 2h | — |
| 4.9 | Semana 3 | Implementar cache Redis de perfiles | 3h | — |
| 4.10 | Semana 3 | Implementar cálculo de timeline | 4h | — |
| 4.11 | Semana 4 | Implementar detección de red organizada | 4h | 4.4 |
| 4.12 | Semana 4 | Tests unitarios + integración | 8h | — |
| 4.13 | Semana 4 | Panel admin: visualización de perfiles y redes | 6h | 4.5 |
| 4.14 | Semana 4 | ADR + documentación | 2h | — |

### Entregables
- [ ] Geocodificación con MaxMind GeoLite2 local
- [ ] Modelo Profile + ProfileUpdate
- [ ] Clustering geográfico (≥3 ciudades/países)
- [ ] Perfil de identificador (timeline, scores, ciudades, evidencia)
- [ ] Detección de red organizada (2+ criterios)
- [ ] Cache Redis para perfiles
- [ ] Tests ≥80% cobertura
- [ ] SPEC-004, PLAN-004, TASKS-004, ADR-004

---

## 7. FASE 5: PANEL ADMIN (NUEVO)

**Fechas:** 1-31 de octubre 2026
**Duración:** 4 semanas
**Horas:** 50h (ODIN)
**Estado:** ⬜ Nuevo
**Dependencias:** Fase 1-4 completadas

### Hitos

| Hito | Fecha | Descripción | Horas | Dependencia |
|------|-------|-------------|-------|-------------|
| 5.1 | Semana 1 | Auth JWT (login, refresh, logout) | 6h | — |
| 5.2 | Semana 1 | 2FA TOTP (opcional) | 4h | 5.1 |
| 5.3 | Semana 1 | Modelo de roles (5 roles) | 4h | 5.1 |
| 5.4 | Semana 2 | Dashboard de métricas (endpoint + UI) | 6h | 5.1 |
| 5.5 | Semana 2 | Lista de reportes con filtros y paginación | 6h | 5.1, TB-001.2 |
| 5.6 | Semana 2 | Detalle de reporte + botón desencriptar | 4h | 5.5 |
| 5.7 | Semana 3 | Desencriptación bajo demanda (razón + límite) | 6h | 5.6, TB-001.4 |
| 5.8 | Semana 3 | Audit trail (AuditLog) | 4h | 5.7 |
| 5.9 | Semana 3 | Cambio de estado de reporte | 3h | 5.5 |
| 5.10 | Semana 3 | Export JSON (schema fijo) | 4h | 5.5 |
| 5.11 | Semana 4 | Export PDF (branding, reportlab) | 4h | 5.10 |
| 5.12 | Semana 4 | Panel admin: perfiles y redes | 6h | 4.13 |
| 5.13 | Semana 4 | Tests E2E con Playwright | 8h | — |
| 5.14 | Semana 4 | Tests unitarios + integración | 4h | — |
| 5.15 | Semana 4 | ADR + documentación | 2h | — |

### Entregables
- [ ] Auth JWT + 2FA TOTP funcional
- [ ] Dashboard de métricas en tiempo real
- [ ] Lista de reportes con filtros y paginación
- [ ] Desencriptación bajo demanda con audit trail
- [ ] Cambio de estado (4 estados)
- [ ] Export JSON + PDF
- [ ] Tests E2E (Playwright) + unitarios ≥80%
- [ ] SPEC-005, PLAN-005, TASKS-005, ADR (auth)

---

## 8. FASE 6: PASARELA INSTITUCIONAL (NUEVO)

**Fechas:** 1-30 de noviembre 2026
**Duración:** 4 semanas
**Horas:** 48h (ODIN)
**Estado:** ⬜ Nuevo
**Dependencias:** Fase 1-5 completadas

### Hitos

| Hito | Fecha | Descripción | Horas | Dependencia |
|------|-------|-------------|-------|-------------|
| 6.1 | Semana 1 | Modelo Institution + seed | 3h | — |
| 6.2 | Semana 1 | Modelo Alert + Digest | 6h | 6.1 |
| 6.3 | Semana 1 | Envío de alerta por email (SMTP) | 4h | 6.2 |
| 6.4 | Semana 2 | Formato JSON estructurado | 3h | — |
| 6.5 | Semana 2 | Formato PDF institucional | 4h | 6.4 |
| 6.6 | Semana 2 | Formato NCMEC (CyberTipline) | 4h | 6.4 |
| 6.7 | Semana 2 | Resumen de IA de 200 caracteres | 3h | 3.11 |
| 6.8 | Semana 3 | Alertas automáticas por severidad (cron) | 4h | 6.5, 6.6 |
| 6.9 | Semana 3 | Digest diario/semanal/mensual (cron) | 4h | 6.8 |
| 6.10 | Semana 3 | API gateway con API key | 4h | 5.1 |
| 6.11 | Semana 3 | Rate limiting 100 req/hr | 2h | 6.10 |
| 6.12 | Semana 4 | Confirmación de recepción | 3h | 6.10 |
| 6.13 | Semana 4 | Panel admin: config alertas + historial | 4h | 5.15 |
| 6.14 | Semana 4 | Tests de integración con mocks | 6h | — |
| 6.15 | Semana 4 | ADR + documentación | 2h | — |

### Entregables
- [ ] Seed de instituciones (ICBF, Fiscalía, Policía, NCMEC)
- [ ] Alertas automáticas por severidad (severe <15min, critical 4h, high 24h)
- [ ] Digest diario, semanal, mensual
- [ ] API gateway funcional (X-API-Key, rate limiting 100/hr)
- [ ] Formatos JSON, PDF, NCMEC
- [ ] Confirmación de recepción por institución
- [ ] Tests de integración con mocks
- [ ] SPEC-006, PLAN-006, TASKS-006, ADR-005

---

## 9. FASE 7: PRODUCCIÓN + PILOTO (NUEVO)

**Fechas:** 1-31 de diciembre 2026
**Duración:** 4 semanas
**Horas:** 78h (mix ODIN + operativo)
**Estado:** ⬜ Nuevo
**Dependencias:** Fase 1-6 completadas

### Hitos

| Hito | Fecha | Descripción | Horas | Dependencia |
|------|-------|-------------|-------|-------------|
| 7.1 | Semana 1 | Deploy en VPS/cloud (DigitalOcean) | 8h | — |
| 7.2 | Semana 1 | TLS 1.3 + dominio propio | 4h | 7.1 |
| 7.3 | Semana 1 | Monitoreo y alerting (uptime, logs) | 6h | 7.1 |
| 7.4 | Semana 2 | Auditoría de seguridad interna (OWASP ZAP) | 8h | — |
| 7.5 | Semana 2 | Auditoría de seguridad externa (pentest) | 16h | 7.4 |
| 7.6 | Semana 3 | Capacitación a autoridades (demo + manual) | 8h | 6.15 |
| 7.7 | Semana 3 | Piloto con 1 colegio B2B2C | 20h | — |
| 7.8 | Semana 3 | Marketing de lanzamiento (Zaira) | 8h | — |
| 7.9 | Semana 4 | Iteración post-piloto (UX, ajustes) | 16h | 7.7 |
| 7.10 | Semana 4 | Negociación de contratos B2G | 10h | — |
| 7.11 | Semana 4 | Documentación final + runbook | 8h | — |

### Entregables
- [ ] Deploy en VPS funcional (DigitalOcean)
- [ ] TLS 1.3 activo, dominio propio
- [ ] Monitoreo 24/7 operativo
- [ ] Auditoría OWASP ZAP: 0 vulnerabilidades críticas
- [ ] Pentest externo: 0 vulnerabilidades críticas
- [ ] Piloto con 1 colegio B2B2C completado
- [ ] 500+ reportes reales procesados
- [ ] 1 contrato o carta de intención firmada
- [ ] Manual de operación + runbook
- [ ] Marketing de lanzamiento (redes, PR, evento)

---

## 10. DEPENDENCIAS CRÍTICAS

```
001 (Registro) ──► 002 (Consulta) ──► 003 (IA) ──► 004 (Clustering)
                                            │              │
                                            │              ▼
                                            │         005 (Panel Admin)
                                            │              │
                                            │              ▼
                                            │         006 (Pasarela)
                                            │              │
                                            └──────────────┘
                                                   │
                                                   ▼
                                              007 (Producción)
```

**Dependencias críticas (bloqueantes):**
- 002 depende de 001 (necesita modelo Report)
- 003 depende de 001 (necesita datos de reportes para entrenar)
- 004 depende de 003 (necesita scores para perfil)
- 005 depende de 004 (necesita perfiles para panel admin)
- 006 depende de 005 (necesita panel admin para configuración de alertas)
- 007 depende de 001-006 (necesita todos los módulos funcionales)

**Dependencias no críticas (paralelizables):**
- Marketing de Zaira puede empezar en Fase 2 (landing page + consulta)
- Contacto con ICBF/Fiscalía puede empezar en Fase 5 (panel admin funcional para demo)
- Piloto con colegio puede empezar en Fase 5 (consulta + reporte funcional)

---

## 11. RIESGOS AL CRONOGRAMA

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|-------------|---------|------------|
| Retraso en Fase 3 (IA) por dataset insuficiente | Media | Alto | Dataset sintético + data augmentation. Si no funciona, usar keyword matching como fallback para Fase 4. |
| Retraso en Fase 5 (Panel Admin) por complejidad de auth | Baja | Medio | Usar biblioteca auth estándar (FastAPI-Users o similar). No implementar auth desde cero. |
| Retraso en Fase 6 (Pasarela) por falta de API de instituciones | Alta | Medio | Email estructurado como fallback. No depender de API institucional para completar fase. |
| Retraso en Fase 7 (Producción) por auditoría externa | Media | Medio | Auditoría interna primero (OWASP ZAP). Auditoría externa puede retrasarse a enero 2027. |
| Retraso por dependencia de ODIN como único dev | Media | Alto | Documentación SDD completa. Juan como backup técnico. Dividir tareas en micro-tareas. |

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Cronograma detallado del Semáforo de Confianza*
