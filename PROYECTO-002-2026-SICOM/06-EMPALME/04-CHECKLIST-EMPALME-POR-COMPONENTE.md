# 📋 CHECKLIST DE EMPALME SICOM — POR COMPONENTE

**Periodo:** Día 1 (Mié 11 jun) → Día 29 (Vie 18 jul)  
**Feriados:** Día 6 (Lun 16 jun), Día 14 (Lun 30 jun) — NO LABORABLES  
**Inicio operación CI2:** 1 de julio 2026

---

## 🔧 1. INFRAESTRUCTURA (S3 — Especialista Infraestructura)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 1 | Mié 11 jun | Acceso a vSphere / VMware | S3 + INTERNEXA | Credenciales validadas | ⏳ |
| 2 | Jue 12 jun | Inventario de VMs (27 servidores) | S3 | Lista de VMs, IPs, recursos | ⏳ |
| 3 | Vie 13 jun | Inventario de storage y red (VLAN, SAN) | S3 | Diagrama de red preliminar | ⏳ |
| 5 | Mar 17 jun | Validación de backups (Veeam) | S3 | Estado de jobs de backup | ⏳ |
| 6 | Mié 18 jun | Documentación de arquitectura física | S3 | Diagrama de racks, cables, equipos | ⏳ |
| 9 | Lun 23 jun | Shadowing con admin infra INTERNEXA | S3 + INTERNEXA | Notas de procedimientos | ⏳ |
| 10 | Mar 24 jun | Shadowing día 2 — monitoreo y alertas | S3 + INTERNEXA | Notas de monitoreo | ⏳ |
| 12 | Jue 26 jun | Prueba de restore VM en ambiente de pruebas | S3 | VM restaurada = OK o FAIL | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — reiniciar servicio sin ayuda | S3 | Log de prueba | ⏳ |
| 20 | Lun 7 jul | Simulacro DRP — recuperar infraestructura | S3 | Resultado documentado | ⏳ |
| 22 | Mié 9 jul | Pruebas de estrés — carga CPU/memoria | S3 | Reporte de rendimiento | ⏳ |
| 25 | Lun 14 jul | Validación final de acceso operativo | S3 | Checklist firmado | ⏳ |

---

## 🗄️ 2. BASE DE DATOS (S2 — Especialista BD)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 1 | Mié 11 jun | Acceso a Oracle (SQL Developer, Toad) | S2 + INTERNEXA | Conexión validada | ⏳ |
| 2 | Jue 12 jun | Inventario de esquemas y tablas | S2 | Lista de schemas, volúmenes | ⏳ |
| 3 | Vie 13 jun | Inventario de jobs, triggers, procedimientos | S2 | Lista de jobs programados | ⏳ |
| 5 | Mar 17 jun | Validación de backups Oracle (RMAN) | S2 | Estado de backups, último restore | ⏳ |
| 6 | Mié 18 jun | Diccionario de datos — tablas críticas | S2 | Diccionario preliminar | ⏳ |
| 9 | Lun 23 jun | Shadowing con DBA INTERNEXA día 1 | S2 + INTERNEXA | Notas de administración | ⏳ |
| 10 | Mar 24 jun | Shadowing día 2 — tuning y troubleshooting | S2 + INTERNEXA | Notas de optimización | ⏳ |
| 12 | Jue 26 jun | Prueba de restore de BD en ambiente de pruebas | S2 | BD restaurada = OK o FAIL | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — backup sin ayuda | S2 | Log de backup + verificación | ⏳ |
| 20 | Lun 7 jul | Simulacro DRP — restore BD desde cero | S2 | Resultado documentado | ⏳ |
| 22 | Mié 9 jul | Validación de integraciones con otras BD | S2 | Pruebas de conectividad | ⏳ |
| 25 | Lun 14 jul | Validación final de acceso operativo | S2 | Checklist firmado | ⏳ |

---

## 🛡️ 3. SEGURIDAD (S5 — Especialista Seguridad)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 1 | Mié 11 jun | Acceso a Fortinet / WAF / SIEM | S5 + INTERNEXA | Credenciales validadas | ⏳ |
| 2 | Jue 12 jun | Inventario de reglas de firewall | S5 | Lista de reglas, puertos, IPs | ⏳ |
| 3 | Vie 13 jun | Inventario de certificados SSL | S5 | Lista de certificados, fechas vencimiento | ⏳ |
| 5 | Mar 17 jun | Matriz de vulnerabilidades actual | S5 | Matriz de riesgos v0.1 | ⏳ |
| 6 | Mié 18 jun | RBAC — usuarios, roles, privilegios | S5 | Lista de cuentas y permisos | ⏳ |
| 9 | Lun 23 jun | Shadowing con especialista seguridad INTERNEXA | S5 + INTERNEXA | Notas de políticas | ⏳ |
| 10 | Mar 24 jun | Shadowing día 2 — incidentes y respuesta | S5 + INTERNEXA | Notas de procedimientos | ⏳ |
| 12 | Jue 26 jun | Validación de MFA y cuentas de servicio | S5 | Estado de MFA, cuentas activas | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — revisión de vulnerabilidades | S5 | Log de auditoría | ⏳ |
| 20 | Lun 7 jul | Simulacro DRP — seguridad durante recuperación | S5 | Resultado documentado | ⏳ |
| 23 | Jue 10 jul | Auditoría de vulnerabilidades completa | S5 | Reporte de auditoría + plan remediación | ⏳ |
| 25 | Lun 14 jul | Validación final de acceso operativo | S5 | Checklist firmado | ⏳ |

---

## 💻 4. SOFTWARE / APLICACIONES (S1 — Especialista Software)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 1 | Mié 11 jun | Acceso a repositorios Git / SVN | S1 + INTERNEXA | Credenciales validadas | ⏳ |
| 2 | Jue 12 jun | Inventario de aplicaciones Java / Web | S1 | Lista de apps, versiones, servidores | ⏳ |
| 3 | Vie 13 jun | Inventario de librerías y dependencias | S1 | Lista de jars, frameworks, versiones | ⏳ |
| 5 | Mar 17 jun | Validación de pipelines / CI-CD | S1 | Estado de builds, deployments | ⏳ |
| 6 | Mié 18 jun | Documentación de arquitectura de software | S1 | Diagrama de componentes | ⏳ |
| 9 | Lun 23 jun | Shadowing con desarrollador INTERNEXA | S1 + INTERNEXA | Notas de código, procedimientos | ⏳ |
| 10 | Mar 24 jun | Shadowing día 2 — deploy y rollback | S1 + INTERNEXA | Notas de despliegue | ⏳ |
| 12 | Jue 26 jun | Prueba de build reproducible | S1 | Build exitoso = OK o FAIL | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — deploy básico sin ayuda | S1 | Log de deploy | ⏳ |
| 20 | Lun 7 jul | Simulacro DRP — levantar app desde cero | S1 | Resultado documentado | ⏳ |
| 22 | Mié 9 jul | Validación de integraciones con sistemas externos | S1 | Pruebas de APIs | ⏳ |
| 25 | Lun 14 jul | Validación final de acceso operativo | S1 | Checklist firmado | ⏳ |

---

## 🔄 5. BPM / BIZAGI (S1 + S6 — Software + Arquitectura)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 2 | Jue 12 jun | Acceso a Bizagi Studio / Server | S1 + INTERNEXA | Credenciales validadas | ⏳ |
| 3 | Vie 13 jun | Inventario de procesos BPM (flujos, reglas) | S1 | Lista de procesos, versiones | ⏳ |
| 5 | Mar 17 jun | Inventario de formularios y conectores | S1 | Lista de forms, conectores, APIs | ⏳ |
| 6 | Mié 18 jun | Documentación de publicación de procesos | S1 | Manual de publicación preliminar | ⏳ |
| 9 | Lun 23 jun | Shadowing con experto Bizagi INTERNEXA | S1 + INTERNEXA | Notas de procedimientos | ⏳ |
| 10 | Mar 24 jun | Shadowing día 2 — troubleshooting BPM | S1 + INTERNEXA | Notas de errores comunes | ⏳ |
| 12 | Jue 26 jun | Prueba de publicación de proceso en ambiente de pruebas | S1 | Proceso publicado = OK o FAIL | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — publicar sin ayuda | S1 | Log de publicación | ⏳ |
| 20 | Lun 7 jul | Simulacro DRP — recuperar BPM | S1 | Resultado documentado | ⏳ |
| 25 | Lun 14 jul | Validación final de acceso operativo | S1 | Checklist firmado | ⏳ |

---

## 🔗 6. INTEGRACIONES (S4 — Especialista Redes + S6 Arquitectura)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 1 | Mié 11 jun | Acceso a diagramas de integraciones | S4 + S6 + INTERNEXA | Diagrama preliminar | ⏳ |
| 2 | Jue 12 jun | Inventario de APIs SOAP/REST | S4 + S6 | Lista de endpoints, métodos, contratos | ⏳ |
| 3 | Vie 13 jun | Inventario de colas, SFTP, jobs de integración | S4 + S6 | Lista de conexiones, programación | ⏳ |
| 5 | Mar 17 jun | Contactos técnicos de contrapartes (SIGDI, ANH, etc.) | S4 + S6 | Lista de contactos | ⏳ |
| 6 | Mié 18 jun | Documentación de credenciales y certificados por integración | S4 + S6 | Ficha técnica por integración | ⏳ |
| 9 | Lun 23 jun | Shadowing con ingeniero de integraciones INTERNEXA | S4 + S6 + INTERNEXA | Notas de procedimientos | ⏳ |
| 10 | Mar 24 jun | Shadowing día 2 — troubleshooting de integraciones | S4 + S6 + INTERNEXA | Notas de errores comunes | ⏳ |
| 12 | Jue 26 jun | Prueba de conectividad con cada sistema externo | S4 + S6 | Resultado por integración | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — validar integración sin ayuda | S4 + S6 | Log de prueba | ⏳ |
| 20 | Lun 7 jul | Simulacro DRP — recuperar integraciones | S4 + S6 | Resultado documentado | ⏳ |
| 22 | Mié 9 jul | Pruebas de integración end-to-end | S4 + S6 | Todas las integraciones OK | ⏳ |
| 25 | Lun 14 jul | Validación final de acceso operativo | S4 + S6 | Checklist firmado | ⏳ |

---

## 📊 7. BI / REPORTES (S2 + S6 — BD + Arquitectura)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 2 | Jue 12 jun | Acceso a Oracle BI / OBIEE | S2 + S6 + INTERNEXA | Credenciales validadas | ⏳ |
| 3 | Vie 13 jun | Inventario de dashboards y reportes | S2 + S6 | Lista de reportes, usuarios, frecuencia | ⏳ |
| 5 | Mar 17 jun | Inventario de ETL / procesos de carga | S2 + S6 | Lista de jobs ETL, fuentes, destinos | ⏳ |
| 6 | Mié 18 jun | Documentación de modelos OLAP / cubos | S2 + S6 | Diagrama de modelo de datos BI | ⏳ |
| 9 | Lun 23 jun | Shadowing con experto BI INTERNEXA | S2 + S6 + INTERNEXA | Notas de procedimientos | ⏳ |
| 10 | Mar 24 jun | Shadowing día 2 — troubleshooting BI | S2 + S6 + INTERNEXA | Notas de errores comunes | ⏳ |
| 12 | Jue 26 jun | Prueba de ejecución de reporte en ambiente de pruebas | S2 + S6 | Reporte ejecutado = OK o FAIL | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — ejecutar reporte sin ayuda | S2 + S6 | Log de ejecución | ⏳ |
| 20 | Lun 7 jul | Simulacro DRP — recuperar BI | S2 + S6 | Resultado documentado | ⏳ |
| 25 | Lun 14 jul | Validación final de acceso operativo | S2 + S6 | Checklist firmado | ⏳ |

---

## 📞 8. OPERACIÓN / CONTINUIDAD (S1-S6 + Jelkin)

| Día | Fecha | Actividad | Responsable | Entregable | Estado |
|-----|-------|-----------|-------------|------------|--------|
| 1 | Mié 11 jun | Acceso a mesa de servicio (Aranda) y call center (WolKVOX) | Jelkin + S1-S6 | Credenciales validadas | ⏳ |
| 2 | Jue 12 jun | Inventario de runbooks actuales | Jelkin | Lista de runbooks existentes | ⏳ |
| 3 | Vie 13 jun | Inventario de árbol de escalamiento | Jelkin | Lista de contactos, turnos | ⏳ |
| 5 | Mar 17 jun | Casos críticos históricos (top 10 incidentes) | Jelkin + S1-S6 | Documento de lecciones aprendidas | ⏳ |
| 6 | Mié 18 jun | Documentación de procedimientos de contingencia | Jelkin + S5 | Procedimiento DRP preliminar | ⏳ |
| 9 | Lun 23 jun | Shadowing con operador de mesa de servicio | S1-S6 + INTERNEXA | Notas de operación | ⏳ |
| 10 | Mar 24 jun | Shadowing con operador de call center | S1-S6 + INTERNEXA | Notas de operación | ⏳ |
| 12 | Jue 26 jun | Prueba de atención de ticket simulado | S1-S6 | Ticket atendido = OK o FAIL | ⏳ |
| 15 | Mar 1 jul | Prueba de fuego — atender ticket sin ayuda | S1-S6 | Log de atención | ⏳ |
| 20 | Lun 7 jul | **SIMULACRO DRP COMPLETO** | Todos | Resultado global = OK o FAIL | ⏳ |
| 21 | Mar 8 jul | Corrección de gaps post-simulacro | Todos | Runbooks v2, docs actualizados | ⏳ |
| 22 | Mié 9 jul | Pruebas de integración end-to-end | Todos | Sistema operativo al 100% | ⏳ |
| 23 | Jue 10 jul | Validación de seguridad final | S5 | Reporte de auditoría | ⏳ |
| 25 | Lun 14 jul | **VALIDACIÓN FINAL DE ACCESOS OPERATIVOS** | Todos | 8 checklists firmados | ⏳ |
| 26 | Mar 15 jul | Reunión con CI2 — presentación estado | Jelkin | Presentación ejecutiva | ⏳ |
| 27 | Mié 16 jul | Reunión con MME — informe final | Jelkin + Elizabeth | Informe final aprobado | ⏳ |
| 28 | Jue 17 jul | Cierre de gaps menores | Todos | Lista de cierre completada | ⏳ |
| 29 | Vie 18 jul | **ACTA DE CIERRE OFICIAL DEL EMPALME** | Todos | Acta firmada | ⏳ |

---

## 📅 RESUMEN DE FECHAS CLAVE

| Día | Fecha | Evento | Tipo |
|-----|-------|--------|------|
| 1 | Mié 11 jun | Inicio empalme, kickoff CI2 | Inicio |
| 6 | Lun 16 jun | 🏖️ FERIADO — Sagrado Corazón | Feriado |
| 14 | Lun 30 jun | 🏖️ FERIADO — San Pedro y San Pablo | Feriado |
| 15 | Mar 1 jul | **INICIO OPERACIÓN CI2** | Hito |
| 20 | Lun 7 jul | **SIMULACRO DRP COMPLETO** | Hito crítico |
| 25 | Lun 14 jul | Validación final de accesos | Hito |
| 29 | Vie 18 jul | **CIERRE OFICIAL DEL EMPALME** | Cierre |

---

> **ZEUS — Innovadataco** | Versión 1.0 | 2026-06-07
