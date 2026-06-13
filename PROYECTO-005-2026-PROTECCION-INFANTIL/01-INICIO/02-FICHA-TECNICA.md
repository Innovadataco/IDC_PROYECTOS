# FICHA TÉCNICA — Protección Infantil Comunitaria

## Proyecto: 005 — Protección Infantil Comunitaria
**Código:** IDC_2026_05  
**Fecha:** 13 de junio de 2026  
**Versión:** 1.0  
**Autor:** ZEUS EOS  
**Aprobador:** Jelkin Zair Carrillo Franco (CEO)

---

## 1. RESUMEN EJECUTIVO

Plataforma web y móvil para reporte comunitario de protección infantil. Permite a ciudadanos y padres reportar de forma anónima o autenticada información sobre personas que contactan niños con fines de abuso. El sistema garantiza anonimato absoluto, encriptación de datos sensibles y genera alertas estructuradas para autoridades competentes.

---

## 2. IDENTIFICACIÓN DEL PROYECTO

| Campo | Valor |
|-------|-------|
| **Nombre completo** | Protección Infantil Comunitaria |
| **Código interno** | IDC_2026_05 |
| **Cliente** | Innovadataco (Producto Propietario) |
| **Sector** | Protección Social / Tecnología Cívica |
| **Tipo de proyecto** | Desarrollo de producto propio |
| **Metodología de desarrollo** | SDD (Spec-Driven Development) |
| **Metodología de gestión** | PM2 (Project Management Methodology) |
| **Agente de desarrollo** | ODIN (Kimi Code CLI) |
| **Agente de gestión** | ZEUS EOS |
| **Product Owner** | Jelkin Zair Carrillo Franco |
| **Fecha de inicio** | 12 de junio de 2026 (Módulo 001) |
| **Duración estimada** | 12-16 semanas (4 módulos) |
| **Estado actual** | En ejecución — Módulo 001 completado |

---

## 3. STACK TECNOLÓGICO

| Capa | Tecnología | Versión | Justificación |
|------|-----------|---------|---------------|
| Frontend | React | 19.0.0 | Componentes reactivos, ecosistema maduro |
| Build tool | Vite | 6.0.0 | Rápido, HMR, soporte PWA |
| CSS | Tailwind CSS | 3.4.17 | Utility-first, prototipado rápido |
| Backend | FastAPI | 0.136.3 | Alto rendimiento, validación Pydantic, OpenAPI auto |
| ORM | SQLAlchemy | 2.0.50 | Mapeo objeto-relacional robusto |
| Base de datos | SQLite (dev) / PostgreSQL (prod) | - | SQLite sin infra en dev; PostgreSQL escalable en prod |
| Cache/Rate limit | Redis (prod) / Memoria (dev) | 4.0.0+ | Redis distribuido; memoria para desarrollo local |
| Encriptación | cryptography (AES-256-GCM) | 48.0.1 | Estándar industrial, disponible en Python |
| Tests backend | pytest + pytest-cov | 9.0.3 / 7.1.0 | Tests unitarios e integración con cobertura |
| Tests frontend | vitest + Testing Library | 3.0.0 | Tests de componentes React |
| Deploy | Docker + Uvicorn | - | Contenedores para prod/staging |

---

## 4. ARQUITECTURA DE ALTO NIVEL

```
┌─────────────────────────────────────────────────────────────────┐
│                         Usuario (navegador/móvil)              │
│              Sin login, sin cookies, sin IP guardada             │
└───────────────────────────┬─────────────────────────────────────┘
                            │ HTTPS
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│  Frontend — React + Vite (PWA-capable)                           │
│  • ReportForm.jsx (Módulo 001)                                   │
│  • AdminPanel.jsx (Módulo 002)                                   │
│  • NotificationCenter.jsx (Módulo 003)                           │
│  • IA Dashboard.jsx (Módulo 004)                                 │
└───────────────────────────┬─────────────────────────────────────┘
                            │ CORS restringido
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│  Backend — FastAPI                                               │
│  • Middleware de headers de seguridad OWASP                      │
│  • /api/reportes → validación, rate limit, encriptación, BD      │
│  • /api/admin → autenticación, panel de revisión (Módulo 002)   │
│  • /api/notifications → alertas a autoridades (Módulo 003)   │
│  • /api/ia → scoring y análisis (Módulo 004)                   │
│  • /api/health → health check                                    │
└───────────────────────────┬─────────────────────────────────────┘
                            │ SQLAlchemy ORM
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│  Base de datos — SQLite (dev) / PostgreSQL (prod)                │
│  Tabla: reports (encriptada)                                     │
│  Tabla: admin_users (Módulo 002)                                 │
│  Tabla: notifications (Módulo 003)                              │
│  Tabla: ia_scores (Módulo 004)                                  │
└─────────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────────┐
│  Redis (opcional en prod) — Rate limiting + Cache + Pub/Sub    │
└─────────────────────────────────────────────────────────────────┘
```

---

## 5. MÓDULOS Y ROADMAP

| Módulo | Nombre | Descripción | Estado | Fecha estimada |
|--------|--------|-------------|--------|----------------|
| **001** | Registro Anónimo | Formulario web, API, encriptación, rate limit | ✅ Completado | 12 jun 2026 |
| **002** | Panel de Administración | Auth, revisión de reportes, dashboard | ⬜ Pendiente | Jul 2026 |
| **003** | Notificaciones a Autoridades | Integración ICBF, Fiscalía, alertas automáticas | ⬜ Pendiente | Ago 2026 |
| **004** | IA / Scoring | Detección de patrones, priorización, análisis | ⬜ Pendiente | Sep 2026 |

---

## 6. REQUISITOS NO FUNCIONALES CRÍTICOS

| ID | Requisito | Criterio | Prioridad |
|----|-----------|----------|-----------|
| RNF-001 | Encriptación AES-256-GCM en reposo | Datos sensibles encriptados | Alta |
| RNF-002 | Headers de seguridad OWASP | HSTS, CSP, X-Frame, etc. | Alta |
| RNF-003 | Cobertura de tests ≥ 80% | pytest + vitest | Alta |
| RNF-004 | Tiempo de respuesta < 500ms | 95 percentile | Media |
| RNF-005 | Sin cookies de tracking | No cookies ni localStorage | Alta |
| RNF-006 | Anonimato absoluto | No IP, no user-agent, no metadata | Alta |
| RNF-007 | Disponibilidad 99.9% | Uptime en producción | Media |
| RNF-008 | Escalabilidad horizontal | Docker + load balancer | Media |

---

## 7. ENTORNOS

| Entorno | Infraestructura | BD | Rate Limit | Uso |
|---------|----------------|-----|------------|-----|
| Dev | Local | SQLite | Memoria | Desarrollo ODIN |
| Staging | Docker / VPS | PostgreSQL | Redis | Validación ZEUS |
| Prod | Docker / VPS / Cloud | PostgreSQL + backups | Redis | Operación real |

---

## 8. REPOSITORIOS Y DOCUMENTACIÓN

| Recurso | URL / Ubicación |
|---------|-----------------|
| Código fuente | `github.com/Innovadataco/Desarrollos/PROYECTO-005-PROTECCION-INFANTIL` |
| Especificación Módulo 001 | `specs/001-registro-anonimo/spec.md` |
| Plan técnico Módulo 001 | `specs/001-registro-anonimo/plan.md` |
| ADR seguridad | `specs/001-registro-anonimo/ADR-001-seguridad.md` |
| Gestión de proyecto | `github.com/Innovadataco/IDC_PROYECTOS/PROYECTO-005-2026-PROTECCION-INFANTIL` |

---

> *Documento generado por ZEUS — Innovadataco*
