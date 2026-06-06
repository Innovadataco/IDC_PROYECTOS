PLAN DE EMPALME Y RECIBO OPERATIVO DEL SICOM
Página 1

PLAN DETALLADO DE EMPALME, TRANSFERENCIA DE CONOCIMIENTO Y PREPARACIÓN OPERATIVA DEL SICOM
Propuesta para el contratista entrante CI2 / IND TECH
Periodo de preparación: 19 de mayo de 2026 a 30 de junio de 2026 (6 semanas)
Inicio esperado de operación: 1 de julio de 2026

Base documental:
- Anexo técnico de características SICOM
- Contrato interadministrativo GGC-2034-2025
- 48 documentos técnicos analizados (Manuales SIGDI, Informes de Seguridad, Infraestructura, DRP, Call Center, BI/Calidad, Desarrollo, Gobernanza)

Objetivo:
Recibir el sistema sin interrupción del servicio, con dominio técnico mínimo viable y con evidencia formal de todo lo entregado por el operador saliente INTERNEXA S.A.

Enfoque:
Empalme intensivo de 6 semanas, con operación en sombra, validación técnica, cierre de brechas, actas y criterios de aceptación por dominios. Gobierno del proceso a través de Comité Directivo, Mesa Técnica Diaria, War Room de Corte, Mesa de Seguridad y Mesa Funcional.

Equipo de Empalme:
- Gerente de Empalme / PM Ejecutivo: Jelkin Zair Carrillo Franco (Innovadataco)
- Gerente de Proyecto CI2: Luis Felipe Herrera (CI2 / IND TECH)
- Supervisora Contrato MME: Elizabeth (Ministerio de Minas y Energía)
- Coordinador Técnico CI2: [Designar]
- 6 Especialistas CI2: Software, Base de Datos, Infraestructura, Redes, Seguridad, Arquitectura de Software

---

1. RESUMEN EJECUTIVO

El anexo técnico sí define una base mínima para el empalme — acceso a información, máquinas virtuales, código fuente, backups, documentación, capacitación y pruebas — pero no alcanza por sí solo para reducir adecuadamente el riesgo de recibir un sistema crítico y de misión nacional como el SICOM.

Por eso, este plan amplía el alcance operativo del empalme con un paquete de entregables de detalle, criterios de aceptación, gobierno del proceso, operación en sombra, validación cruzada y un corte controlado para llegar al 1 de julio de 2026 con capacidad real de operar.

La lógica central del plan es simple: no basta con recibir archivos, repositorios y manuales; se debe recibir conocimiento ejecutable, trazabilidad de la arquitectura, control de accesos, dependencia de terceros, evidencia de pruebas, operación de contingencia, trazabilidad de cambios y una línea base de servicio que permita a CI2 asumir el control sin quedar expuesta a riesgos ocultos.

ESTADO ACTUAL DEL EMPALME (Junio 2026):
- Fase 0 (Preparación y Gobierno): ✅ Instalada — 19-25 mayo 2026
- Fase 1 (Inventario y Documentación): 🔄 En ejecución — 26 mayo-14 junio 2026
- Fase 2 (Acceso y Validación): 🔄 En ejecución — 2-12 junio 2026
- Fase 3 (Transferencia de Conocimiento): ⏳ Pendiente — 10-24 junio 2026
- Fase 4 (Replicación y Pruebas): ⏳ Pendiente — 17-30 junio 2026
- Fase 5 (Corte y Migración): ⏳ Pendiente — 26-30 junio 2026

---

2. LO QUE YA EXIGEN EL ANEXO Y EL CONTRATO

El empalme inicial y el empalme final exigen, como mínimo:
- Migración de datos
- Recibo/entrega de máquinas virtuales
- Código fuente Java
- Flujos BPM/Bizagi
- Backups
- Documentación, manuales, características de sistemas operativos y bases de datos
- Transferencia de conocimiento y capacitación

El empalme inicial además exige:
- Pruebas de acceso, estrés, rendimiento
- Infraestructura principal y alterna
- Pruebas funcionales, de seguridad, de servicios web
- Pruebas de integración, integridad y disponibilidad de la información

El anexo exige:
- Repositorio Git y control de versiones
- Actualización y soporte de Bizagi y Oracle
- Infraestructura en nube privada con sitio principal y alterno
- Documentación del proyecto para desarrollos y ajustes implementados

El contrato refuerza la obligación de:
- Garantizar continuidad ininterrumpida
- Fortalecer ciberseguridad
- Facilitar auditorías
- Mantener actas y trazabilidad documental
- Entregar programas fuente, objetos, librerías, esquemas de bases de datos, configuraciones
- Informes mensuales de cambios y commits

Referencias base para sustentar el plan:
- Anexo Técnico, numerales 3.1, 3.2, 4.1, 7.2 y 7.3
- Contrato, cláusula tercera (obligaciones específicas 4, 6, 13, 16, 17, 19, 20, 21 y 24)

---

3. BRECHAS CRÍTICAS QUE CONVIENE EXIGIR EXPRESAMENTE AL OPERADOR SALIENTE

A continuación, se listan los elementos de alta relevancia que no están suficientemente aterrizados en el texto base y que deberían quedar exigidos en el plan formal de empalme, en las actas y en la matriz de recibo:

3.1 Inventario Técnico y Contractual
Exigencia: Inventario completo de servidores, VMs, contenedores, balanceadores, bases de datos, licencias (estado), certificados digitales, dominios, integraciones, cuentas de servicio, herramientas de monitoreo, contratos de soporte, numeración de enlaces, ambientes y responsables, usuarios de los sistemas y de todas las herramientas (GIT, BIZAGI, etc. o de cualquier sistema que haga parte del SICOM sin excepción incluyendo toda la información de los sistemas legados y sus diferentes escenarios de comunicación o arquitectura).

Estado: 🔄 En proceso — Validación con 48 documentos técnicos analizados. Identificados 27 IPs internas, 27 URLs externas, 8 subsistemas, 7 integraciones externas.

3.2 Arquitectura Lógica y Física Aterrizada
Exigencia: No sólo diagramas generales: se requiere mapa por ambiente, por flujo, por dependencia, por integración y por componente, incluyendo puertos, DNS, reglas, VLAN, almacenamiento, replicación, jobs y servicios programados, arquitectura de red (topologías).

Estado: 🔄 En proceso — Super Documento SICOM v1.2 contiene análisis de arquitectura, procesos, módulos, actores, infraestructura, seguridad y operación. Pendiente validación con contraparte INTERNEXA.

3.3 Arquitectura de Datos
Exigencia: Modelo entidad-relación vigente, diccionario de datos, catálogos, reglas de calidad, procesos ETL, tableros BI, linaje de datos, tablas críticas, volúmenes, políticas de retención, particionamiento y auditoría.

Estado: ⏳ Pendiente — Especialista de BD CI2 debe iniciar shadowing con DBA INTERNEXA.

3.4 Mapa de Integraciones y Dependencias Externas
Exigencia: APIs, servicios SOAP/REST, colas, archivos, SFTP, jobs, cronogramas, credenciales, certificados, whitelist, contactos técnicos, ventanas de mantenimiento, contratos y mecanismos de contingencia por cada tercero.

Sistemas externos identificados: SIGDI, ANH, WolKVOX, Aranda, Entidades Reguladas (EDS, DI, CI, Comercializadores).

Estado: 🔄 En proceso — Análisis contractual INTERNEZA-SICOM documenta obligaciones. Pendiente validación técnica.

3.5 Seguridad Operativa Real
Exigencia: Matriz RBAC, autenticación, MFA, cuentas privilegiadas, cuentas de servicio, rotación de claves, bóveda de secretos, certificados, WAF/firewall, EDR/antimalware, hardening, logs, SIEM/SOC, vulnerabilidades abiertas y planes de remediación.

Estado: 🔄 En proceso — Matriz de vulnerabilidades analizada (IDE-0020 Ethical Hacking). Hallazgos: versiones de software sin soporte (PHP EOL, Apache Tomcat desactualizado), nginx desactualizado, certificados SSL, encabezados HTTP.

3.6 DevOps y Trazabilidad de Despliegue
Exigencia: Estructura de repositorios, ramas, pipelines, scripts de construcción, variables, artefactos desplegados, procedimiento de rollback, evidencias de último despliegue estable y trazabilidad entre commit, build y producción.

Estado: ⏳ Pendiente — Especialista de Software CI2 debe validar durante shadowing.

3.7 Operación y Soporte 24/7
Exigencia: Runbooks, árbol de escalamiento, turnos, matrículas de personal, tablero de incidentes, top de fallas conocidas, errores recurrentes, lecciones aprendidas, casos críticos históricos y tiempos reales de resolución.

Estado: ⏳ Pendiente — Pendiente shadowing con operadores INTERNEXA.

3.8 Continuidad y Recuperación
Exigencia: RPO, RTO, pruebas de contingencia, bitácoras de restauración, sitio alterno, replicación, procedimiento de conmutación, retorno a normalidad, dependencia de terceros durante desastre y responsables por actividad.

Estado: 🔄 En proceso — Procedimiento Activación DR y Pruebas DRP Marzo 2025 analizados. Dataset de Casos Aranda Enero 2026 (~1,900 casos) documentado.

3.9 Calidad y Estado Real del Software
Exigencia: Deuda técnica, componentes obsoletos, librerías sin soporte, vulnerabilidades, incidencias conocidas, módulos incompletos, desarrollos en curso, branches abiertos y compromisos pendientes con el Ministerio.

Estado: 🔄 En proceso — Análisis de 48 documentos técnicos. Identificados módulos de contingencias de abastecimiento (HU-1531), solución workaround módulo encuestas, listado general de requerimientos SICOM Líquidos.

3.10 Conocimiento Funcional del Negocio
Exigencia: Se requiere transferencia del conocimiento funcional por proceso misional: líquidos, GNCV, autogestión, mesa de servicio, BI, APPs, atención al usuario, operación estadística DANE y contingencias de negocio.

Estado: ⏳ Pendiente — Mesa funcional semanal programada para Semana 3.

3.11 Legalidad, Propiedad y Cierre Documental
Exigencia: Acta de cesión, acta de destrucción de información en infraestructura del saliente, actas de acceso, cadena de custodia de backups, aprobación de repositorios y matriz de entregables firmada por dominio.

Estado: ⏳ Pendiente — Programado para Semana 4 (cierre de empalme).

---

4. PRINCIPIOS DEL EMPALME PROPUESTO

• Cero interrupción del servicio: ninguna actividad de empalme puede degradar la operación vigente.

• Recibo con evidencia: todo entregable debe tener soporte, demostración y aceptación formal.

• Validación por dominios: infraestructura, bases de datos, seguridad, aplicaciones, integraciones, BI, mesa de servicio, APPs, continuidad y operación funcional.

• Operación en sombra: el equipo entrante debe observar, replicar, ejecutar y validar con acompañamiento antes del corte y se requiere conocer muy bien la operación participando en los diferentes escenarios de actuación del SICOM con sus actores estratégicos, visitas en sitio.

• Accesos progresivos y custodiados: primero privilegios de lectura, luego privilegios de operación controlada, y sólo al final privilegios productivos completos.

• Riesgo visible: toda brecha debe registrarse en matriz RAID (riesgos, supuestos, incidencias y dependencias) con responsable y fecha.

---

5. GOBIERNO DEL PROCESO DE EMPALME

Instancia | Frecuencia | Objetivo | Resultado esperado
---|---|---|---
Comité Directivo | 2 veces por semana | Desbloqueo, decisiones y escalaciones con MME/supervisión. | Acta, riesgos y decisiones.
Mesa Técnica Diaria | Diaria | Seguimiento detallado de entregables, accesos, pruebas y novedades. | Tablero actualizado y compromisos.
War Room de Corte | Última semana | Preparar handover final y contingencias de salida/entrada. | Checklist Go/No-Go.
Mesa de Seguridad | Semanal | Revisión de accesos, secretos, vulnerabilidades y evidencias. | Matriz de remediación.
Mesa Funcional | Semanal | Validar procesos de negocio y escenarios críticos. | Acta de pruebas funcionales.

Estructura de Gobierno:
```
MINISTERIO DE MINAS Y ENERGÍA (MME) — Elizabeth
    ↓ Supervisa contractualmente
CI2 / IND TECH — Luis Felipe Herrera (Gerente de Proyecto)
    ↓ Reporta avances semanales
INNOVADATACO — Jelkin Zair Carrillo Franco (Director de Empalme / PM Ejecutivo)
    ↓ Coordina ejecución técnica
    ├── Coordinador Técnico CI2
    ├── Especialista de Software [S1]
    ├── Especialista de Base de Datos [S2]
    ├── Especialista de Infraestructura [S3]
    ├── Especialista de Redes [S4]
    ├── Especialista de Seguridad [S5]
    └── Arquitecto de Software [S6]
    ↓ Trabaja con
INTERNEXA S.A. — Operador Saliente
```

---

6. CRONOGRAMA DE EMPALME (6 SEMANAS)

Fase | Periodo | Duración | Hitos | Estado
---|---|---|---|---
F0: Preparación y Gobierno | 19 may — 25 may | 1 semana | Gobierno instalado | ✅ Completado
F1: Inventario y Documentación | 26 may — 14 jun | 3 semanas | Inventario técnico validado | 🔄 En ejecución
F2: Acceso y Validación | 2 jun — 12 jun | ~2 semanas | Accesos validados | 🔄 En ejecución
F3: Transferencia de Conocimiento | 10 jun — 24 jun | ~2 semanas | Shadowing iniciado | ⏳ Pendiente
F4: Replicación y Pruebas | 17 jun — 30 jun | ~2 semanas | Pruebas de aceptación | ⏳ Pendiente
F5: Corte y Migración | 26 jun — 30 jun | 5 días | Corte controlado | ⏳ Pendiente
F6: Operación y Estabilización | 1 jul — 15 jul | 2 semanas | Operación plena CI2 | ⏳ Programado
F7: Transferencia Final | Nov 2026 | 1 mes | Cierre contrato CI2 | ⏳ Programado

---

7. MATRIZ DE ENTREGABLES OBLIGATORIOS PARA EL RECIBO

Dominio | Entregable | Responsable inicial | Criterio de aceptación | Estado
---|---|---|---|---
Infraestructura | Inventario completo de DC principal y alterno, VMs, recursos, configuraciones y versionamiento. | Operador saliente | Inventario + evidencia + validación en ambiente. | 🔄 En proceso
Código y DevOps | Repositorios, ramas, pipelines, artefactos, scripts y procedimiento de rollback. | Operador saliente | Build reproducible y despliegue controlado exitoso. | ⏳ Pendiente
BPM/Bizagi | Flujos, reglas, formularios, conectores, ambientes y manual de publicación. | Operador saliente | Publicación controlada y prueba de punta a punta. | ⏳ Pendiente
Base de datos | Esquemas, ER, diccionario, jobs, respaldos, usuarios, parámetros y monitoreo. | Operador saliente | Restore exitoso + validación de integridad. | 🔄 En proceso
Seguridad | RBAC, cuentas de servicio, MFA, secretos, certificados, reglas y hardening. | Operador saliente | Accesos controlados y evidencias firmadas. | 🔄 En proceso
Integraciones | Ficha técnica por integración externa e interna. | Operador saliente | Pruebas OK por interfaz. | 🔄 En proceso
Operación | Runbooks, monitoreo, umbrales, escalamiento, incidentes conocidos. | Operador saliente | Simulación operativa atendida por el entrante. | ⏳ Pendiente
Continuidad | Backups, RPO/RTO, conmutación, DRP y pruebas históricas. | Operador saliente | Restore y prueba de contingencia validados. | 🔄 En proceso

---

8. RIESGOS PRINCIPALES Y ESTRATEGIA DE MITIGACIÓN

ID | Riesgo | Probabilidad | Impacto | Estrategia | Estado
---|---|---|---|---|---
R001 | INTERNEXA no coopera con la entrega | Alta | Crítico | Escalar a Elizabeth (MME) contractualmente | 🔄 Monitoreo
R002 | Documentación de INTERNEXA incompleta | Alta | Alto | Validar con pruebas técnicas; documentar nosotros mismos | 🔄 En proceso
R003 | Backups no restaurables | Media | Crítico | Validar restore en Semana 3, tener plan B | 🔄 En proceso
R004 | Credenciales no transferibles | Media | Alto | Resetear credenciales | ⏳ Programado
R005 | Dependencia de personas clave de INTERNEXA | Alta | Alto | Identificar y entrevistar ASAP; grabar sesiones | 🔄 En proceso
R006 | Infraestructura destino CI2 no está lista | Media | Alto | Plan B: cloud temporal | ⏳ Programado
R007 | Pruebas de estrés revelan fallas | Media | Alto | Corregir antes del corte | ⏳ Programado
R008 | Brechas de seguridad no detectadas | Media | Crítico | Auditoría de seguridad en Semana 5 | 🔄 En proceso
R009 | Licenciamiento Oracle vence sin renovación | Media | Crítico | Alertar a MME desde día 1; incluir en informes quincenales | 🔄 Alerta activa

---

9. INDICADORES DE ALERTA TEMPRANA (WATCHLIST)

Semáforo | Indicador | Qué significa | Acción
---|---|---|---
🔴 | INTERNEXA niega acceso a nuevos ingenieros | Sabotaje pasivo | Escalar a MME contractualmente en 24h
🔴 | Personal clave de INTERNEXA renuncia en masa | Fuga de conocimiento | Acelerar shadowing; grabar todo lo posible
🔴 | Licenciamiento Oracle vence sin renovación | Riesgo de caída total | Alertar a MME; evaluar PostgreSQL como alternativa
🟡 | Documentación solicitada tarda semanas en llegar | Resistencia a transición | Presionar contractualmente; documentar nosotros
🟡 | Nuevo operador pide "más tiempo" recurrentemente | Subestimaron complejidad | Evaluar extensión con MME; ajustar cronograma
🟡 | Fallos en integraciones (SIGDI, ANH) durante transición | Problemas de autenticación/credenciales | Documentar; renegociar credenciales con terceros
🟢 | Shadowing operativo comienza a tiempo | Buena señal | Continuar según plan
🟢 | Nuevo operador hace preguntas técnicas profundas | Están realmente entendiendo | Fomentar cultura de aprendizaje
🟢 | Pruebas DRP ejecutadas con nuevo operador | Confianza en recuperación | Documentar resultado

---

10. RECOMENDACIONES ESTRATÉGICAS

1. Determinar la fecha real de cierre del contrato GGC-2034-2025. Sin esta fecha, toda planificación es ciega.

2. Si la fecha límite es en menos de 3 meses: Negociar prórroga técnica con INTERNEXA (aunque sea por 90 días). Comenzar transición INMEDIATA. No esperar una migración limpia; esperar una migración "con heridas".

3. Si la fecha límite es en 3-6 meses: Es viable, pero hay que moverse YA. El riesgo más alto es el licenciamiento (tiempo de compra Oracle + VMware). Requiere un project manager de hierro y un líder técnico que conozca el SICOM.

4. Si la fecha límite es en 6+ meses: La migración es totalmente viable si se planifica bien. Aprovechar para hacer limpieza: mitigar vulnerabilidades, documentar deuda técnica, mejorar monitoreo.

5. Presupuesto de licenciamiento: El MME debe conocer que necesita $285,000-570,000 USD anuales en licenciamiento (Oracle, BI, VMware, Fortinet, Bizagi, Veeam). No hay línea presupuestal visible en los documentos analizados.

---

11. CONCLUSIÓN

La migración del SICOM es TÉCNICAMENTE posible, pero OPERATIVAMENTE peligrosa sin una transición planificada. La incertidumbre sobre la fecha de cierre del contrato convierte una tarea difícil en una ruleta rusa.

Condición | Éxito?
---|---
Migración sin fecha clara + sin plan + sin presupuesto | ❌ NO. Es suicidio.
Migración con 3-6 meses + plan + presupuesto + cooperación | ✅ Sí. Difícil, pero viable.
Migración con 6+ meses + plan + presupuesto + líder técnico | ✅ Sí. Altamente viable.
Mantener INTERNEXA mientras se prepara transición | ✅ Sí. La opción más inteligente a corto plazo.

> "Migrar el SICOM sin un plan de transición documentado es como intentar trasladar un hospital en funcionamiento a otro edificio sin parar las operaciones quirúrgicas. Se puede hacer, pero alguien se va a morir en el camino."

---

Documento elaborado por ZEUS — Innovadataco
Fecha: 2026-06-06
Versión: 2.0 (Actualización con estado de empalme a junio 2026)
Clasificación: Interno — CI2 / IND TECH / MME
Elaborado para: Jelkin Zair Carrillo Franco (Gerente de Empalme / PM Ejecutivo)

> "ZEUS online. La empresa está operando." ⚡
