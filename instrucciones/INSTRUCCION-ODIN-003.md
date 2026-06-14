# INSTRUCCION-ODIN-003.md
**Proyecto:** PROYECTO-005: Semáforo de Confianza (Protección Infantil)  
**Módulo:** 003 — IA Triage y Clasificación  
**Actividad:** ACT-003 — IA Triage  
**Auditoría base:** ACTA-VALIDACION-ODIN-002-CORRECCION.md  
**Asignado:** ODIN (CEO IA Dev)  
**Aprobador:** Jelkin Zair Carrillo Franco (CEO)  
**Fecha instrucción:** 2026-06-14 12:15 CST (Shanghai) / 11:15 (Bogotá)  
**Estado:** APROBADA ✅

---

## 1. CONTEXTO

**ACT-002: MERGEADO A MAIN ✅**

- 22 tasks implementados, 2 hallazgos corregidos
- Validado por ZEUS, aprobado por CEO
- ODIN declaró "LISTO PARA VALIDACIÓN"
- ZEUS validó ✅
- Jelkin aprobó ✅
- Merge a main completado

**Jelkin ordena:** Iniciar Módulo 003 (IA Triage). Orden secuencial: 003 → 004 → 005 → 006.

---

## 2. OBJETIVO

Implementar un sistema de Inteligencia Artificial para clasificación automática de reportes y detección de patrones de grooming.

**El modelo NO acusa.** Genera un score de "contacto inapropiado con menores reportado por la comunidad". La investigación judicial es responsabilidad exclusiva de las autoridades.

---

## 3. ALCANCE

**~40 tasks en 5 categorías:**

### Categoría 1: Dataset y Entrenamiento (5 tasks)
- TML-003.1: Dataset sintético 1,500 ejemplos (español colombiano/mexicano/argentino)
- TML-003.2: Estratificar por categoría (CAT-01 a CAT-06) y severidad
- TML-003.3: Etiquetar semi-automáticamente (keyword matching) + revisión manual
- TML-003.4: Split train/val/test (70/15/15)
- TML-003.5: Guardar dataset versionado (DVC o git LFS)

### Categoría 2: Preprocesamiento y Features (6 tasks)
- TML-003.6: Instalar spaCy + modelo es_core_news_md
- TML-003.7: Preprocesamiento (tokenización, lematización, stopwords)
- TML-003.8: TF-IDF vectorizer (n-grams 1-3)
- TML-003.9: Embeddings (distiluse-base-multilingual, opcional)
- TML-003.10: Features manuales (longitud, emojis, URLs, teléfonos)
- TML-003.11: Lexicon de grooming (lista de palabras/frases indicadoras)

### Categoría 3: Modelo y Evaluación (8 tasks)
- TML-003.12: Entrenar Logistic Regression (baseline)
- TML-003.13: Entrenar Random Forest (ensemble)
- TML-003.14: Implementar ensemble (voting o stacking)
- TML-003.15: Calibrar probabilidad con Platt scaling
- TML-003.16: Evaluar AUC-ROC en test (objetivo ≥ 0.80)
- TML-003.17: Fairness audit: disparidad < 10% entre subgrupos
- TML-003.18: Red-teaming: 0 falsos negativos de alto riesgo
- TML-003.19: Model card (objetivo, dataset, métricas, limitaciones)

### Categoría 4: Explicabilidad (4 tasks)
- TML-003.20: Integrar SHAP para explicación de tokens
- TML-003.21: Top 5 tokens que contribuyen al score
- TML-003.22: Detección de indicadores de grooming
- TML-003.23: Explicación solo para scores > 0.7 (performance)

### Categoría 5: Backend Integración (8 tasks)
- TB-003.1: Modelo `Analysis` (SQLAlchemy)
- TB-003.2: Endpoint POST /api/analyze/{report_id} (async)
- TB-003.3: Endpoint GET /api/analyze/{report_id}
- TB-003.4: Integrar análisis automático en POST /api/reportes (webhook interno)
- TB-003.5: Modelo versionado en código (model_version string)
- TB-003.6: No almacenar texto desencriptado en logs ni disco
- TB-003.7: Tests unitarios (pytest, cobertura ≥ 80%)
- TB-003.8: Tests de integración (TestClient)

### Categoría 6: Documentación (5 tasks)
- TD-003.1: ADR-003: Decisión de modelo NLP + dataset + fairness
- TD-003.2: Model card (docs/model-card.md)
- TD-003.3: Evaluation report (docs/evaluation.md)
- TD-003.4: Red-teaming report (docs/red-teaming.md)
- TD-003.5: Fairness report (docs/fairness.md)

---

## 4. REQUISITOS TÉCNICOS

### Modelo NLP
- Pipeline: spaCy (es_core_news_md) → TF-IDF → Ensemble (LR + RF)
- Embeddings opcionales: distiluse-base-multilingual
- AUC-ROC objetivo: ≥ 0.80
- Fairness: disparidad < 10% entre subgrupos
- Red-teaming: 0 falsos negativos de alto riesgo

### Score de Riesgo
| Score | Nivel | Acción | Color |
|-------|-------|--------|-------|
| 0.0-0.3 | Low | Almacenar, no alerta | — |
| 0.3-0.5 | Medium | Almacenar, resumen semanal | — |
| 0.5-0.7 | High | Almacenar, alerta diaria | 🟡 |
| 0.7-0.85 | Critical | Almacenar, alerta inmediata | 🔴 |
| 0.85-1.0 | Severe | Almacenar, alerta inmediata + pasarela | ⚫ |

### Categorías
- CAT-01: Contacto inapropiado (30%)
- CAT-02: Solicitud material (20%)
- CAT-03: Grooming (25%)
- CAT-04: Cita en persona (15%)
- CAT-05: Extorsión (10%)
- CAT-06: Desconocido (5%)

---

## 5. REGLAS DE EJECUCIÓN

### R-001: 1 commit por categoría o task
ODIN puede agrupar commits por categoría.
Formato: `feat(ia): Módulo 003 — [categoría] descripción`

Ejemplos:
```
feat(ia): Módulo 003 — dataset sintético 1,500 ejemplos
feat(ia): Módulo 003 — preprocesamiento spaCy + TF-IDF
feat(ia): Módulo 003 — modelo ensemble LR+RF, AUC-ROC 0.82
feat(ia): Módulo 003 — SHAP explicabilidad
feat(backend): Módulo 003 — endpoint /api/analyze/{report_id}
```

### R-002: Push por categoría completa
Cada vez que ODIN termine una categoría, hace push.
**No esperar a terminar el módulo completo para hacer push.**

### R-003: Declarar "LISTO PARA VALIDACIÓN" cuando termine el módulo
ODIN declara listo cuando todas las categorías están completas. ZEUS valida.

### R-004: No tocar IDC_PROYECTOS
ODIN solo trabaja en el repo `Desarrollos`. ZEUS maneja `IDC_PROYECTOS`.

### R-005: Timestamp obligatorio
ODIN registra fecha/hora de fin del módulo.

### R-006: Rama correcta
ODIN trabaja en `feature/v2-fullstack` (misma rama, o nueva si Jelkin lo ordena).

---

## 6. DEFINICIÓN DE TERMINADO (DoD)

- [ ] Dataset de 1,500 ejemplos generado
- [ ] Modelo entrenado con AUC-ROC ≥ 0.80
- [ ] Fairness audit: disparidad < 10%
- [ ] Red-teaming: 0 falsos negativos de alto riesgo
- [ ] Endpoint /api/analyze/{report_id} funcional (async)
- [ ] SHAP explicabilidad para scores > 0.7
- [ ] Tests unitarios ≥ 80% cobertura
- [ ] Tiempo inferencia < 500ms
- [ ] ADR-003 aprobado
- [ ] No almacenar texto desencriptado en logs ni disco

---

## 7. CONSECUENCIAS

**Si ODIN implementa el módulo:**
→ ZEUS valida → ACTA-VALIDACION-ODIN-003.md → Aprobación Jelkin → Merge a main → Módulo 004

**Si ODIN no implementa o introduce errores:**
→ ZEUS rechaza → ACTA-CORRECCION-ODIN-003.md → ODIN re-corrige

**Sin validación, no hay merge. Sin merge, no hay Módulo 004.**

---

## 8. FORMATO DE DECLARACIÓN DE FIN

Cuando ODIN termine, debe escribir EXACTAMENTE:

```
MÓDULO 003 — LISTO PARA VALIDACIÓN

Fecha/hora fin: [YYYY-MM-DD HH:MM] [Zona horaria]
Tasks completados: [X/Y]
Commits:
- [hash] — [mensaje]

Tests ejecutados:
- Unitarios: [X] tests, [X%] cobertura
- Integración: [X] tests
- E2E: [X] tests

Métricas del modelo:
- AUC-ROC: [X.XX]
- Fairness: [X%] disparidad
- Red-teaming: [X] falsos negativos
- Tiempo inferencia: [X]ms

Notas: [cualquier nota relevante]
```

---

## 9. FIRMA

| Rol | Nombre | Firma | Fecha |
|-----|--------|-------|-------|
| CEO | Jelkin Zair Carrillo Franco | ✅ Aprobado | 2026-06-14 |
| PMO | ZEUS | ✅ Generado | 2026-06-14 |
| Dev | ODIN | [Pendiente] | — |

---

> **"IA para proteger, no para acusar."**  
> **Jelkin Zair Carrillo Franco — CEO**

---

**Instrucción generada:** 2026-06-14 12:15 CST (Shanghai) / 11:15 (Bogotá)  
**Próxima acción:** ODIN lee instrucción → inicia Módulo 003 → push por categoría → ZEUS valida  
**Estado:** APROBADA — Esperando ejecución por ODIN
