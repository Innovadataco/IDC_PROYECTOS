# KPI Y MÉTRICAS — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. FRAMEWORK DE MÉTRICAS

Las métricas se organizan en 4 dimensiones:

| Dimensión | Descripción | Frecuencia |
|-----------|-------------|------------|
| **Producto** | Uso, engagement, funcionalidad | Diaria / Semanal |
| **Técnica** | Performance, seguridad, calidad de código | Diaria / Semanal |
| **Negocio** | Ingresos, costos, sostenibilidad | Mensual / Trimestral |
| **Impacto Social** | Protección de menores, empoderamiento ciudadano | Mensual / Trimestral |

---

## 2. MÉTRICAS DE PRODUCTO

### 2.1 Adopción y Uso

| Métrica | Definición | Meta (M1) | Meta (M3) | Meta (M6) | Meta (M12) | Instrumento |
|---------|-----------|-----------|-----------|-----------|------------|-------------|
| **Consultas al Semáforo** | Número de consultas GET /api/validate/{identifier} | — | 100/día | 500/día | 1,000/día | PostgreSQL + API logs |
| **Reportes Anónimos** | Número de reportes POST /api/v1/reportes | 10/semana | 50/semana | 100/semana | 200/semana | PostgreSQL |
| **Usuarios Únicos** | Distinct IPs (hashed) que consultan o reportan | 50/semana | 200/semana | 500/semana | 1,000/semana | Redis (IP hash) |
| **Tasa de Conversión** | Reportes / Consultas (%) | 5% | 10% | 15% | 20% | PostgreSQL |
| **Retención D1** | % de usuarios que vuelven al día siguiente | — | 20% | 30% | 40% | Redis (IP hash) |
| **Retención D7** | % de usuarios que vuelven a los 7 días | — | 10% | 20% | 30% | Redis (IP hash) |
| **Suscriptores Premium** | Usuarios B2C con plan de pago ($2.99/mes) | 0 | 10 | 50 | 200 | Stripe |
| **Colegios B2B2C** | Instituciones educativas suscritas | 0 | 1 (piloto) | 3 | 10 | Contratos |
| **NPS (Net Promoter Score)** | "¿Recomendarías este servicio a otro padre?" (0-10) | — | 30 | 40 | 50 | Encuesta en PWA |

### 2.2 Engagement

| Métrica | Definición | Meta (M3) | Meta (M6) | Meta (M12) | Instrumento |
|---------|-----------|-----------|-----------|------------|-------------|
| **Tiempo en PWA** | Tiempo promedio en la PWA (segundos) | 60s | 90s | 120s | Frontend analytics (sin tracking) |
| **Consultas por sesión** | Promedio de consultas por visita | 2 | 3 | 4 | PostgreSQL |
| **Evidencia adjunta** | % de reportes con evidencia multimedia | 30% | 40% | 50% | PostgreSQL |
| **Compartir resultado** | % de consultas compartidas (URL) | 5% | 10% | 15% | PostgreSQL (share_url) |
| **Alerta premium** | % de usuarios premium con alertas activas | — | 50% | 60% | PostgreSQL |

---

## 3. MÉTRICAS TÉCNICAS

### 3.1 Performance

| Métrica | Definición | Meta (MVP) | Meta (Escalado) | Instrumento |
|---------|-----------|-----------|-----------------|-------------|
| **Tiempo de consulta (P95)** | 95th percentile de GET /api/validate | <500ms | <200ms | Prometheus / Nginx logs |
| **Tiempo de reporte (P95)** | 95th percentile de POST /api/v1/reportes | <2s | <1s | Prometheus / Nginx logs |
| **Tiempo de inferencia IA (P95)** | 95th percentile de POST /api/analyze | <500ms | <200ms | Prometheus / Python logs |
| **Tiempo de desencriptación (P95)** | 95th percentile de POST /api/admin/reports/{id}/decrypt | <2s | <1s | Prometheus / Nginx logs |
| **Uptime** | % de tiempo que el sistema está operativo | 99.5% | 99.9% | Uptime Kuma / Pingdom |
| **Error rate** | % de requests con error 5xx | <1% | <0.1% | Nginx logs / Sentry |
| **Cache hit rate** | % de consultas servidas desde cache | <50% | >70% | Redis INFO |
| **Database query time (P95)** | 95th percentile de queries PostgreSQL | <100ms | <50ms | PostgreSQL pg_stat_statements |

### 3.2 Seguridad

| Métrica | Definición | Meta | Frecuencia | Instrumento |
|---------|-----------|------|------------|-------------|
| **Vulnerabilidades críticas** | Número de vulnerabilidades críticas (OWASP ZAP) | 0 | Mensual | OWASP ZAP |
| **Vulnerabilidades altas** | Número de vulnerabilidades altas | 0 | Mensual | OWASP ZAP |
| **Intentos de brute force** | Intentos de login fallidos / hora | <5 | Diaria | Nginx logs / AuditLog |
| **Rate limit triggers** | Requests bloqueados por rate limiting / día | <100 | Diaria | Redis / Nginx logs |
| **Desencriptaciones** | Número de desencriptaciones por admin / día | <10 | Diaria | AuditLog |
| **Alertas de seguridad** | Alertas de Dependabot (CVE) abiertas | 0 | Semanal | GitHub Dependabot |
| **Backup success rate** | % de backups diarios exitosos | 100% | Diaria | Cron logs / S3 |
| **TLS score** | SSL Labs score (A+ = óptimo) | A+ | Mensual | SSL Labs |

### 3.3 Calidad de Código

| Métrica | Definición | Meta | Frecuencia | Instrumento |
|---------|-----------|------|------------|-------------|
| **Cobertura de tests** | % de líneas cubiertas por tests | ≥80% | Semanal | pytest --cov |
| **Tests E2E pass rate** | % de tests E2E (Playwright) que pasan | 100% | Semanal | Playwright CI |
| **Code smells** | Número de code smells (lint) | 0 | Semanal | ruff / eslint |
| **Debt ratio** | Ratio de deuda técnica (SonarQube) | <5% | Mensual | SonarQube (futuro) |
| **Tiempo de build CI** | Tiempo de build en GitHub Actions | <10 min | Semanal | GitHub Actions |
| **Deploy frequency** | Número de deploys a producción / semana | ≥1 | Semanal | GitHub Actions |
| **Lead time for changes** | Tiempo desde commit hasta producción | <1 día | Semanal | GitHub Actions |
| **Mean time to recovery** | Tiempo desde fallo hasta recuperación | <1 hora | Mensual | Incident logs |

### 3.4 IA / ML

| Métrica | Definición | Meta | Frecuencia | Instrumento |
|---------|-----------|------|------------|-------------|
| **AUC-ROC** | Área bajo la curva ROC (test holdout) | ≥0.80 | Trimestral | scikit-learn |
| **Precision (severe)** | % de reportes clasificados severe que realmente son severe | ≥70% | Trimestral | scikit-learn |
| **Recall (severe)** | % de reportes severe correctamente detectados | ≥85% | Trimestral | scikit-learn |
| **F1-score (severe)** | Media armónica de precision y recall | ≥0.75 | Trimestral | scikit-learn |
| **Fairness disparity** | Disparidad de AUC-ROC entre subgrupos | <10% | Trimestral | Fairness audit script |
| **False negative rate (severe)** | % de reportes severe clasificados como low | 0% | Trimestral | Red-teaming script |
| **Model drift** | Cambio en AUC-ROC entre entrenamientos | <5% | Trimestral | scikit-learn |
| **Inference time (P95)** | 95th percentile de tiempo de inferencia | <500ms | Semanal | Prometheus |
| **Dataset size** | Número de ejemplos en dataset de entrenamiento | 1,500 → 5,000 | Trimestral | Dataset logs |

---

## 4. MÉTRICAS DE NEGOCIO

### 4.1 Ingresos

| Métrica | Definición | Meta (M3) | Meta (M6) | Meta (M12) | Instrumento |
|---------|-----------|-----------|-----------|------------|-------------|
| **MRR (Monthly Recurring Revenue)** | Ingresos recurrentes mensuales (B2C + B2B2C) | $0 | $500 | $2,000 | Stripe + contratos |
| **ARR (Annual Recurring Revenue)** | Ingresos recurrentes anuales | $0 | $6,000 | $24,000 | Stripe + contratos |
| **B2C MRR** | Suscriptores Premium × $2.99 | $0 | $150 | $600 | Stripe |
| **B2B2C MRR** | Colegios × precio promedio / 12 | $0 | $350 | $1,400 | Contratos |
| **B2G ingresos** | Contratos con autoridades | $0 | $0 | $5,000 | Contratos |
| **Churn rate B2C** | % de suscriptores que cancelan / mes | — | <10% | <5% | Stripe |
| **Churn rate B2B2C** | % de colegios que no renuevan / año | — | 0% | <10% | Contratos |
| **LTV (Lifetime Value)** | Valor promedio de un cliente durante su vida | — | $50 | $100 | Stripe + análisis |
| **CAC (Customer Acquisition Cost)** | Costo promedio de adquirir un cliente | — | $20 | $15 | Marketing spend / clientes |
| **LTV/CAC ratio** | Ratio de LTV sobre CAC | — | >2 | >3 | Cálculo interno |
| **Payback period** | Meses para recuperar CAC | — | <6 | <3 | Cálculo interno |

### 4.2 Costos

| Métrica | Definición | Meta (MVP) | Meta (Escalado) | Instrumento |
|---------|-----------|-----------|-----------------|-------------|
| **Infraestructura mensual** | VPS, BD, cache, backup, dominio | $30 | $140 | DigitalOcean + AWS |
| **Costo por consulta** | Infra / consultas por mes | — | <$0.01 | Cálculo interno |
| **Costo por reporte** | Infra / reportes por mes | — | <$0.10 | Cálculo interno |
| **Costo de IA** | Tiempo de ODIN en IA / mes | 48h | 24h | Time tracking |
| **Burn rate mensual** | Costos totales / mes | $500 | $1,000 | Finanzas |
| **Runway** | Meses de operación con capital actual | 12 | 6 | Finanzas |

---

## 5. MÉTRICAS DE IMPACTO SOCIAL

### 5.1 Protección de Menores

| Métrica | Definición | Meta (M3) | Meta (M6) | Meta (M12) | Instrumento |
|---------|-----------|-----------|-----------|------------|-------------|
| **Reportes severe** | Número de reportes con score >= 0.85 | 5 | 20 | 50 | PostgreSQL |
| **Reportes critical** | Número de reportes con score >= 0.70 | 10 | 50 | 100 | PostgreSQL |
| **Alertas enviadas a autoridades** | Número de alertas entregadas a ICBF/Fiscalía/Policía | 0 | 10 | 50 | Alerts table |
| **Redes organizadas detectadas** | Número de identificadores con is_network = true | 0 | 2 | 10 | Profiles table |
| **Menores potencialmente protegidos** | Estimación: reportes severe × 1 menor afectado | 5 | 20 | 50 | Cálculo interno |
| **Ciudades con reportes** | Número de ciudades únicas con reportes | 5 | 10 | 20 | PostgreSQL |
| **Países con reportes** | Número de países únicos con reportes | 1 | 2 | 5 | PostgreSQL |

### 5.2 Empoderamiento Ciudadano

| Métrica | Definición | Meta (M3) | Meta (M6) | Meta (M12) | Instrumento |
|---------|-----------|-----------|-----------|------------|-------------|
| **Consultas que evitaron contacto** | Estimación: consultas con semáforo rojo/negro que llevaron a bloqueo | 50 | 200 | 500 | Encuesta en PWA |
| **Reportes que confirmaron riesgo** | % de consultas que resultaron en reporte | 5% | 10% | 15% | PostgreSQL |
| **Satisfacción de consulta** | "¿La información te ayudó a tomar una decisión?" (Sí/No) | 80% | 85% | 90% | Encuesta en PWA |
| **Confianza en la plataforma** | "¿Confías en el Semáforo de Confianza?" (1-5) | 3.5 | 4.0 | 4.5 | Encuesta en PWA |

---

## 6. DASHBOARD DE MÉTRICAS

### 6.1 Dashboard Técnico (Panel Admin)

```
┌─────────────────────────────────────────────────────────────┐
│  SEMÁFORO DE CONFIANZA — Dashboard Técnico                  │
│  Última actualización: 2026-06-13 10:00:00 UTC              │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  📊 TRÁFICO (Últimas 24h)                                   │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐           │
│  │ Consultas   │ │ Reportes    │ │ Usuarios    │           │
│  │ 1,234       │ │ 56          │ │ 892         │           │
│  │ ↑ 12%       │ │ ↑ 8%        │ │ ↑ 15%       │           │
│  └─────────────┘ └─────────────┘ └─────────────┘           │
│                                                             │
│  🟢🟡🔴⚫ SEMÁFORO (Total acumulado)                        │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────┐│
│  │ Verde       │ │ Amarillo    │ │ Rojo        │ │ Negro   ││
│  │ 45          │ │ 23          │ │ 15          │ │ 4       ││
│  │ 50%         │ │ 25%         │ │ 17%         │ │ 4%      ││
│  └─────────────┘ └─────────────┘ └─────────────┘ └─────────┘│
│                                                             │
│  ⚠️ ALERTAS (Pendientes)                                    │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐           │
│  │ Severe      │ │ Critical    │ │ Networks    │           │
│  │ 3           │ │ 8           │ │ 2           │           │
│  │ Sin enviar  │ │ Sin enviar  │ │ Detectadas  │           │
│  └─────────────┘ └─────────────┘ └─────────────┘           │
│                                                             │
│  📈 PERFORMANCE (P95, última hora)                         │
│  Consulta: 234ms | Reporte: 1.2s | IA: 456ms | Decrypt: 890ms│
│                                                             │
│  🔒 SEGURIDAD (Últimas 24h)                                 │
│  Brute force attempts: 2 | Rate limit triggers: 12 | Vulns: 0│
│                                                             │
│  💰 NEGOCIO (Este mes)                                      │
│  MRR: $2,150 | B2C: $650 | B2B2C: $1,500 | B2G: $0        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 6.2 Dashboard Social (Pública, en PWA)

```
┌─────────────────────────────────────────────────────────────┐
│  IMPACTO DE LA COMUNIDAD                                     │
│                                                             │
│  🛡️ 1,234 consultas realizadas                              │
│  📝 56 reportes anónimos recibidos                          │
│  🚨 15 alertas enviadas a autoridades                       │
│  🌐 10 ciudades, 2 países participando                    │
│  🔴 2 redes organizadas detectadas y reportadas            │
│                                                             │
│  "Gracias a tu reporte, 3 menores están más seguros."     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## 7. REPORTES Y REVISIÓN

| Reporte | Frecuencia | Audiencia | Contenido | Responsable |
|---------|------------|-----------|-----------|-------------|
| **Daily Standup** | Diaria | ODIN, ZEUS | Progreso, bloqueos, plan | ODIN + ZEUS |
| **Weekly Metrics** | Semanal | Todos | KPIs de producto, técnica, negocio | ZEUS |
| **Monthly Review** | Mensual | Todos | Revisión de hitos, métricas, decisiones | ZEUS |
| **Quarterly OKR** | Trimestral | Jelkin, ZEUS, Diana | Objetivos, key results, dirección | ZEUS |
| **Security Report** | Mensual | ODIN, ZEUS | Vulnerabilidades, incidentes, mitigaciones | ODIN |
| **IA Evaluation** | Trimestral | ODIN, ZEUS | AUC-ROC, fairness, drift, model card | ODIN |
| **Financial Report** | Mensual | Jelkin, ZEUS | MRR, ARR, costos, runway, burn rate | ZEUS |
| **Social Impact Report** | Trimestral | Todos | Reportes, alertas, menores protegidos, ciudades | ZEUS |

---

## 8. OKRs (Objectives and Key Results)

### Q3 2026 (Julio - Septiembre)

**O1: Completar MVP Técnico (Módulos 002-004)**
- KR1: Módulo 002 (Consulta Semáforo) en producción con >100 consultas/día
- KR2: Módulo 003 (IA Triage) con AUC-ROC >= 0.80 y fairness audit aprobado
- KR3: Módulo 004 (Clustering) detectando >=1 red organizada real
- KR4: Cobertura de tests >= 80% en todos los módulos

**O2: Generar Tracción Inicial (B2C)**
- KR1: 1,000 consultas al Semáforo en el primer mes de lanzamiento
- KR2: 50 reportes anónimos en el primer mes
- KR3: 10 suscriptores Premium B2C
- KR4: NPS >= 30

### Q4 2026 (Octubre - Diciembre)

**O1: Completar Producto Funcional (Módulos 005-006)**
- KR1: Módulo 005 (Panel Admin) con auth, dashboard, desencriptación, audit trail
- KR2: Módulo 006 (Pasarela Institucional) con alertas automáticas y digest
- KR3: 0 vulnerabilidades críticas en auditoría OWASP ZAP + pentest
- KR4: Deploy en producción con 99.5% uptime

**O2: Sostenibilidad Económica**
- KR1: 50 suscriptores Premium B2C ($150 MRR)
- KR2: 3 colegios B2B2C ($1,400 MRR)
- KR3: MRR total >= $2,000
- KR4: Burn rate < MRR (punto de equilibrio operativo)

**O3: Impacto Social Medible**
- KR1: 500 reportes reales procesados
- KR2: 50 alertas enviadas a autoridades
- KR3: 5 redes organizadas detectadas
- KR4: 10 ciudades con reportes activos

### Q1 2027 (Enero - Marzo)

**O1: Escalar Operación**
- KR1: 200 suscriptores Premium B2C ($600 MRR)
- KR2: 10 colegios B2B2C ($2,500 MRR)
- KR3: 1 contrato B2G firmado ($5,000 ARR)
- KR4: ARR total >= $24,000

**O2: Expandir Geográficamente**
- KR1: 5 países con reportes activos
- KR2: 20 ciudades con reportes activos
- KR3: 1 implementación en país de LATAM (piloto)
- KR4: 2,000 consultas/día promedio

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — KPI y métricas del Semáforo de Confianza*
> *4 dimensiones, 50+ métricas, 3 OKRs trimestrales*
