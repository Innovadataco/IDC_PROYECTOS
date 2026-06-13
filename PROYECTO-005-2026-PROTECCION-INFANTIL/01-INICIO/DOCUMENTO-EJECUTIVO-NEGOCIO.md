# DOCUMENTO EJECUTIVO DE NEGOCIO

## PROYECTO-005: Semáforo de Confianza

**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0 — Actualizado con pivote PWA + Semáforo + Freemium B2B2C
**Autor:** ZEUS EOS (Inteligencia Estratégica — Innovadataco)
**Destinatario:** Jelkin Zair Carrillo Franco, CEO Innovadataco
**Clasificación:** Uso interno — Decisión estratégica

---

## 1. RESUMEN EJECUTIVO PARA EL CEO

El Proyecto-005 ha pivotado. Ya no es solo una plataforma de reporte anónimo. Es ahora un **buscador universal de confianza comunitaria** donde padres, colegios y ciudadanos pueden consultar si un número de teléfono, cuenta de redes sociales, email o URL ha sido reportado como riesgo para menores — recibiendo un **Semáforo de Confianza** (🟢🟡🔴⚫). Y reportar, si lo desean, sin exponer su identidad.

**Estado actual:** El Módulo 001 (registro anónimo con evidencia multimedia) está completamente desarrollado y probado. La plataforma ya puede recibir reportes encriptados con seguridad de nivel industrial. El paso siguiente es completar los 5 módulos restantes para tener un producto funcional: buscador, IA de triage, clustering geográfico, panel admin, y pasarela institucional.

**Pregunta central para tu aprobación:** ¿Innovadataco se posiciona como proveedor tecnológico de infraestructura de protección infantil (B2G), como operador directo de alertas (B2G como servicio), o como plataforma freemium B2C + B2B2C para colegios? Esta decisión define el modelo de negocio, los riesgos legales asumidos, y la arquitectura de los próximos módulos.

---

## 2. PROPUESTA DE VALOR DEL NEGOCIO

### 2.1 ¿Qué problema resuelve?

En Colombia y Latinoamérica, la denuncia de abuso infantil enfrenta una barrera de silencio estructural:

- **El miedo a la identificación:** Los canales actuales requieren, en la práctica, que el denunciante se identifique. Esto genera represalias sociales, familiares o laborales.
- **La baja tasa de reporte:** Se estima que solo 1 de cada 10 casos de abuso infantil llega a autoridades. El 90% restante permanece silenciado.
- **La falta de prevención:** Los padres y colegios no tienen forma de verificar si un contacto que interactúa con un menor tiene historial de reportes.
- **La falta de datos estructurados:** Las autoridades reciben denuncias fragmentadas, sin capacidad de cruzar información ni detectar patrones (mismo agresor, red organizada, modus operandi).

**La plataforma resuelve esto mediante:** anonimato absoluto + encriptación industrial + buscador preventivo + IA de triage + agregación de datos + alertas estructuradas.

### 2.2 ¿Para quién?

| Segmento | Rol | Necesidad cubierta | Modelo |
|----------|-----|-------------------|--------|
| **Ciudadanos / Padres** | Usuario final | Consultar si un contacto tiene reportes + reportar sin miedo | Freemium B2C ($2.99/mes Premium) |
| **Colegios / Instituciones educativas** | Comprador institucional | Panel de consulta para padres, reportes ilimitados, alertas institucionales | B2B2C ($1,000-$2,500/año) |
| **Autoridades (ICBF, Fiscalía, Policía)** | Receptor de alertas | Recibir datos estructurados, detectar patrones, priorizar casos | B2G (contrato piloto) |
| **Innovadataco** | Propietario del producto | Demostrar capacidad técnica, generar ingresos, crear impacto social | Producto propio |

### 2.3 ¿Cómo se monetiza?

**Modelo híbrido recomendado por ZEUS:**

1. **Fase 1 (Meses 1-6):** Freemium B2C + B2B2C colegios. Generar ingresos recurrentes para sostener operación.
2. **Fase 2 (Meses 6-12):** Contrato piloto con 1 autoridad colombiana (ICBF o Fiscalía). Construir credibilidad institucional.
3. **Fase 3 (Meses 12-18):** Expandir a más municipios y 1 país de LATAM. Escalar B2B2C a distritos educativos.

**Ingresos objetivo (18 meses):**
- B2C Premium: 200 suscriptores × $2.99/mes × 12 meses = $7,176
- B2B2C Colegios: 10 colegios × $1,500/año = $15,000
- B2G Piloto: 1 contrato × $15,000/año = $15,000
- **Total estimado:** ~$37,000 en 18 meses

**Costos estimados (18 meses):**
- Infraestructura: $3,000
- Auditoría de seguridad: $5,000
- Marketing/posicionamiento: $2,000
- Seguro responsabilidad civil: $2,000
- **Total:** ~$12,000

**Punto de equilibrio:** Con $12,000 de costos, el proyecto se sostiene con **5 colegios B2B2C** o **1 contrato B2G**.

---

## 3. ALCANCE COMPLETO DEL PRODUCTO

### 3.1 Qué INCLUYE (6 módulos)

| Módulo | Funcionalidad | Estado | Fecha |
|--------|--------------|--------|-------|
| **001 — Registro Anónimo** | PWA, formulario, evidencia multimedia, encriptación AES-256-GCM, rate limiting | ✅ Completado | Junio 2026 |
| **002 — Consulta Semáforo** | Buscador universal, normalización de identificadores, semáforo verde/amarillo/rojo/negro | ⬜ Nuevo | Julio 2026 |
| **003 — IA Triage** | NLP ensemble, clasificación, detección de grooming, scoring 0-1, explicabilidad SHAP | ⬜ Nuevo | Agosto 2026 |
| **004 — Clustering + Perfil** | Geocodificación, clustering geográfico, perfil de identificador, detección de red organizada | ⬜ Nuevo | Septiembre 2026 |
| **005 — Panel Admin** | Auth JWT + 2FA, dashboard, desencriptación bajo demanda, audit trail, cambio de estado, export | ⬜ Nuevo | Octubre 2026 |
| **006 — Pasarela Institucional** | API gateway, alertas automáticas, digest diario/semanal/mensual, formatos JSON/PDF/NCMEC | ⬜ Nuevo | Noviembre 2026 |
| **Infraestructura** | Deploy VPS, PostgreSQL 16, Redis 7, TLS 1.3, Docker, GitHub Actions, monitoreo | ⬜ Paralelo | Diciembre 2026 |

### 3.2 Qué NO INCLUYE (límites explícitos)

- Investigación judicial (la plataforma genera alertas, no pruebas)
- Atención psicológica a víctimas (no es línea de atención directa)
- Operación 24/7 de respuesta humana (sistema automatizado, autoridades reciben alertas)
- Aplicaciones nativas iOS/Android (PWA en navegador, suficiente para MVP)
- Despliegue en países sin marco legal de protección infantil (requiere análisis legal por país)
- Scoring de pedofilia (número 0-100) — legalmente conservador, nunca acusar
- Evidencia pública — nunca exponer contenido de reportes
- Alertar al agresor — nunca notificar al identificador reportado

---

## 4. OBJETIVOS ESTRATÉGICOS Y OPERATIVOS

### 4.1 Horizonte 12 meses (junio 2026 — junio 2027)

| Objetivo | Tipo | Meta | Indicador |
|----------|------|------|-----------|
| Completar 6 módulos funcionales | Operativo | 100% en producción | Dashboard de módulos |
| Tener 200 suscriptores B2C Premium | Estratégico | 200 × $2.99/mes | Métrica de Stripe |
| Tener 5 colegios B2B2C | Estratégico | 5 contratos firmados | Cartera de clientes |
| Procesar 500+ reportes reales | Operativo | 500 reportes en DB | Métrica de base de datos |
| Tener 10,000+ consultas al semáforo | Operativo | 10,000 consultas | Métrica de API |
| Posicionar a Innovadataco como referente | Estratégico | 1 publicación en medios o 1 charla | Métrica de marketing |
| Pasar auditoría de seguridad externa | Operativo | 0 vulnerabilidades críticas | Reporte de auditoría |
| Primer contrato con autoridad | Estratégico | Contrato o carta de intención firmada | Documento contractual |

### 4.2 Horizonte 18 meses (junio 2026 — diciembre 2027)

| Objetivo | Tipo | Meta | Indicador |
|----------|------|------|-----------|
| Operar en 2+ municipios o departamentos | Estratégico | 2 contratos activos | Cartera de clientes |
| Scoring de IA con precisión > 85% | Operativo | AUC-ROC > 0.85 | Métrica de ML |
| Expandir a 1 país de LATAM | Estratégico | Implementación en México, Perú o Chile | Contrato o carta |
| Generar $50,000 USD anuales recurrentes | Estratégico | Ingresos anuales por producto | Estado financiero |
| Tener equipo de operación dedicado (1 FTE) | Operativo | 1 contratado para operación/soporte | Nómina |

---

## 5. RIESGOS DEL NEGOCIO Y DEL PROYECTO

### 5.1 Riesgos de Negocio

| ID | Riesgo | Prob | Impacto | Estrategia de mitigación | Responsable |
|----|--------|------|---------|-------------------------|-------------|
| RN-01 | Responsabilidad legal si reporte no se procesa | Media | Catastrófico | Innovadataco es canal tecnológico, no operador. Contrato limita responsabilidad. Seguro de responsabilidad civil. | Diana (Legal) |
| RN-02 | Falta de adopción por autoridades | Alta | Alto | Iniciar con B2C + B2B2C (colegios) para generar ingresos y casos de uso. Luego ir a B2G con credibilidad. | Jelkin (CEO) |
| RN-03 | Reputación: si sistema es hackeado | Baja | Catastrófico | Inversión en seguridad desde día 1. Auditoría externa. Open source para auditoría comunitaria. | ODIN + ZEUS |
| RN-04 | Modelo de negocio no viable (sin ingresos) | Media | Alto | Freemium B2C + B2B2C colegios como base. B2G como línea secundaria. Costos bajos. | Jelkin (CEO) |
| RN-05 | Spam y falsos reportes | Media | Medio | Rate limiting + scoring de IA + revisión humana en panel admin. | ODIN + ZEUS |
| RN-06 | Competencia de grandes tecnológicas | Baja | Medio | Diferenciación: anonimato + encriptación + PWA + diseño LATAM. Velocidad de ejecución. | ZEUS (Estrategia) |
| RN-07 | Colegios no adoptan B2B2C | Media | Alto | Piloto gratuito 1 mes. Demo con datos de impacto. Case study de otros colegios. | Zaira (Marketing) |

### 5.2 Riesgos de Proyecto

| ID | Riesgo | Prob | Impacto | Mitigación | Responsable |
|----|--------|------|---------|------------|-------------|
| RP-01 | Dependencia técnica de ODIN | Media | Alto | Documentación SDD completa. Juan como backup técnico. | ZEUS |
| RP-02 | Dataset de IA insuficiente | Media | Alto | Dataset sintético 1,500 ejemplos + red-teaming. Re-entrenar con 500 reportes reales. | ODIN |
| RP-03 | Clave de encriptación comprometida | Baja | Catastrófico | Rotación manual, KEK en env var, plan de respuesta a incidentes. | ODIN |
| RP-04 | IA sesgada o injusta | Media | Alto | Fairness audit, dataset balanceado, red-teaming. | ODIN + ZEUS |
| RP-05 | Instituciones no integran API | Alta | Medio | Email estructurado como fallback universal. Panel admin como portal web. | ODIN |

---

## 6. ETAPAS Y FASES — ROADMAP

```
Junio 2026  │███ Módulo 001 (completado) + PM2 Inicio
            │
Julio 2026  │████ Módulo 002: Consulta Semáforo + PWA como landing
            │     + Landing page + SEO básico
            │     + Registro de Stripe para pagos
            │
Agosto 2026 │████ Módulo 003: IA Triage
            │     + Dataset + entrenamiento + fairness audit
            │     + Model card + evaluation report
            │
Sep 2026    │████ Módulo 004: Clustering + Perfil
            │     + Geocodificación + detección de redes
            │     + Panel admin de perfiles
            │
Oct 2026    │████ Módulo 005: Panel Admin
            │     + Auth + desencriptación + audit trail + export
            │     + Auditoría de seguridad interna (OWASP ZAP)
            │
Nov 2026    │████ Módulo 006: Pasarela Institucional
            │     + API gateway + alertas + digest + NCMEC
            │     + Primer contacto con ICBF/Fiscalía (demo)
            │
Dic 2026    │███ Producción + Piloto
            │     + Deploy en VPS/cloud
            │     + Piloto con 1 colegio B2B2C
            │     + Marketing de lanzamiento (Zaira)
            │
Ene 2027    │███ Iteración y crecimiento
            │     + Ajustes UX basados en datos reales
            │     + Marketing de crecimiento
            │     + Negociación de contratos B2G
```

---

## 7. DECISIONES PENDIENTES DEL CEO

| # | Decisión | Opciones | Recomendación ZEUS |
|---|----------|----------|-------------------|
| 1 | Modelo de negocio prioritario | B2C freemium / B2B2C colegios / B2G / Híbrido | **Híbrido:** B2C + B2B2C primero, B2G después |
| 2 | ¿Aprobamos los 5 nuevos módulos? | Sí / No (mantener solo 001) / Prioridad baja | **Sí**, en secuencia 002→003→004→005→006 |
| 3 | ¿Proveedor de infraestructura? | DigitalOcean / Hetzner / AWS Lightsail | **DigitalOcean** (mejor UX, buen precio, LATAM-friendly) |
| 4 | ¿Innovadataco asume responsabilidad legal? | Sí, con seguro / No, solo tecnología / A definir con Diana | **No, solo tecnología** hasta primer contrato B2G. Luego definir con Diana. |
| 5 | ¿Contratamos auditoría de seguridad externa? | Sí, antes de producción / No, auditoría interna / Sí, después de piloto | **Sí, antes de producción** (noviembre 2026) |
| 6 | ¿Colegio piloto B2B2C? | Sí, buscar 1 colegio / No, esperar a B2C primero | **Sí, buscar 1 colegio en diciembre 2026** |

---

## 8. ANEXOS Y REFERENCIAS

- Artefactos PM2 completos: `IDC_PROYECTOS/PROYECTO-005-2026-PROTECCION-INFANTIL/`
- Código fuente y especificaciones técnicas: `github.com/Innovadataco/Desarrollos/PROYECTO-005-PROTECCION-INFANTIL/`
- Especificación Módulo 001: `specs/001-registro-anonimo/spec.md`
- ADR-001 (encriptación): `docs/ADR-001-seguridad.md`
- ADR-002 (PWA): `docs/ADR-002-pwa.md`
- ADR-003 (IA NLP): `docs/ADR-003-ia-triage.md`
- ADR-004 (clustering): `docs/ADR-004-clustering.md`
- ADR-005 (pasarela): `docs/ADR-005-pasarela.md`
- Normativa: Ley 1098 de 2006 (Código de Infancia y Adolescencia, Colombia)

---

> **Documento preparado por ZEUS EOS para decisión del CEO.**
>
> **Estado:** Borrador v2.0 — Listo para revisión y aprobación.
>
> *ZEUS online. La empresa está operando.* ⚡
