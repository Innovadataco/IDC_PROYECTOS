# CASO DE NEGOCIO — Semáforo de Confianza

## Proyecto: 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS
**Aprobador:** Jelkin Zair Carrillo Franco (CEO)

---

## 1. JUSTIFICACIÓN ESTRATÉGICA

### Problema
- La protección de menores es una responsabilidad compartida entre Estado, comunidad y ciudadanía.
- En Colombia y Latinoamérica, la falta de canales seguros y anónimos para reportar contactos inapropiados crea una barrera de silencio que protege a los agresores.
- Se estima que solo 1 de cada 10 casos de abuso infantil llega a autoridades. El 90% permanece en la comunidad, silenciado.
- No existe una plataforma donde padres y colegios puedan **consultar preventivamente** si un contacto tiene historial de reportes.

### Oportunidad
Innovadataco puede construir una plataforma tecnológica de impacto social que:
- Empodere a ciudadanos, padres y colegios para **consultar** y **reportar** sin exponer su identidad.
- Genere datos estructurados para autoridades y organizaciones de protección.
- Demuestre la capacidad de Innovadataco para desarrollar productos propios con stack moderno y seguridad robusta.
- Sirva como caso de estudio y portafolio para futuros proyectos de gobierno digital, seguridad ciudadana y EdTech.

---

## 2. ANÁLISIS DE COSTO-BENEFICIO

| Concepto | Valor |
|----------|-------|
| **Inversión estimada (Módulos 001-006)** | $20,000 — $35,000 USD |
| **Tiempo de desarrollo** | 20-24 semanas |
| **Equipo requerido** | 1-2 desarrolladores (ODIN + soporte humano) |
| **Infraestructura anual** | $500 — $2,000 USD (VPS/cloud) |
| **Beneficio social** | Protección de menores, empoderamiento ciudadano, prevención |
| **Beneficio empresarial** | Producto propietario, portafolio, credibilidad en seguridad digital |
| **Modelo de sostenibilidad** | Freemium B2C + B2B2C colegios + contratos con gobierno / ONGs |
| **ROI estratégico** | Alto (posicionamiento en tecnología cívica + protección social + EdTech) |

---

## 3. MODELO DE NEGOCIO

### Freemium B2C

| Plan | Precio | Funcionalidad |
|------|--------|---------------|
| **Gratuito** | $0 | 3 consultas/día, reportes anónimos ilimitados |
| **Premium** | $2.99/mes | Consultas ilimitadas, alertas por email, historial de reportes |

### B2B2C — Instituciones Educativas

| Plan | Precio | Funcionalidad |
|------|--------|---------------|
| **Colegio Básico** | $1,000/año | Panel de consulta para padres, reportes ilimitados, alertas institucionales |
| **Colegio Premium** | $2,500/año | Todo Básico + API de integración, dashboard de tendencias, soporte prioritario |
| **Distrito Educativo** | Custom | Multi-colegio, analytics agregado, pasarela directa con autoridades |

### B2G — Autoridades (Futuro)

- Contratos de servicio con ICBF, Fiscalía, o programas de cooperación internacional.
- Piloto gratuito 3 meses para construir credibilidad y case study.

---

## 4. ALINEACIÓN CON OBJETIVOS DE INNOVADATACO

| Objetivo Empresarial | Alineación |
|----------------------|------------|
| Demostrar capacidad técnica end-to-end | ✅ Stack completo: React 19 + PWA + FastAPI + encriptación + IA + deploy |
| Construir productos propios | ✅ Producto propietario, no consultoría por horas |
| Generar impacto social medible | ✅ Reportes procesados, menores protegidos, consultas realizadas |
| Fortalecer portafolio para licitaciones | ✅ Caso de éxito en gobierno digital, seguridad, EdTech |
| Aprendizaje organizacional | ✅ SDD, encriptación, anonimato, seguridad OWASP, IA NLP, PWA |

---

## 5. RIESGOS DEL NO-PROYECTO

| Riesgo | Impacto |
|--------|---------|
| Pérdida de oportunidad en tecnología cívica y EdTech | Innovadataco no entra a mercados de alto crecimiento y baja oferta tecnológica. |
| Débil diferenciación técnica | Sin proyectos propios, la empresa sigue dependiendo 100% de contratos externos. |
| Sin caso de éxito para licitaciones | Dificultad para demostrar capacidad en RFPs de gobierno digital. |
| Frustración del equipo fundador | El proyecto nace de una necesidad real detectada por Jelkin; abandonarlo resta motivación. |

---

## 6. PROPUESTA DE VALOR

> **"Un buscador de confianza donde cualquier persona puede consultar si un contacto ha sido reportado como riesgo para menores, y reportar contactos inapropiados sin exponer su identidad, generando alertas estructuradas para las autoridades."**

**Diferenciadores clave:**
1. **Anonimato absoluto:** Sin IP, sin cookies, sin metadata, sin sesión.
2. **Encriptación industrial:** AES-256-GCM con DEK por campo, incluyendo evidencia multimedia.
3. **Semáforo de Confianza:** Visualización clara de riesgo comunitario, sin acusar.
4. **PWA sin fricción:** Sin descarga, sin tienda, sin tracking, sin metadata de instalación.
5. **IA de triage:** Clasificación automática, detección de grooming, scoring de riesgo.
6. **Diseñado para LATAM:** En español, pensado para contextos de infraestructura variable.
7. **Modelo freemium:** Sostenible sin depender 100% de contratos gubernamentales.

---

## 7. CRITERIOS DE ÉXITO

| Criterio | Métrica | Meta |
|----------|---------|------|
| Consultas realizadas | Número de consultas al semáforo | > 1,000 en primer mes |
| Reportes procesados | Reportes anónimos válidos | > 100 en primer mes |
| Seguridad técnica | Cobertura de tests + auditoría OWASP | 100% tests pasan, 0 vuln críticas |
| Adopción de autoridades | Instituciones conectadas al panel | 1-3 en fase piloto |
| Satisfacción reportante | UX simple, < 2 minutos por reporte | Formulario de 3 campos máximo |
| Satisfacción consultante | Resultado en < 2 segundos | 95 percentile < 500ms |
| Sostenibilidad | Costos operativos cubiertos | 12 meses con modelo freemium + B2B2C |

---

## 8. DECISIÓN

**Recomendación:** Aprobar el proyecto y asignar recursos para completar los 6 módulos planificados.

**Justificación:**
- Inversión baja, impacto social alto, aprendizaje técnico estratégico.
- Módulo 001 ya completado (registro anónimo) demuestra viabilidad técnica.
- El pivote a PWA + Semáforo de Confianza + modelo freemium aumenta la viabilidad comercial.
- El proyecto posiciona a Innovadataco en sectores de alto crecimiento: tecnología cívica, protección social, EdTech.
- Stack y metodología (SDD + ODIN) son replicables para futuros productos.

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Pivote PWA + Semáforo de Confianza + Freemium B2C + B2B2C*
