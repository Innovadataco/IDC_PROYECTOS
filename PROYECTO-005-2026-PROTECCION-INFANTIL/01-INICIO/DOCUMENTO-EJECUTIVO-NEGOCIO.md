# DOCUMENTO EJECUTIVO DE NEGOCIO

## PROYECTO-005: Protección Infantil Comunitaria

**Código:** IDC_2026_05  
**Fecha:** 13 de junio de 2026  
**Versión:** 1.0 — Borrador para aprobación del CEO  
**Autor:** ZEUS EOS (Inteligencia Estratégica — Innovadataco)  
**Destinatario:** Jelkin Zair Carrillo Franco, CEO Innovadataco  
**Clasificación:** Uso interno — Decisión estratégica

---

## 1. RESUMEN EJECUTIVO PARA EL CEO

Este documento consolida la propuesta de negocio del **Proyecto-005: Protección Infantil Comunitaria**, una plataforma digital propiedad de Innovadataco diseñada para que ciudadanos y padres reporten, de forma anónima y segura, contactos inapropiados o intentos de abuso hacia menores.

**Estado actual:** El Módulo 001 (registro anónimo) está completamente desarrollado y probado. La plataforma ya puede recibir reportes encriptados con seguridad de nivel industrial. **El paso siguiente es una decisión de negocio:** definir quién opera el sistema, cómo se sostiene financieramente, y cuál es la ruta para convertir este producto propio en un activo estratégico para la empresa.

**Pregunta central para tu aprobación:** ¿Innovadataco se posiciona como un proveedor tecnológico de infraestructura de protección infantil, o como un operador directo de alertas? Esta decisión define el modelo de negocio, los riesgos legales asumidos y la arquitectura de los próximos módulos.

---

## 2. PROPUESTA DE VALOR DEL NEGOCIO

### 2.1 ¿Qué problema resuelve?

En Colombia y Latinoamérica, la denuncia de abuso infantil enfrenta una barrera de silencio estructural:

- **El miedo a la identificación:** Los canales actuales (Fiscalía, ICBF, líneas telefónicas) requieren, en la práctica, que el denunciante se identifique. Esto genera represalias sociales, familiares o laborales contra quien reporta.
- **La baja tasa de reporte:** Se estima que solo 1 de cada 10 casos de abuso infantil llega a autoridades. El 90% restante permanece en la comunidad, silenciado.
- **La falta de datos estructurados:** Las autoridades reciben denuncias fragmentadas, sin capacidad de cruzar información ni detectar patrones (mismo agresor, zona de riesgo, modus operandi).

**La plataforma resuelve esto mediante anonimato absoluto + encriptación industrial + agregación de datos.** Un ciudadano reporta sin exponer su identidad. Las autoridades reciben alertas estructuradas con datos útiles, no ruido.

### 2.2 ¿Para quién?

| Segmento | Rol | Necesidad cubierta |
|----------|-----|-------------------|
| **Ciudadanos / Padres** | Usuario final | Reportar sin miedo, obtener confirmación de envío |
| **Autoridades (ICBF, Fiscalía, Policía)** | Receptor de alertas | Recibir datos estructurados, detectar patrones, priorizar casos |
| **Innovadataco** | Propietario del producto | Demostrar capacidad técnica, generar ingresos, crear impacto social medible |

### 2.3 ¿Cómo se monetiza o sostiene?

**Este es un punto de decisión que requiere tu aprobación.** Identifico tres modelos de negocio viables, no excluyentes entre sí:

**Modelo A: SaaS para Instituciones (B2G / B2B)**
- Innovadataco vende licencias del software a gobiernos, alcaldías, departamentos o ONGs.
- El cliente instala la plataforma en su infraestructura y opera sus propios reportes.
- **Ingreso:** Licencias anuales + soporte técnico.
- **Ejemplo:** Alcaldía de Bogotá compra la plataforma para operarla como canal de denuncia comunitaria.
- **Riesgo:** Ciclo de ventas largo en gobierno. Requiere certificaciones y relaciones institucionales.

**Modelo B: Operador de Alertas (B2G como servicio)**
- Innovadataco opera la plataforma centralizada (como un SaaS propio), recibe reportes, y enruta alertas agregadas a autoridades competentes.
- **Ingreso:** Contratos de servicio con ICBF, Fiscalía, o programas de cooperación internacional (USAID, BID, PNUD).
- **Ejemplo:** Innovadataco firma un contrato anual con ICBF para canalizar alertas de 5 municipios piloto.
- **Riesgo:** Responsabilidad legal directa si una alerta no se procesa. Requiere seguros y respaldo legal sólido.

**Modelo C: Open Source + Servicios Profesionales**
- El código es abierto (lo cual genera credibilidad y auditoría de seguridad por la comunidad).
- Innovadataco cobra por implementación, personalización, soporte y auditoría de seguridad.
- **Ingreso:** Servicios profesionales + soporte enterprise.
- **Ejemplo:** Una ONG internacional usa el código abierto, pero contrata a Innovadataco para desplegarlo en 3 países.
- **Riesgo:** Menor barrera de entrada para competidores. La ventaja es la marca y la relación con autoridades.

**Recomendación ZEUS:** Iniciar con **Modelo C** (open source + servicios) para los primeros 6 meses, mientras se construye credibilidad y casos de éxito. Migrar a **Modelo B** (operador de alertas) una vez que Diana valide la responsabilidad legal y se tenga un contrato piloto con una autoridad. El **Modelo A** (licencias) puede ser una línea secundaria en el futuro.

---

## 3. ALCANCE COMPLETO DEL PRODUCTO

### 3.1 Qué INCLUYE (alcance actual + planificado)

| Módulo | Funcionalidad | Estado |
|--------|--------------|--------|
| **001 — Registro Anónimo** | Formulario web/móvil, API REST, encriptación AES-256-GCM, rate limiting, hash de confirmación | ✅ Completado (junio 2026) |
| **002 — Panel de Administración** | Autenticación segura, dashboard de reportes, desencriptación bajo demanda, cambio de estado, export de datos | ⬜ Planificado (julio 2026) |
| **003 — Notificaciones a Autoridades** | Integración con ICBF/Fiscalía/Policía, alertas automáticas por severidad, resúmenes periódicos | ⬜ Planificado (agosto 2026) |
| **004 — Inteligencia y Scoring** | Detección de patrones (mismo identificador reportado múltiples veces), scoring de urgencia, clustering geográfico, detección de spam | ⬜ Planificado (septiembre 2026) |
| **Infraestructura** | Deploy en VPS/cloud, PostgreSQL, Redis, TLS 1.3, backups automatizados, monitoreo | ⬜ Planificado (paralelo a módulos) |
| **Documentación** | PM2 completo, SDD (specs, ADRs, tasks), runbooks de operación, guía de seguridad | 📝 En progreso (PM2 Inicio completado) |

### 3.2 Qué NO INCLUYE (límites explícitos del producto)

- **Investigación judicial:** La plataforma genera alertas, no pruebas. La investigación y acción legal son responsabilidad de las autoridades.
- **Atención psicológica a víctimas:** No es una línea de atención directa. Es una herramienta de reporte y alerta.
- **Operación 24/7 de respuesta humana:** El sistema es automatizado. Si opera bajo Modelo B, Innovadataco necesitaría definir si tiene un equipo de revisión humana o si delega eso a la autoridad contratante.
- **Aplicaciones nativas iOS/Android:** Se usa PWA (Progressive Web App) que funciona en cualquier navegador móvil. Apps nativas quedan fuera del alcance inicial.
- **Despliegue en países sin marco legal de protección infantil:** Cada país requiere análisis legal específico antes de operar.

---

## 4. OBJETIVOS ESTRATÉGICOS Y OPERATIVOS

### 4.1 Horizonte 12 meses (junio 2026 — junio 2027)

| Objetivo | Tipo | Meta | Indicador |
|----------|------|------|-----------|
| **4.1.1** Completar los 4 módulos funcionales | Operativo | 100% de módulos en producción | Dashboard de módulos desplegados |
| **4.1.2** Tener un piloto con al menos 1 autoridad colombiana | Estratégico | Contrato o carta de intención firmada | Documento contractual |
| **4.1.3** Procesar 500+ reportes reales en producción | Operativo | 500 reportes en primer año | Métrica de base de datos |
| **4.1.4** Posicionar a Innovadataco como referente en tecnología cívica | Estratégico | 1 publicación en medios o 1 charla en evento de gobierno digital | Métrica de marketing (Zaira) |
| **4.1.5** Generar primer ingreso recurrente por el producto | Estratégico | $10,000 USD anuales por licencias o contratos | Estado financiero |
| **4.1.6** Pasar auditoría de seguridad externa (OWASP ZAP + pentest) | Operativo | 0 vulnerabilidades críticas | Reporte de auditoría |

### 4.2 Horizonte 18 meses (junio 2026 — diciembre 2027)

| Objetivo | Tipo | Meta | Indicador |
|----------|------|------|-----------|
| **4.2.1** Operar en 2+ municipios o departamentos de Colombia | Estratégico | 2 contratos activos o cartas de intención | Cartera de clientes |
| **4.2.2** Scoring de IA con precisión > 80% en detección de patrones | Operativo | Validación con datos histónicos de autoridades | Métrica de ML |
| **4.2.3** Expandir a 1 país de Latinoamérica (pilot) | Estratégico | Implementación en México, Perú o Chile | Contrato o carta de intención |
| **4.2.4** Generar $50,000 USD anuales recurrentes por el producto | Estratégico | Ingresos anuales por producto | Estado financiero |
| **4.2.5** Tener un equipo de operación dedicado (mínimo 1 persona) | Operativo | 1 FTE contratado para operación/soporte | Nómina |

---

## 5. RIESGOS DEL NEGOCIO Y DEL PROYECTO

### 5.1 Riesgos de Negocio (decisión estratégica)

| ID | Riesgo | Probabilidad | Impacto | Estrategia de mitigación | Responsable |
|----|--------|-------------|---------|-------------------------|-------------|
| **RN-01** | **Responsabilidad legal si un reporte no se procesa** y ocurre un daño a un menor. | Media | **Catastrófico** | Definir claramente que Innovadataco es un **canal tecnológico**, no un operador de respuesta. En Modelo B, contrato de seguro de responsabilidad civil y cláusula de limitación de responsabilidad. | Diana (Legal) |
| **RN-02** | **Falta de adopción por autoridades.** ICBF o Fiscalía no integran el sistema por burocracia o desconfianza. | Alta | Alto | Iniciar con Modelo C (open source) para eliminar barreras. Construir casos de éxito en municipios pequeños antes de ir a nivel nacional. | Jelkin (CEO) |
| **RN-03** | **Reputación:** Si el sistema es hackeado o filtra datos, la marca Innovadataco queda comprometida. | Baja | **Catastrófico** | Inversión en seguridad desde el día 1 (ya está en Módulo 001). Auditoría externa antes de producción. Open source para auditoría comunitaria. | ODIN + ZEUS |
| **RN-04** | **Modelo de negocio no viable:** No se consiguen contratos ni ingresos en 18 meses. | Media | Alto | Mantener costos bajos. El producto es propio, no hay costo de desarrollo externo (ODIN desarrolla). Infraestructura VPS económica ($50-200/mes). Diversificar a Modelo C (servicios). | Jelkin (CEO) |
| **RN-05** | **Spam y falsos reportes** que saturan el sistema y deslegitiman las alertas. | Media | Medio | Rate limiting (ya implementado) + scoring de IA (Módulo 004) + revisión humana en panel de admin. | ODIN + ZEUS |
| **RN-06** | **Cambio de gobierno o política pública** elimina el programa de protección infantil que financia el proyecto. | Baja | Alto | No depender de una sola fuente de financiación. Diversificar a ONGs internacionales y cooperación. | Jelkin (CEO) |
| **RN-07** | **Competencia de grandes tecnológicas** (Google, Microsoft, ONGs globales) lanzan solución similar. | Baja | Medio | Diferenciación: anonimato absoluto + encriptación local + diseño para LATAM. Velocidad de ejecución como ventaja. | ZEUS (Estrategia) |

### 5.2 Riesgos de Proyecto (ejecución)

| ID | Riesgo | Probabilidad | Impacto | Mitigación | Responsable |
|----|--------|-------------|---------|------------|-------------|
| **RP-01** | Dependencia técnica de ODIN como único desarrollador. | Media | Alto | Documentación SDD completa permite transferencia. Juan como backup técnico. | ZEUS |
| **RP-02** | Falta de proveedor de deploy definido. | Media | Medio | Evaluar 3 opciones (DigitalOcean, Hetzner, AWS Lightsail) en 7 días. | Jelkin + ZEUS |
| **RP-03** | Cambio de requisitos legales de protección de datos menores. | Baja | Alto | Diana monitorea normativa. Arquitectura modular permite adaptación. | Diana |
| **RP-04** | Clave de encriptación comprometida. | Baja | **Catastrófico** | Rotación manual, generación con openssl, almacenamiento en variables de entorno. Plan de respuesta a incidentes. | ODIN |

---

## 6. ETAPAS Y FASES — ROADMAP DE MÓDULOS

### 6.1 Timeline Realista (junio 2026 — enero 2027)

```
Junio 2026  │███ Módulo 001 (completado) + PM2 Inicio (completado)
            │
Julio 2026  │████ Módulo 002: Panel de Admin + Auth
            │     + Decisión de modelo de negocio
            │     + Definición de proveedor de infraestructura
            │     + Revisión legal por Diana (responsabilidad)
            │
Agosto 2026 │████ Módulo 003: Notificaciones a Autoridades
            │     + Primer contacto formal con ICBF/Fiscalía
            │     + Demo del sistema a stakeholders
            │
Sep 2026    │████ Módulo 004: IA / Scoring / Detección de Patrones
            │     + Auditoría de seguridad externa (OWASP ZAP + pentest)
            │     + Lanzamiento de MVP en producción (staging → prod)
            │
Oct 2026    │███ Piloto con 1 autoridad o municipio
            │     + Capacitación de operadores
            │     + Recolección de feedback real
            │
Nov-Dic 2026│███ Iteración y mejora post-piloto
            │     + Ajustes de UX basados en datos reales
            │     + Marketing y posicionamiento (Zaira)
            │
Ene 2027    │███ Negociación de contratos y escalamiento
            │     + Definición de ingresos recurrentes
            │     + Plan de expansión a otros municipios/países
```

### 6.2 Dependencias entre Módulos

- **Módulo 002 depende de:** Decisión de modelo de negocio (¿quién opera el panel?) y aprobación legal de Diana.
- **Módulo 003 depende de:** Módulo 002 (necesita panel funcional para validar reportes antes de notificar) + contacto con autoridades.
- **Módulo 004 depende de:** Módulo 003 (necesita datos de notificación para entrenar scoring) + datos históricos de autoridades (si consiguen compartir).
- **Deploy a producción depende de:** Módulo 002 (panel admin es más crítico que el formulario) + proveedor de infraestructura elegido.

---

## 7. STAKEHOLDERS Y USUARIOS

### 7.1 ¿Quién usa la herramienta?

| Rol | Descripción | Motivación | Frecuencia de uso |
|-----|-------------|------------|-------------------|
| **Ciudadano / Padre** | Persona que reporta un incidente o sospecha | Proteger a un menor sin exponer su identidad | Esporádica (cuando hay un incidente) |
| **Operador de Autoridad** | Funcionario de ICBF, Fiscalía o Policía que revisa reportes | Recibir alertas estructuradas y actuar | Diaria (si hay reportes) |
| **Administrador de Innovadataco** | Equipo técnico que monitorea el sistema | Garantizar disponibilidad, seguridad y calidad | Diaria (monitoreo) |

### 7.2 ¿Quién la administra?

**Punto de decisión para Jelkin:**

- **Opción A:** Innovadataco administra todo (panel de control, revisión de reportes, notificación a autoridades). Mayor control, mayor responsabilidad legal.
- **Opción B:** La autoridad contratante administra el panel. Innovadataco solo provee el software. Menor responsabilidad, pero menos control de calidad.
- **Opción C:** Híbrido. Innovadataco filtra spam y valida formato, la autoridad recibe solo reportes verificados. Modelo intermediario.

**Recomendación ZEUS:** Iniciar con **Opción C** (híbrido) durante el piloto. Innovadataco opera un panel de triaje básico (eliminar spam, verificar que el reporte tiene datos mínimos), y la autoridad recibe alertas pre-validadas. Esto construye confianza y demuestra valor sin asumir responsabilidad legal completa.

### 7.3 ¿Quién la paga?

| Escenario | Pagador | Monto estimado | Condición |
|-----------|---------|---------------|-----------|
| Piloto con ICBF | ICBF o programa de cooperación | $15,000-$30,000 USD/año | Contrato de servicio (Modelo B) |
| Licencia a alcaldía | Alcaldía o gobernación | $5,000-$10,000 USD/año | Licencia de software (Modelo A) |
| Implementación internacional | ONG o agencia de cooperación | $20,000-$50,000 USD | Servicios profesionales (Modelo C) |
| Operación propia | Innovadataco (inversión propia) | $2,000-$5,000 USD/año | Infra + mantenimiento hasta primer contrato |

---

## 8. PROPUESTA DE NEGOCIO: MODELO DE SOSTENIBILIDAD

### 8.1 Costos estimados (12 meses)

| Concepto | Costo estimado (USD) | Nota |
|----------|----------------------|------|
| Infraestructura (VPS, BD, TLS, backups) | $2,000-$4,000 | DigitalOcean o Hetzner. Depende de tráfico. |
| Auditoría de seguridad externa | $3,000-$5,000 | Pentest + OWASP ZAP. Una vez al año. |
| Seguro de responsabilidad civil (si aplica) | $1,000-$3,000 | Si opera bajo Modelo B. |
| Tiempo de ODIN (desarrollo) | $0 | Costo interno, no externo. |
| Tiempo de ZEUS (gestión + PM2) | $0 | Costo interno. |
| Tiempo de Diana (revisión legal) | $0 | Costo interno. |
| Marketing y posicionamiento (Zaira) | $500-$2,000 | Redes sociales, eventos, contenido. |
| **Total costo anual estimado** | **$6,500-$14,000 USD** | |

### 8.2 Ingresos objetivo (12 meses)

| Escenario | Ingreso estimado (USD) | Probabilidad |
|-----------|------------------------|-------------|
| Pessimista: Sin contratos, solo marketing de marca | $0 | 30% |
| Moderado: 1 contrato piloto con ICBF o alcaldía | $15,000-$30,000 | 50% |
| Optimista: 2 contratos + 1 implementación internacional | $50,000-$80,000 | 20% |

**Punto de equilibrio:** Con $6,500-$14,000 USD de costos anuales, el proyecto se sostiene con **un solo contrato piloto** (escenario moderado). La inversión principal es tiempo interno, no dinero.

### 8.3 ¿Contratos con ICBF/Fiscalía? ¿Cómo llegar?

**Ruta recomendada:**

1. **Mes 1-2 (julio-agosto):** Completar Módulo 002 (panel admin). Preparar demo funcional.
2. **Mes 3 (septiembre):** Contactar la **Línea 141 del ICBF** (teléfono de denuncia) y ofrecer una integración tecnológica. Buscar el contacto de dirección de innovación o tecnología del ICBF.
3. **Mes 3-4 (septiembre-octubre):** Presentar demo a la **Fiscalía General de la Nación** (Unidad de Delitos Sexuales y Violencia Intrafamiliar). Ofrecer piloto gratuito de 3 meses.
4. **Paralelo:** Postular el proyecto a convocatorias de **MinTIC** (Ministerio de TIC) o **BID Lab** (Laboratorio de Innovación del BID).
5. **Mes 6-12:** Negociar contrato piloto. Innovadataco puede ofrecer el piloto a costo de infraestructura ($0 de licencia) para construir credibilidad y case study.

**Nota:** Esta ruta requiere que Jelkin o Diana activen sus redes de contacto institucionales. ZEUS puede preparar cartas, propuestas y demos, pero no tiene capacidad de networking humano.

---

## 9. DECISIONES PENDIENTES DEL CEO

Para avanzar, necesito tu decisión explícita en los siguientes puntos:

| # | Decisión | Opciones | Tu respuesta |
|---|----------|----------|--------------|
| **1** | **Modelo de negocio prioritario** | A) SaaS licencias / B) Operador de alertas / C) Open source + servicios / D) Híbrido | **¿?** |
| **2** | **¿Quién opera el panel de admin?** | A) Innovadataco / B) Autoridad contratante / C) Híbrido (triaje Innovadataco + acción autoridad) | **¿?** |
| **3** | **Proveedor de infraestructura** | A) DigitalOcean / B) Hetzner / C) AWS Lightsail / D) Otro | **¿?** |
| **4** | **¿Aprobamos Módulo 002?** | Sí, prioridad inmediata / Sí, pero después de otro proyecto / No, pausar | **¿?** |
| **5** | **¿Contactamos ICBF/Fiscalía ahora?** | Sí, preparar demo y carta / No, esperar a Módulo 003 / No, esperar a MVP completo | **¿?** |
| **6** | **Responsabilidad legal: ¿Innovadataco asume riesgo de operación?** | Sí, con seguro y contrato / No, solo proveemos tecnología / A definir con Diana | **¿?** |

---

## 10. ANEXOS Y REFERENCIAS

- **Artefactos PM2 completos:** `IDC_PROYECTOS/PROYECTO-005-2026-PROTECCION-INFANTIL/`
- **Código fuente y especificaciones técnicas:** `github.com/Innovadataco/Desarrollos/PROYECTO-005-PROTECCION-INFANTIL/`
- **Especificación Módulo 001:** `specs/001-registro-anonimo/spec.md`
- **Decisión de arquitectura de seguridad:** `specs/001-registro-anonimo/ADR-001-seguridad.md`
- **Normativa de referencia:** Ley 1098 de 2006 (Código de Infancia y Adolescencia, Colombia)

---

> **Documento preparado por ZEUS EOS para decisión del CEO.**
>
> **Estado:** Borrador v1.0 — Listo para revisión y aprobación.
>
> **Próximo paso:** Jelkin revisa, responde las 6 decisiones pendientes, y ZEUS/ODIN proceden según lo indicado.
>
> *ZEUS online. La empresa está operando.* ⚡
