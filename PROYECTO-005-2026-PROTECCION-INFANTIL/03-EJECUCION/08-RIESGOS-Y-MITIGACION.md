# RIESGOS Y MITIGACIÓN — Semáforo de Confianza

**Proyecto:** 005 — Semáforo de Confianza
**Código:** IDC_2026_05
**Fecha:** 13 de junio de 2026
**Versión:** 2.0
**Autor:** ZEUS EOS

---

## 1. MATRIZ DE RIESGOS

### 1.1 Riesgos de Negocio (Estratégicos)

| ID | Riesgo | Descripción | Probabilidad | Impacto | Estrategia | Mitigación | Responsable | Estado |
|----|--------|-------------|-------------|---------|------------|------------|-------------|--------|
| RN-01 | Responsabilidad legal si reporte no se procesa | Si un reporte severe no llega a autoridades y ocurre un daño, ¿Innovadataco es responsable? | Media | **Catastrófico** | Mitigar | Innovadataco es canal tecnológico, no operador. Contrato limita responsabilidad. Seguro de responsabilidad civil. Cláusula de canal tecnológico en todos los contratos. | Diana (Legal) | Pendiente |
| RN-02 | Falta de adopción por autoridades | ICBF o Fiscalía no integran el sistema por burocracia o desconfianza | Alta | Alto | Mitigar | Iniciar con B2C + B2B2C (colegios) para generar ingresos y casos de uso. Construir credibilidad con demo funcional. Piloto gratuito 3 meses. Open source para auditoría comunitaria. | Jelkin (CEO) | Activo |
| RN-03 | Reputación comprometida por hackeo | Si el sistema es hackeado o filtra datos, la marca Innovadataco queda comprometida | Baja | **Catastrófico** | Mitigar | Inversión en seguridad desde día 1 (ya en Módulo 001). Auditoría externa antes de producción. Open source para auditoría comunitaria. Plan de respuesta a incidentes. Rotación de claves. | ODIN + ZEUS | Activo |
| RN-04 | Modelo de negocio no viable | No se consiguen suscriptores B2C ni colegios B2B2C en 18 meses | Media | Alto | Mitigar | Freemium B2C + B2B2C colegios como base. B2G como línea secundaria. Costos bajos ($30-$140/mes). MVP funcional en 6 meses. Marketing desde Fase 2. | Jelkin (CEO) | Activo |
| RN-05 | Spam y falsos reportes | Reportes falsos o de broma saturan el sistema y deslegitiman las alertas | Media | Medio | Mitigar | Rate limiting (5/hr). Scoring de IA (Módulo 003) para filtrar spam. Panel admin para revisión humana. Reputación de reporte (múltiples reportes del mismo IP = flag). | ODIN + ZEUS | Activo |
| RN-06 | Competencia de grandes tecnológicas | Google, Microsoft, ONGs globales lanzan solución similar | Baja | Medio | Mitigar | Diferenciación: anonimato absoluto + encriptación local + PWA sin tracking + diseño para LATAM + freemium. Velocidad de ejecución (6 meses a MVP). Comunidad local. | ZEUS (Estrategia) | Activo |
| RN-07 | Colegios no adoptan B2B2C | Colegios no ven valor o no tienen presupuesto para el plan B2B2C | Media | Alto | Mitigar | Piloto gratuito 1 mes. Demo con datos de impacto ("3 reportes de su comunidad esta semana"). Case study de otros colegios. Precio accesible ($1,000-$2,500/año). ROI claro: protección de alumnos, reputación institucional. | Zaira (Marketing) | Activo |
| RN-08 | Cambio de gobierno o política | Cambio de gobierno elimina programa de protección infantil que podría financiar el proyecto | Baja | Alto | Mitigar | No depender de una sola fuente de financiación. Diversificar a B2C + B2B2C + ONGs internacionales. Producto autosostenible con freemium. | Jelkin (CEO) | Activo |
| RN-09 | Retraso en aprobación de ADRs | Decisiones técnicas críticas (IA, clustering, pasarela) no se aprueban a tiempo | Baja | Medio | Mitigar | ADRs son recomendaciones de ZEUS. Si Jelkin no responde en 7 días, ZEUS/ODIN proceden con recomendación por defecto. Documentar decisión en DECISIONES.md. | ZEUS | Activo |
| RN-10 | Presupuesto insuficiente | Costos de infraestructura, auditoría, marketing exceden presupuesto | Media | Medio | Mitigar | MVP con costos mínimos ($30/mes). Escalar solo cuando hay ingresos. Priorizar features por impacto/hora. Open source para reducir costos de licencia. | ZEUS + Jelkin | Activo |

### 1.2 Riesgos de Proyecto (Técnicos y Operativos)

| ID | Riesgo | Descripción | Probabilidad | Impacto | Estrategia | Mitigación | Responsable | Estado |
|----|--------|-------------|-------------|---------|------------|------------|-------------|--------|
| RP-01 | Dependencia técnica de ODIN | ODIN es el único desarrollador. Si no está disponible, el proyecto se detiene. | Media | Alto | Mitigar | Documentación SDD completa (specs, plans, tasks, ADRs). Juan como backup técnico (capacitación progresiva). Código limpio, comentado, tests ≥80%. Git con ramas claras. | ZEUS | Activo |
| RP-02 | Dataset de IA insuficiente | 1,500 ejemplos sintéticos no son suficientes para modelo robusto. AUC-ROC < 0.80. | Media | Alto | Mitigar | Dataset sintético + data augmentation (back-translation, synonym replacement). Re-entrenar con 500 reportes reales (con consentimiento). Si AUC-ROC < 0.80, usar keyword matching como fallback para Módulo 003. Evaluar compra de dataset anónimo. | ODIN | Activo |
| RP-03 | Clave de encriptación comprometida | KEK (Key Encryption Key) se expone por error de configuración, leak en repo, o acceso al servidor. | Baja | **Catastrófico** | Mitigar | KEK en variable de entorno, nunca en código ni repo. Rotación manual cada 6 meses. Script de re-encriptación. Backup de KEK en GPG + cofre físico (Diana). HSM en futuro. Plan de respuesta a incidentes: rotación inmediata + notificación. | ODIN + ZEUS | Activo |
| RP-04 | IA sesgada o injusta | Modelo clasifica reportes de ciertos dialectos o géneros como menos graves. | Media | Alto | Mitigar | Fairness audit: disparidad <10% entre subgrupos. Dataset balanceado (estratificado por dialecto, género, tipo de evidencia). Red-teaming: 0 falsos negativos de alto riesgo. Si disparidad >10%, re-entrenar con pesos por grupo. | ODIN + ZEUS | Activo |
| RP-05 | Instituciones no tienen API | ICBF, Fiscalía, Policía no tienen API pública para integración. | Alta | Medio | Mitigar | Email estructurado como fallback universal (funciona con cualquier institución). Panel admin como portal web para lectura manual. API gateway para instituciones que sí tengan capacidad técnica. Nunca depender de API institucional para completar funcionalidad. | ODIN | Activo |
| RP-06 | Geocodificación imprecisa | MaxMind GeoLite2 no es 100% preciso, especialmente para móviles con VPN. | Alta | Medio | Mitigar | Usar solo ciudad/país aproximado, nunca coordenadas exactas. Graceful degradation: si GeoLite2 no disponible, continuar sin geocodificación. Actualización mensual de base de datos. No usar geocodificación para scoring individual, solo para clustering. | ODIN | Activo |
| RP-07 | PWA no funciona en iOS | iOS limita PWA: no push notifications, no add-to-home automático, storage limitado. | Media | Medio | Mitigar | Instrucciones visuales en onboarding ("Añadir a inicio"). Usar SMS/email para alertas premium (no push). Graceful degradation: si PWA no instala, funciona como web app normal. Evaluar wrapper Capacitor si escala a 100,000+ usuarios. | ODIN + Zaira | Activo |
| RP-08 | Retraso en cronograma | Un módulo se retrasa y afecta los demás. | Media | Alto | Mitigar | Módulos independientes donde sea posible. Fallbacks: si IA no está lista, usar keyword matching. Si pasarela no está lista, usar email manual. Buffer de 1 semana por fase. Documentación SDD permite que Juan asuma tareas. | ZEUS | Activo |
| RP-09 | Fuga de evidencia multimedia | Imagen o video de un reporte se filtra por error de configuración de filesystem. | Baja | **Catastrófico** | Mitigar | Evidencia encriptada con AES-256-GCM. Nombre de archivo aleatorio (UUID). Sin directorio estructurado por fecha. URL de evidencia solo accesible con token temporal (JWT, 5 min) y autenticación admin. Nunca URL directa. Audit trail de cada acceso. | ODIN | Activo |
| RP-10 | Brute force de admin panel | Atacante intenta adivinar password de admin para acceder a datos sensibles. | Media | Alto | Mitigar | Bcrypt 12 rounds. Rate limiting login: 5 intentos / 15 min. Bloqueo de cuenta tras 10 intentos fallidos (requiere reset por root). 2FA opcional (recomendado para root y admin). JWT expira en 1h. Alerta de login desde IP nueva. | ODIN | Activo |
| RP-11 | Email de alerta bloqueado como spam | Alertas a ICBF/Fiscalía van a spam o son rechazadas por filtros. | Media | Medio | Mitigar | SPF, DKIM, DMARC configurados desde día 1. Nombre de remitente profesional (alertas@semaforo.innovadataco.com). Whitelist de dominios de instituciones. Confirmación de recepción por institución. Retry con backoff. | ODIN | Activo |
| RP-12 | Escalabilidad del clustering | Con 10,000+ reportes, el recálculo de perfiles se vuelve lento. | Baja | Medio | Mitigar | Índice en identifier_hash (PostgreSQL B-tree). Cache Redis para perfiles (TTL 1h). Recálculo lazy: recalcular solo si TTL expiró. Background job (Celery) para recálculo. Query optimizada. Particionamiento de tabla reports por mes si escala a 100,000+. | ODIN | Activo |
| RP-13 | Fairness audit falla | Disparidad entre subgrupos >10%, modelo sesgado. | Media | Alto | Mitigar | Re-entrenar con pesos por grupo. Data augmentation para subgrupos subrepresentados. Ajustar threshold por subgrupo. Si no se puede mitigar, documentar limitación en model card y no usar modelo para scores >0.7 en ese subgrupo. | ODIN + ZEUS | Activo |
| RP-14 | Dependencia de proveedores externos | Dependencia de DigitalOcean, Stripe, SendGrid, MaxMind. Si cierran o suben precios... | Baja | Medio | Mitigar | Stack open source: PostgreSQL, Redis, Nginx, Let's Encrypt (no dependencia de proveedor). VPS puede migrarse a Hetzner, AWS, GCP en <1 día. Email puede usar SMTP propio. MaxMind es local (database descargada). Stripe es opcional (MVP puede funcionar sin pagos). | ZEUS | Activo |
| RP-15 | Retraso en aprobación de contrato con institución | ICBF/Fiscalía tardan 6-12 meses en aprobar contrato o piloto. | Alta | Alto | Mitigar | No bloquear proyecto por contrato institucional. B2C + B2B2C como líneas principales. B2G como línea secundaria. Contacto paralelo con múltiples instituciones. Postular a convocatorias de MinTIC, BID Lab, USAID. | Jelkin (CEO) | Activo |
| RP-16 | Modelo de IA sobreajustado (overfitting) | Modelo funciona bien en dataset sintético pero mal en datos reales. | Media | Alto | Mitigar | Cross-validation (5-fold). Test holdout (15% del dataset). Regularización (C=0.5 en LR, max_depth=10 en RF). Early stopping. Re-entrenar con 500 reportes reales. Monitoreo de drift en producción. Si AUC-ROC cae <0.75, re-entrenar. | ODIN | Activo |
| RP-17 | Usuario consiente ubicación por error | Checkbox de consentimiento está marcado por defecto o es confuso. | Baja | Medio | Mitigar | Checkbox no pre-marcado. Texto claro: "Compartir mi ciudad aproximada para detectar redes organizadas. Esto mejora la seguridad de la comunidad." Puede desactivarse sin afectar el envío del reporte. | ODIN + Zaira | Activo |
| RP-18 | Falsa alarma de red organizada | Clustering detecta red organizada cuando no lo es (falsos positivos). | Media | Medio | Mitigar | 2+ criterios requeridos para flag is_network. No solo ciudades. Revisión humana en panel admin antes de alertar a autoridades. Threshold ajustable en configuración. | ODIN + ZEUS | Activo |
| RP-19 | Costo de infraestructura crece | VPS, BD, cache, backups, monitoreo superan presupuesto. | Media | Medio | Mitigar | MVP con costos mínimos ($30/mes). Escalar solo cuando hay ingresos. Monitoreo de costos semanal. Optimizar queries y cache. Usar CDN gratuito (Cloudflare). Backup solo de BD (no evidencia, que ya está encriptada en filesystem). | ZEUS | Activo |
| RP-20 | Vulnerabilidad en dependencia de terceros | Vulnerabilidad crítica en FastAPI, React, PostgreSQL, Redis, etc. | Baja | Alto | Mitigar | Dependabot en GitHub (alertas automáticas de CVE). Actualización de dependencias mensual. Tests de regresión antes de actualizar. Pin de versiones en requirements.txt/package.json. Contenedores Docker con versiones fijas. | ODIN | Activo |

---

## 2. MAPA DE RIESGOS (Probabilidad vs Impacto)

```
Impacto
  ↑
Catastrófico │  RN-03   RN-01   RP-03   RP-09
             │  (baja)  (media) (baja)  (baja)
  ↑
    Alto     │  RN-02   RN-04   RN-07   RN-08
             │  (alta)  (media) (media) (baja)
             │  RP-01   RP-02   RP-04   RP-05
             │  (media) (media) (media) (alta)
             │  RP-08   RP-10   RP-13   RP-15
             │  (media) (media) (media) (alta)
             │  RP-16   RP-20
             │  (media) (baja)
  ↑
   Medio     │  RN-05   RN-06   RN-09   RN-10
             │  (media) (baja)  (baja)  (media)
             │  RP-06   RP-07   RP-11   RP-12
             │  (alta)  (media) (media) (baja)
             │  RP-14   RP-17   RP-18   RP-19
             │  (baja)  (baja)  (media) (media)
  ↓
    Bajo     │
             └────────────────────────────────────→ Probabilidad
              Baja    Media    Alta
```

---

## 3. PLAN DE CONTINGENCIA

### 3.1 Contingencia: ODIN No Disponible

| Escenario | Acción | Responsable | Tiempo |
|-----------|--------|-------------|--------|
| ODIN no disponible 1-2 días | Juan asume tareas de soporte y QA. ZEUS coordina. | Juan + ZEUS | Inmediato |
| ODIN no disponible 1-2 semanas | Juan asume desarrollo de tareas documentadas (specs, plans, tasks). ZEUS revisa PRs. | Juan + ZEUS | 1 semana |
| ODIN no disponible >1 mes | Contratar desarrollador freelance (Upwork, Toptal). ZEUS entrega specs completos. | Jelkin + ZEUS | 2 semanas |
| ODIN permanentemente no disponible | Juan asume lead técnico. Contratar desarrollador adicional. Reestimar cronograma. | Jelkin + ZEUS | 1 mes |

### 3.2 Contingencia: AUC-ROC < 0.80

| Escenario | Acción | Responsable | Tiempo |
|-----------|--------|-------------|--------|
| AUC-ROC 0.75-0.80 | Ajustar hiperparámetros (C, max_depth, n_estimators). Data augmentation. | ODIN | 1 semana |
| AUC-ROC 0.70-0.75 | Añadir más features (embeddings distiluse). Re-etiquetar dataset. | ODIN | 2 semanas |
| AUC-ROC < 0.70 | Usar keyword matching como fallback para Módulo 003. Documentar limitación. Re-evaluar modelo BERT cuando haya más datos. | ODIN + ZEUS | 1 semana |

### 3.3 Contingencia: Institución No Responde

| Escenario | Acción | Responsable | Tiempo |
|-----------|--------|-------------|--------|
| ICBF no responde en 1 mes | Contactar Fiscalía. Contactar Policía. Postular a convocatoria MinTIC. | Jelkin | Inmediato |
| Ninguna institución responde en 3 meses | Enfocar en B2C + B2B2C. El producto no depende de B2G para funcionar. | Jelkin + ZEUS | Inmediato |
| Institución responde pero no tiene API | Usar email estructurado. Panel admin como portal. No bloquear proyecto. | ODIN | Inmediato |

### 3.4 Contingencia: KEK Comprometida

| Escenario | Acción | Responsable | Tiempo |
|-----------|--------|-------------|--------|
| KEK expuesta en logs | Rotar KEK inmediatamente. Re-encriptar todos los datos. Revisar logs. Notificar a Jelkin y Diana. | ODIN | 4 horas |
| KEK expuesta en repo | Rotar KEK. Eliminar del historial de Git (git filter-repo). Re-encriptar. Cambiar credenciales. | ODIN | 8 horas |
| KEK expuesta en servidor comprometido | Rotar KEK. Re-encriptar. Migrar a nuevo servidor. Auditoría de seguridad. Notificar a autoridades si aplica. | ODIN + ZEUS | 24 horas |

### 3.5 Contingencia: DDoS o Ataque

| Escenario | Acción | Responsable | Tiempo |
|-----------|--------|-------------|--------|
| DDoS leve (<1Gbps) | Nginx rate limiting. Cloudflare (si activado). Escalar VPS temporalmente. | ODIN | 1 hora |
| DDoS severo (>1Gbps) | Activar Cloudflare Pro. Escalar a CDN. Contactar DigitalOcean support. | ODIN + ZEUS | 2 horas |
| Defacement o compromiso | Restaurar desde backup. Rotar credenciales. Auditoría de logs. Reportar a autoridades. | ODIN + ZEUS | 4 horas |

---

## 4. REGISTRO DE RIESGOS ACTUALIZADO

| Fecha | Riesgo | Acción Tomada | Responsable | Estado |
|-------|--------|--------------|-------------|--------|
| 2026-06-13 | RN-01 | Documentado en ADR-005 y contrato template. Diana revisa. | ZEUS | Pendiente aprobación Diana |
| 2026-06-13 | RP-01 | Documentación SDD completa generada. Juan inicia capacitación. | ZEUS | Activo |
| 2026-06-13 | RP-03 | KEK en env var. Script de rotación planificado. Backup GPG en cofre de Diana. | ODIN | Activo |
| 2026-06-13 | RN-04 | Modelo freemium B2C + B2B2C definido. Landing page planificada para julio. | ZEUS + Zaira | Activo |
| 2026-06-13 | RN-05 | Rate limiting implementado (Módulo 001). Panel admin para revisión en Módulo 005. | ODIN | Parcialmente mitigado |
| 2026-06-13 | RN-03 | Auditoría de seguridad interna planificada (octubre). Auditoría externa (noviembre). | ZEUS | Activo |
| 2026-06-13 | RP-05 | Email estructurado como fallback definido en ADR-005. API gateway como primario. | ZEUS | Activo |
| 2026-06-13 | RP-06 | GeoLite2 local configurado. Solo ciudad/país. Graceful degradation. | ODIN | Activo |
| 2026-06-13 | RP-07 | PWA con instrucciones de instalación. SMS/email para alertas premium. | ODIN + Zaira | Activo |
| 2026-06-13 | RP-08 | Buffer de 1 semana por fase. Fallbacks definidos (keyword matching, email manual). | ZEUS | Activo |
| 2026-06-13 | RP-09 | Encriptación AES-256-GCM. UUID para nombres de archivo. Token temporal para URL. | ODIN | Activo |
| 2026-06-13 | RP-10 | Bcrypt 12 rounds. Rate limiting login. 2FA opcional. | ODIN | Activo |
| 2026-06-13 | RP-15 | Contacto con ICBF planificado para septiembre. Postular a MinTIC/BID en paralelo. | Jelkin | Activo |
| 2026-06-13 | RP-16 | Cross-validation 5-fold. Regularización. Test holdout. Drift monitoring en producción. | ODIN | Activo |
| 2026-06-13 | RP-20 | Dependabot activado. Actualización mensual planificada. Pin de versiones. | ODIN | Activo |

---

> *Documento generado por ZEUS — Innovadataco*
> *Versión 2.0 — Riesgos y mitigación del Semáforo de Confianza*
> *20 riesgos identificados, 15 mitigaciones activas, 4 contingencias documentadas*
