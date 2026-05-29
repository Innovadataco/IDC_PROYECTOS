# PROYECTO 004 DE 2026 — SETP-SINCELEJO
## Componente Tecnológico — Sistema ITS

---

## 📋 IDENTIFICACIÓN DEL PROYECTO

| Campo | Valor |
|-------|-------|
| **Código** | PROYECTO-004-2026-SETP-SINCELEJO |
| **Nombre** | Sistema Estratégico de Transporte Público (SETP) de Sincelejo — Componente Tecnológico |
| **Cliente** | METRO SABANAS S.A.S. |
| **Ente Gestor** | METRO SABANAS S.A.S. |
| **Municipio** | Sincelejo, Sucre, Colombia |
| **Marco Legal** | Decreto 393 de 2010 (adopción SETP), modificado por Decreto 482 de 2023 |
| **Normativa Superior** | Decreto Nacional 1079 de 2015 (Sector Transporte) |
| **Consultoría Base** | A4 ASOCIADOS S.A.S. (2022) — 7 Entregables |
| **Estudios Previos Tecnología** | 2023 — Presupuesto $3.793.756.953 COP |
| **Estado** | En estructuración |
| **Objetivo INNOVADATACO** | Revisar, estructurar y acompañar el componente tecnológico ITS |

---

## 🎯 OBJETIVO DEL PROYECTO

### Objetivo General
Estructurar, diseñar y acompañar la implementación del **componente tecnológico ITS** (Sistemas Inteligentes de Transporte) del SETP Sincelejo, integrando los sistemas de recaudo, control de flota, información al usuario y seguridad de transacciones, garantizando interoperabilidad, escalabilidad y cumplimiento normativo.

### Objetivos Específicos
1. Revisar exhaustivamente la documentación técnica existente (consultoría 2022 + estudios previos 2023 + RFI 2025)
2. Identificar gaps y oportunidades de mejora en la arquitectura tecnológica propuesta
3. Diseñar arquitectura ITS de referencia para Sincelejo (5 capas)
4. Estructurar especificaciones técnicas para contratación (SRC, SGCF, SIU, SST)
5. Definir modelo de contratación, hitos de pago y riesgos técnicos
6. Acompañar proceso de licitación y selección de proveedor tecnológico
7. Transferir conocimiento a METRO SABANAS para autonomía post-implementación

---

## 📊 ALCANCE TECNOLÓGICO

### Sistemas a Implementar
| Sistema | Sigla | Prioridad |
|:--------|:------|:----------|
| Sistema de Recaudo Centralizado | SRC | ALTA |
| Sistema de Gestión y Control de Flota | SGCF | ALTA |
| Sistema de Información al Usuario | SIU | MEDIA |
| Sistema de Seguridad de Transacciones | SST | ALTA |

### Infraestructura Tecnológica
| Componente | Descripción |
|:-------------|:------------|
| Equipos a bordo | Validadores, torniquetes, cámaras, conteo pasajeros, consola conductor, botón pánico, router WiFi |
| Centro de Control | 4 TVs, 2 PCs doble pantalla, mobiliario, UPS, switch, antenas inicialización |
| Comunicaciones | 4G/5G, WiFi, VPN, firewall |
| Cloud/SaaS | Hosting aplicaciones, base de datos, APIs |
| Seguridad | SAM/HSM, TLS/SSL, OAuth2, cifrado end-to-end |

---

## 📁 ESTRUCTURA DEL REPOSITORIO (PM2)

| Carpeta | Fase PM2 | Contenido |
|:--------|:---------|:----------|
| `00-META/` | Meta | Acta de constitución, registro cambios, glosario |
| `01-INICIO/` | Inicio | Charter, caso de negocio, stakeholders, lecciones aprendidas |
| `02-PLANIFICACION/` | Planificación | Plan de gestión, EDT/WBS, cronograma, presupuesto, riesgos, calidad |
| `03-EJECUCION/` | Ejecución | Informes avance, actas reuniones, cambios, issues log |
| `04-CIERRE/` | Cierre | Acta de cierre, lecciones aprendidas, transferencia, documentación final |
| `05-ENTREGABLES/` | Entregables | Documentos técnicos, presentaciones, propuestas, contratos |

---

## 📈 ESTADO ACTUAL

| Fase | Estado | % |
|:----|:-------|:-:|
| 01-INICIO | ✅ Completado | 100% |
| 02-PLANIFICACION | 🟡 En progreso | 60% |
| 03-EJECUCION | 🔴 Pendiente | 0% |
| 04-CIERRE | 🔴 Pendiente | 0% |

## 📦 ENTREGABLES GENERADOS

| Entregable | Estado | Ubicación |
|:---|:---|:---|
| **E1 — Arquitectura ITS Completa** | ✅ Generado | `05-ENTREGABLES/E1-Arquitectura-ITS/` |
| **E2 — Hallazgos e Inconsistencias** | ✅ Generado | `05-ENTREGABLES/E2-Hallazgos-Inconsistencias/` |
| **E3 — Propuesta Comercial INNOVADATACO** | ✅ Generado | `05-ENTREGABLES/E3-Propuesta-Comercial/` |
| **E4 — Documento Referencia APP Chía-Girardot** | 🟡 En proceso | `05-ENTREGABLES/E4-Documento-Referencia-APP/` |

---

## 🏛️ GOBERNANZA

| Rol | Responsable | Entidad |
|:----|:------------|:--------|
| **Director Proyecto** | Jelkin Zair Carrillo Franco | INNOVADATACO |
| **Gerente Proyecto** | Diana Carolina Baquero Tobías | Metro Sabanas |
| **Representante Legal** | Oscar Iván Viana Gómez | Metro Sabanas |
| **Asesor Tecnología** | ZEUS / INNOVADATACO | INNOVADATACO |
| **Interventoría** | Por definir | Metro Sabanas |

---

## 📅 FECHAS CLAVE

| Evento | Fecha | Estado |
|:-------|:------|:-------|
| Consultoría A4 ASOCIADOS | 2022 | ✅ Completado |
| Estudios Previos Tecnología | 2023 | ✅ Completado |
| RFI Emisión | Sept 2025 | ✅ Completado |
| Inicio estructuración INNOVADATACO | Mayo 2026 | 🟡 En curso |
| Entrega propuesta técnica | Por definir | 🔴 Pendiente |
| Licitación tecnología | Por definir | 🔴 Pendiente |

---

## 📚 DOCUMENTACIÓN BASE ANALIZADA

### Entregables Consultoría 2022 (A4 ASOCIADOS)
1. E1 — Plan de Trabajo
2. E3 — Matriz Origen-Destino (200 ZATs, 3.512 encuestas)
3. E4 — Avances Modelo Transporte (14 rutas definitivas)
4. E5 — Especificaciones Autobuses
5. E6 — Informe Definitivo Modelo Transporte
6. E7 — Estructuración Financiera

### Estudios Previos 2023
- Estudios Previos Tecnología — $3.793.756.953 COP
- Presupuesto ITS, plazo 9 meses, 5 hitos de pago

### RFI 2025
- RFI Integración Contrataciones SETP (Sept 2025)
- Anexo Técnico 1 — Especificaciones Buses (75 microbuses)
- Anexo Técnico 2 — Resumen ITS (cloud-first, APIs, SaaS)
- Anexo Técnico 3 — Operación SETP (20 años, mototaxismo, patios)

---

## ⚡ NOTAS

**Documento generado por ZEUS — Agente IA Estratégico INNOVADATACO**
**Fecha:** 2026-05-29
**Versión:** 1.0

---

> **"ZEUS online. La empresa está operando."** ⚡
