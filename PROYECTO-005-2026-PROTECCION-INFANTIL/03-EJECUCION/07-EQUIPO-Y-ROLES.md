# EQUIPO Y ROLES — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. ESTRUCTURA DE EQUIPO

```
┌─────────────────────────────────────────────────────────────┐
│                    JELKIN ZAIR CARRILLO FRANCO             │
│                      CEO Estratégico                       │
│              Aprobador, visión, decisión final           │
└────────────────────────┬────────────────────────────────────┘
                         │
         ┌───────────────┼───────────────┐
         │               │               │
         ▼               ▼               ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│   ZEUS       │ │   DIANA      │ │   ZAIRA      │
│  PMO / AI    │ │   Legal      │ │  Marketing   │
│  Gestión +   │ │  Compliance  │ │  Posicionam. │
│  Estrategia  │ │  Asesoría    │ │  Growth      │
└──────┬───────┘ └──────────────┘ └──────────────┘
       │
       ▼
┌──────────────┐
│    ODIN      │
│  Desarrollo  │
│  Full-Stack  │
│  (100% FTE)  │
└──────────────┘
       │
       ▼
┌──────────────┐
│    JUAN      │
│  Soporte /   │
│  Backup      │
│  Técnico     │
│  (10% FTE)   │
└──────────────┘
```

---

## 2. ROLES Y RESPONSABILIDADES

### Jelkin Zair Carrillo Franco — CEO Estratégico

| Aspecto | Responsabilidad |
|---------|---------------|
| **Aprobación** | Aprobación final de todos los documentos PM2, specs, ADRs, y decisiones de negocio |
| **Visión** | Define visión del producto, pivote, y dirección estratégica |
| **Negociación** | Contacto con autoridades (ICBF, Fiscalía), colegios piloto, contratos B2G |
| **Recursos** | Asignación de presupuesto, infraestructura, contratación |
| **Decisión** | Decisiones de negocio: modelo de negocio, proveedor, responsabilidad legal |
| **Tiempo** | 20% del tiempo (4h/semana) |
| **Contacto** | jelkin@innovadataco.com |

### ZEUS — PMO / Gestión de Proyecto / Inteligencia Estratégica

| Aspecto | Responsabilidad |
|---------|---------------|
| **PM2** | Crear, actualizar, y mantener todos los documentos PM2 |
| **Estrategia** | Análisis de negocio, modelo de negocio, competencia, oportunidades |
| **Gestión** | Seguimiento de hitos, cronograma, riesgos, KPIs |
| **Documentación** | SDD, specs, ADRs, evaluation reports, model cards |
| **Comunicación** | Informes semanales, actas de reuniones, decisiones |
| **Tiempo** | 20% del tiempo (8h/semana) |
| **Herramientas** | Markdown, GitHub, Notion (opcional) |

### Diana — Legal / Compliance / Asesoría Estratégica

| Aspecto | Responsabilidad |
|---------|---------------|
| **Legal** | Revisión de contratos con instituciones, cláusulas de limitación de responsabilidad |
| **Compliance** | Validación de cumplimiento con Ley 1098 de 2006 (Código de Infancia), Ley 1581 de 2012 (Protección de Datos), Ley 1273 de 2009 (Delitos Informáticos) |
| **Privacidad** | Validación de anonimato, encriptación, geocodificación, consentimiento |
| **Seguro** | Evaluación de seguro de responsabilidad civil si Innovadataco opera como operador |
| **Asesoría** | Aprobación de ADRs de seguridad, privacidad, y pasarela |
| **Tiempo** | 10% del tiempo (4h/semana) |
| **Contacto** | diana@innovadataco.com |

### Zaira — Marketing / Posicionamiento / Growth

| Aspecto | Responsabilidad |
|---------|---------------|
| **Branding** | Diseño de marca, logo, colores, tono de voz del producto |
| **Landing** | Diseño de landing page, copy, SEO básico |
| **Redes** | Estrategia de contenido en redes sociales (Instagram, TikTok, Facebook) |
| **Colegios** | Contacto con colegios para piloto B2B2C, demo, presentación |
| **PR** | Relaciones públicas, contacto con medios, charlas en eventos de tecnología cívica |
| **Growth** | Estrategia de adquisición de usuarios (B2C), retención (Premium) |
| **Tiempo** | 10% del tiempo (4h/semana) |
| **Herramientas** | Canva, Figma, Instagram, TikTok, Mailchimp |

### ODIN — Desarrollo Full-Stack / Ingeniería

| Aspecto | Responsabilidad |
|---------|---------------|
| **Frontend** | React 19 + Vite + Tailwind CSS + PWA (Workbox) |
| **Backend** | FastAPI + SQLAlchemy + PostgreSQL + Redis |
| **IA/ML** | Dataset, entrenamiento, fairness audit, red-teaming, SHAP |
| **Seguridad** | Encriptación AES-256-GCM, auth JWT + 2FA, rate limiting, OWASP headers |
| **Infra** | Docker + Docker Compose, Nginx, TLS 1.3, GitHub Actions CI/CD |
| **Tests** | pytest + Playwright, cobertura ≥80% |
| **Documentación** | SDD (specs, plans, tasks), ADRs, API reference, estructura de datos |
| **Tiempo** | 100% del tiempo (40h/semana) |
| **Herramientas** | Kimi Code CLI, VS Code, GitHub, Docker, DigitalOcean |

### Juan — Soporte Técnico / Backup Técnico

| Aspecto | Responsabilidad |
|---------|---------------|
| **Backup** | Capacitación en código, documentación, stack técnico para poder asumir si ODIN no está disponible |
| **Soporte** | Soporte técnico de nivel 1: troubleshooting de despliegue, monitoreo, logs |
| **QA** | Revisión de PRs, tests manuales, reporte de bugs |
| **Tiempo** | 10% del tiempo (4h/semana) |
| **Herramientas** | GitHub, Docker, VS Code, pytest |

---

## 3. RESPONSABILIDADES POR MÓDULO

| Módulo | Lead | Responsable | Apoyo | Revisión |
|--------|------|-------------|-------|----------|
| 001 Registro Anónimo | ODIN | ODIN | — | ZEUS |
| 002 Consulta Semáforo | ODIN | ODIN | Zaira (landing) | ZEUS |
| 003 IA Triage | ODIN | ODIN | — | ZEUS (fairness), Diana (legal) |
| 004 Clustering + Perfil | ODIN | ODIN | — | ZEUS, Diana (privacidad) |
| 005 Panel Admin | ODIN | ODIN | Juan (QA) | ZEUS (seguridad) |
| 006 Pasarela Institucional | ODIN | ODIN | — | ZEUS, Diana (legal) |
| 007 Producción + Piloto | ODIN | ODIN | Juan (soporte) | ZEUS, Jelkin (autoridades) |
| Marketing + Branding | Zaira | Zaira | — | Jelkin |
| Legal + Compliance | Diana | Diana | — | Jelkin |
| Gestión + PM2 | ZEUS | ZEUS | — | Jelkin |

---

## 4. COMUNICACIÓN Y REUNIONES

| Reunión | Frecuencia | Participantes | Propósito | Duración |
|---------|------------|---------------|-----------|----------|
| Daily Standup | Diaria | ODIN, ZEUS (async) | Progreso, bloqueos, plan del día | 15 min |
| Weekly Review | Semanal | Todos | Demo de avance, revisión de hitos, decisiones | 1h |
| Monthly Strategy | Mensual | Jelkin, ZEUS, Diana | Estrategia, negocio, riesgos, dirección | 2h |
| Quarterly Planning | Trimestral | Todos | Planificación de siguiente trimestre, objetivos, recursos | 4h |
| Ad-hoc Legal | Bajo demanda | Diana, Jelkin, ZEUS | Decisiones legales, contratos, compliance | 30-60 min |
| Ad-hoc Marketing | Bajo demanda | Zaira, Jelkin, ZEUS | Campañas, colegios, PR, growth | 30-60 min |

### Canales de Comunicación

| Canal | Uso | Herramienta |
|-------|-----|-------------|
| Chat async | Preguntas rápidas, updates, decisiones menores | WhatsApp / Telegram |
| Documentos | Especificaciones, PM2, ADRs, decisiones | GitHub (Markdown) |
| Reuniones | Demos, reviews, estrategia, decisiones | Google Meet / Zoom |
| Tareas | Seguimiento de tareas, bugs, features | GitHub Issues |
| Código | Repositorio, PRs, reviews, CI/CD | GitHub |

---

## 5. RACI POR ÁREA

| Área | Jelkin | ZEUS | Diana | Zaira | ODIN | Juan |
|------|--------|------|-------|-------|------|------|
| **Estrategia de negocio** | A | R | C | C | I | I |
| **Gestión de proyecto** | I | A/R | I | I | C | I |
| **Legal / Compliance** | A | C | R | I | C | I |
| **Marketing / Branding** | A | C | I | R | I | I |
| **Desarrollo frontend** | I | I | I | C | A/R | C |
| **Desarrollo backend** | I | I | I | I | A/R | C |
| **IA / ML** | I | C | I | I | A/R | I |
| **Seguridad / Encriptación** | I | C | C | I | A/R | I |
| **Infraestructura / Deploy** | I | C | I | I | A/R | C |
| **QA / Tests** | I | C | I | I | A/R | C |
| **Documentación técnica** | I | C | I | I | A/R | C |
| **Contacto instituciones** | A/R | C | C | C | I | I |
| **Contacto colegios** | A | C | I | R | I | I |
| **Auditoría de seguridad** | A | C | C | I | R | C |

**Leyenda:** R = Responsible (ejecuta), A = Accountable (aprueba), C = Consulted (consulta), I = Informed (informado)

---

## 6. COMPETENCIAS Y FORMACIÓN

| Miembro | Competencias Clave | Necesidad de Formación |
|---------|-------------------|----------------------|
| Jelkin | Estrategia, negociación, visión | — |
| ZEUS | PM2, análisis de negocio, documentación | — (AI) |
| Diana | Derecho administrativo, protección de datos | Tecnología cívica, modelos de negocio digital |
| Zaira | Marketing digital, redes sociales, branding | Product marketing, SaaS metrics, growth hacking |
| ODIN | Desarrollo full-stack, IA, seguridad | — (AI) |
| Juan | Soporte técnico, QA, troubleshooting | React, FastAPI, Docker, pytest (backup técnico) |

### Plan de Formación

| Miembro | Formación | Fuente | Duración | Fecha |
|---------|-----------|--------|----------|-------|
| Juan | React 19 + Vite + Tailwind | Documentación oficial + cursos online | 20h | Julio 2026 |
| Juan | FastAPI + SQLAlchemy | Documentación oficial + tutoriales | 15h | Agosto 2026 |
| Juan | Docker + Docker Compose | Documentación oficial | 10h | Septiembre 2026 |
| Diana | Protección de datos en plataformas digitales | Curso online (SIC Colombia) | 8h | Julio 2026 |
| Zaira | Product Marketing para SaaS | Reforge, CXL, o similar | 20h | Agosto 2026 |
| Zaira | Growth Hacking para B2B2C | Reforge, CXL, o similar | 15h | Septiembre 2026 |

---

## 7. CONTRATACIÓN Y RECURSOS EXTERNOS

| Recurso | Rol | Cuándo | Costo estimado | Fuente |
|---------|-----|--------|----------------|--------|
| Auditoría de seguridad externa | Pentest + OWASP ZAP | Noviembre 2026 | $3,000-$5,000 USD | Firma de seguridad colombiana |
| Diseño gráfico (branding) | Logo, branding, landing page | Julio 2026 | $500-$1,000 USD | Freelancer o agencia local |
| Traducción i18n | Portugués, inglés | 2027 | $500-$1,000 USD | Freelancer |
| Abogado especializado | Contratos B2G, seguro | Bajo demanda | $200-$500/hr | Firma legal colombiana |
| Consultor IA | Revisión de modelo, fairness | Agosto 2026 | $1,000-$2,000 USD | Freelancer o académico |
| Community manager | Redes sociales, soporte | Diciembre 2026 | $500-$1,000/mes | Freelancer o Zaira |

---

## 8. DECISIONES PENDIENTES DE RECURSOS

| # | Decisión | Opciones | Recomendación ZEUS | Estado |
|---|----------|----------|---------------------|--------|
| 1 | ¿Contratar desarrollador adicional? | Sí (junior) / No (ODIN + Juan) / Sí (senior) | **No por ahora**. ODIN + Juan como backup es suficiente. Evaluar si escala a 10,000+ usuarios. | Pendiente |
| 2 | ¿Contratar auditoría de seguridad externa? | Sí, antes de producción / No, solo interna / Sí, después de piloto | **Sí, antes de producción** (noviembre 2026). Presupuesto $3,000-$5,000. | Pendiente |
| 3 | ¿Contratar diseñador gráfico? | Sí, para branding / No, Zaira + Canva / Sí, para landing page | **Sí, para branding y landing page** (julio 2026). Presupuesto $500-$1,000. | Pendiente |
| 4 | ¿Contratar community manager? | Sí, a tiempo parcial / No, Zaira lo maneja / Sí, full-time | **No por ahora**. Zaira maneja marketing. Evaluar si hay 1,000+ usuarios activos. | Pendiente |
| 5 | ¿Contratar consultor IA? | Sí, para revisión de fairness / No, ODIN maneja / Sí, para mejora de modelo | **Sí, para revisión de fairness** (agosto 2026). Presupuesto $1,000-$2,000. | Pendiente |

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Equipo y roles del Semáforo de Confianza*
