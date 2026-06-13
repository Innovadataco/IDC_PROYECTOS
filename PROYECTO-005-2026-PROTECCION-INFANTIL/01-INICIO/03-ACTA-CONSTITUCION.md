# ACTA DE CONSTITUCIÓN DEL PROYECTO — Protección Infantil Comunitaria

**Proyecto:** Protección Infantil Comunitaria  
**Código:** IDC_2026_05  
**Cliente:** Innovadataco (Producto Propietario)  
**Fecha:** 13 de junio de 2026  
**Versión:** 1.0

---

## 1. MANDATO DEL PROYECTO

El presente proyecto tiene como objetivo diseñar, desarrollar y desplegar una plataforma digital segura y anónima para reporte comunitario de protección infantil, que permita a ciudadanos, padres y comunidades alertar sobre contactos inapropiados o intentos de abuso hacia menores, garantizando absolutamente el anonimato del reportante y generando alertas estructuradas para autoridades competentes.

---

## 2. OBJETIVOS

### Objetivo General
Construir una plataforma web y móvil (PWA) de reporte anónimo de protección infantil, con 4 módulos funcionales, seguridad de nivel industrial, y capacidad de escalamiento para integración con autoridades colombianas y latinoamericanas.

### Objetivos Específicos
1. **Módulo 001:** Implementar formulario de registro anónimo con encriptación AES-256-GCM y rate limiting. → **COMPLETADO**
2. **Módulo 002:** Construir panel de administración con autenticación segura para revisión de reportes.
3. **Módulo 003:** Implementar sistema de notificaciones automáticas a autoridades (ICBF, Fiscalía, Policía).
4. **Módulo 004:** Desarrollar componente de IA para scoring, detección de patrones y priorización de alertas.
5. **Gobernanza:** Documentar todo el proyecto bajo metodología PM2 con artefactos completos.

---

## 3. ALCANCE

### Incluye
- Plataforma web responsive (React 19 + Vite + Tailwind CSS).
- API REST segura (FastAPI + SQLAlchemy + PostgreSQL/SQLite).
- Encriptación de datos sensibles en reposo (AES-256-GCM con DEK por campo).
- Sistema de reporte 100% anónimo (sin IP, cookies, user-agent ni metadata).
- Rate limiting para protección contra abuso.
- Panel de administración para autoridades (Módulo 002).
- Sistema de notificaciones a autoridades (Módulo 003).
- Componente IA para análisis y priorización (Módulo 004).
- Documentación SDD completa (specs, plans, ADRs, tasks).
- Artefactos PM2 de gestión de proyecto (ZEUS).

### Excluye
- Desarrollo de aplicaciones nativas iOS/Android (se usa PWA).
- Construcción de infraestructura física de red.
- Operación y mantenimiento post-cierre (queda en fase de transición).
- Adquisición de certificados de firma digital para autoridades (por definir).
- Modificación de procesos legales de autoridades (el sistema se adapta a ellos).

---

## 4. RESTRICCIONES

| Tipo | Restricción |
|------|-------------|
| **Legal** | Cumplimiento con Ley 1098 de 2006 (Código de Infancia y Adolescencia Colombiano). |
| **Legal** | Respeto al principio de confidencialidad y anonimato del reportante. |
| **Técnica** | Stack tecnológico definido: React 19 + FastAPI + PostgreSQL + AES-256-GCM. |
| **Técnica** | Cobertura de tests ≥ 80% en cada módulo. |
| **Presupuesto** | Inversión total estimada $15,000 — $25,000 USD (4 módulos + infraestructura). |
| **Plazo** | 12-16 semanas desde aprobación (Módulo 001: 1 semana, ya completado). |
| **Recursos** | Desarrollo principal por ODIN (IA Dev); validación por ZEUS (PMO); decisión por Jelkin (CEO). |

---

## 5. RIESGOS INICIALES

| ID | Riesgo | Probabilidad | Impacto | Mitigación |
|----|--------|-------------|---------|------------|
| R01 | Clave de encriptación comprometida | Baja | Alto | Rotación manual, generación con openssl, almacenamiento seguro en env vars. |
| R02 | Rate limiting en memoria no escala en producción | Media | Medio | Configurar Redis obligatorio en prod; warning si usa memoria. |
| R03 | Abuso del formulario anónimo (spam, falsos reportes) | Media | Medio | Rate limiting + scoring IA (Módulo 004) + revisión humana en panel. |
| R04 | Cambios en requisitos legales de protección infantil | Baja | Alto | Diana (Legal) revisa normativa; sistema diseñado para adaptarse. |
| R05 | Dependencia de ODIN como único desarrollador | Media | Alto | Documentación SDD completa permite transferencia; Juan como backup técnico. |
| R06 | Falta de proveedor de deploy definido | Media | Medio | Evaluar VPS (DigitalOcean, Hetzner), Vercel, Railway, AWS. |
| R07 | Rechazo de autoridades a integrar el sistema | Media | Alto | Pilotear con 1-2 entidades; demostrar valor con datos anónimos agregados. |

---

## 6. GOBERNANZA

| Rol | Responsable | Autoridad |
|-----|-------------|-----------|
| Director de Proyecto | Jelkin Zair Carrillo Franco | Aprueba hitos, presupuesto, alcance |
| Product Owner | Jelkin Zair Carrillo Franco | Define prioridades, valida entregables |
| Comité de Dirección | CEO + Diana Cáceres | Decisiones estratégicas y legales |
| Líder Técnico / Dev | ODIN (Kimi Code CLI) | Desarrollo, arquitectura, SDD |
| PMO / Gestión | ZEUS EOS | PM2, artefactos, seguimiento, calidad |
| Asesor Legal | Diana Cáceres | Validación normativa, protección de datos |
| Soporte Técnico | Juan | Backup técnico, validación de arquitectura |
| Asesor Marketing | Zaira | Posicionamiento, comunicación del producto |

---

## 7. CRITERIOS DE ÉXITO

| Criterio | Métrica | Meta |
|----------|---------|------|
| Entregables técnicos | 4 módulos funcionales | 100% completados |
| Cobertura de tests | pytest + vitest | ≥ 80% |
| Seguridad | OWASP ZAP + checklist | 0 vulnerabilidades críticas |
| Anonimato | Auditoría de metadata | 0 campos identificables en BD |
| Usabilidad | Tiempo de reporte | < 2 minutos |
| Autoridades conectadas | Instituciones piloto | 1-3 en primer año |

---

## 8. FIRMAS

| Rol | Nombre | Firma | Fecha |
|-----|--------|-------|-------|
| Director de Proyecto | Jelkin Zair Carrillo Franco | _________________ | |
| Asesor Legal | Diana Marcela Cáceres Valderrama | _________________ | |
| Líder Técnico | ODIN (CEO IA Dev) | _________________ | |
| PMO | ZEUS EOS | _________________ | |

---

> *Documento generado por ZEUS — Innovadataco*
