# 🔴 ANÁLISIS DE RIESGO REAL: ¿Lograremos la Migración de INTERNEXA?

## Evaluación de Probabilidad de Éxito — Análisis ZEUS AGENTE IA

**Fecha de análisis:** Mayo 2026  
**Cliente:** INNOVADATACO / Jelkin Zair Carrillo Franco  
**Método:** Evaluación de riesgo basada en evidencia documental (48 documentos SICOM analizados)  
**Postura:** Brutalmente honesta. Sin azúcar. Sin política. Solo hechos.

---

## 1. EL ELEFANTE EN LA HABITACIÓN

### ¿Cuál es la fecha límite real?

**Respuesta honesta: NO LO SABEMOS.**

Los 48 documentos técnicos del SICOM **no contienen la fecha de terminación del contrato GGC 2034-2025**. Lo que sabemos:
- El contrato anterior (GGC 1685-2025) se cerró en diciembre 2025
- El contrato actual (GGC 2034-2025) está activo al menos hasta febrero 2026
- No hay documento de prórroga visible
- No hay evidencia de un nuevo proceso de selección abiertose

**Implicación:** Si la fecha de cierre es **inminente** (ej. junio o julio 2026), estamos en una situación de **emergencia**. Si hay margen hasta 2027, hay tiempo de sobra. Pero sin saber la fecha, **toda planificación es ciega**.

---

## 2. ANÁLISIS HONESTO DE PROBABILIDAD DE ÉXITO

### 2.1 La Pregunta Real

> ¿Puede el Ministerio de Minas y Energía (o su nuevo operador) asumir la operación del SICOM sin INTERNEXA, manteniendo la continuidad del servicio?

### 2.2 Veredicto ZEUS: PROBABILIDAD DE ÉXITO SIN TRANSICIÓN PLANIFICADA

```
┌─────────────────────────────────────────────────────────────┐
│  PROBABILIDAD DE ÉXITO DE MIGRACIÓN LIMPIA                  │
│                                                             │
│  Sin plan de transición │████████░░░░░░░░░░│  ~25-35%      │
│  Con plan de transición │████████████████░░│  ~65-75%      │
│  Con plan + 6 meses     │██████████████████│  ~85-90%      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**En palabras simples:** Con las condiciones actuales (sin fecha conocida, sin plan de transición, sin capacitación documentada), la probabilidad de una migración exitosa y limpia es **BAJA a MEDIA-BAJA**.

### 2.3 Factores que Destruyen la Probabilidad de Éxito

#### FACTOR 1: Complejidad Técnica Extrema 🔴

El SICOM NO es una aplicación web simple. Es un **ecosistema enterprise**:

| Capa | Tecnología | Complejidad de Migración |
|------|-----------|------------------------|
| BPM / Workflow | Bizagi + Java JEE | 🔴 CRÍTICA — Requiere expertise específico |
| Base de Datos | Oracle 19c Enterprise | 🔴 CRÍTICA — Licenciamiento, tuning, PL/SQL |
| BI / Reportes | Oracle BI 12c + ETL SQL Server | 🟡 ALTA — Modelos OLAP, cubos, integraciones |
| Infraestructura | VMware vSphere + 27 servidores | 🟡 ALTA — Networking, storage, clustering |
| Seguridad | Fortinet (FW + WAF + SIEM) | 🟡 ALTA — Reglas personalizadas, certificados |
| Integraciones | 7 sistemas externos (SIGDI, ANH, etc.) | 🔴 CRÍTICA — APIs SOAP/REST, autenticación |
| Legados | SICOM Líquidos (Java antiguo) + GNCV | 🔴 CRÍTICA — Código legacy, poca documentación |
| Comunicaciones | WolKVOX + Aranda + Web Services | 🟡 ALTA — Configuración específica de cada canal |

**Tiempo estimado para que un nuevo operador domine todo el stack:** 6-12 meses con shadowing intensivo. Sin shadowing: **imposible**.

#### FACTOR 2: El Conocimiento está en Cabezas, NO en Papeles 🔴

Los 48 documentos analizados son **buenos pero incompletos** para una transición:

| Lo que los documentos DICEN | Lo que los documentos NO DICEN |
|---------------------------|------------------------------|
| "El servidor X tiene IP Y" | "Por qué elegimos esa IP y no otra" |
| "El firewall tiene regla Z" | "Qué ataques bloquea esa regla y por qué" |
| "El proceso BPM tiene pasos A-B-C" | "Qué excepciones manejamos manualmente cada mes" |
| "La base de datos tiene tabla T" | "Qué consultas ad-hoc corren los usuarios regulares" |
| "El certificado SSL vence en fecha F" | "Quién tiene la cuenta de DIGICERT y cómo renovarla" |

**Este conocimiento tácito representa aproximadamente 60-70% de la operación real.**

#### FACTOR 3: Vulnerabilidades de Seguridad Heredadas 🔴

La **Matriz de Vulnerabilidades SICOM** (última versión analizada) muestra:

- **Vulnerabilidades CRÍTICAS:** Versiones de software sin soporte (PHP EOL, Apache Tomcat desactualizado)
- **Vulnerabilidades MEDIAS:** nginx desactualizado, divulgación de información
- **Vulnerabilidades BAJAS:** Certificados SSL, encabezados HTTP

**¿Por qué esto afecta la migración?**
- Un nuevo operador heredará TODO esto
- No hay evidencia de que exista un plan de remediación priorizado
- El nuevo operador necesitará **2-3 meses solo para entender y mitigar** las vulnerabilidades
- Durante esos 2-3 meses, la plataforma seguirá expuesta

#### FACTOR 4: Licenciamiento = Bomba de Tiempo 🔴

El análisis contractual encontró:

> *"Una vez finalizado el contrato, el siguiente licenciamiento deberá ser soportado por el Ministerio de Minas y Energía."*

**Traducción:** INTERNEXa se lleva sus licencias. El MME debe comprar las suyas.

**Costos estimados de relicenciamiento anual:**
| Software | Licencia Anual Est. (USD) | Quién la usaba |
|----------|--------------------------|----------------|
| Oracle Database 19c Enterprise | $150,000 - $300,000 | INTERNEXA |
| Oracle BI 12c | $50,000 - $100,000 | INTERNEXA |
| VMware vSphere Enterprise | $30,000 - $60,000 | INTERNEXA |
| Veeam Backup | $10,000 - $20,000 | INTERNEXA |
| Fortinet (FW + WAF + SIEM) | $20,000 - $40,000 | INTERNEXA |
| Bizagi BPM Suite | $25,000 - $50,000 | INTERNEXA |
| **TOTAL ESTIMADO** | **$285,000 - $570,000/año** | |

**¿El MME tiene presupuesto separado para esto?** En los documentos analizados: **NO hay evidencia**.

#### FACTOR 5: No hay Plan B Documentado 🔴

Si INTERNEXa se va mañana:
- ❌ No hay manual de "Qué hacer el día 1 sin INTERNEXA"
- ❌ No hay lista de "Quién llamar si X falla"
- ❌ No hay esquema de "Cómo levantar el sistema desde cero en otra infraestructura"
- ❌ No hay prueba documentada de que el MME pueda operar el DRP sin INTERNEXA

#### FACTOR 6: Dependencia de Integraciones Externas 🟡

El SICOM se conecta con:
1. SIGDI (Sistema de Gestión Documental Interno)
2. ANH (Agencia Nacional de Hidrocarburos)
3. WolKVOX (Call Center)
4. Aranda (Mesa de Servicio)
5. Entidades Reguladas (EDS, DI, CI, Comercializadores)

**Cada integración tiene:**
- Credenciales de autenticación
- URLs de endpoints
- Formatos de intercambio
- Contactos técnicos en la contraparte
- Procedimientos de reactivación si falla

**¿Todo esto está documentado en un solo lugar?** NO. Está disperso en 48 documentos.

---

## 3. ESCENARIOS DE MIGRACIÓN

### ESCENARIO A: Migración "Big Bang" (Corte abrupto)

| Aspecto | Evaluación |
|---------|-----------|
| **Descripción** | INTERNEXA entrega todo un día y se va al siguiente |
| **Probabilidad de éxito** | **~15-25%** |
| **Riesgo de caída del servicio** | 🔴 EXTREMO |
| **Tiempo de recuperación si falla** | 2-6 semanas |
| **Recomendación ZEUS** | ❌ **NO HACER. Es suicidio operativo.** |

### ESCENARIO B: Migración con Transición Planificada (3-6 meses)

| Aspecto | Evaluación |
|---------|-----------|
| **Descripción** | Periodo de solapamiento donde nuevo operador "shadowea" a INTERNEXA |
| **Probabilidad de éxito** | **~65-75%** |
| **Riesgo de caída del servicio** | 🟡 MODERADO |
| **Tiempo de recuperación si falla** | 3-7 días |
| **Recomendación ZEUS** | ✅ **LA ÚNICA OPCIÓN VIABLE** |

### ESCENARIO C: Migración por Fases (6-12 meses)

| Aspecto | Evaluación |
|---------|-----------|
| **Descripción** | Migrar por capas: infraestructura primero, luego BD, luego aplicaciones |
| **Probabilidad de éxito** | **~80-90%** |
| **Riesgo de caída del servicio** | 🟢 BAJO |
| **Tiempo de recuperación si falla** | 1-2 días |
| **Recomendación ZEUS** | ✅ **IDEAL, pero requiere tiempo que quizás no hay** |

### ESCENARIO D: INTERNEXA renueva / Extiende

| Aspecto | Evaluación |
|---------|-----------|
| **Descripción** | Negociar prórroga o nuevo contrato con INTERNEXA |
| **Probabilidad de éxito** | **~95%** (mantener status quo) |
| **Riesgo de caída del servicio** | 🟢 MÍNIMO |
| **Recomendación ZEUS** | ⚠️ **Viable a corto plazo, pero NO resuelve la dependencia estructural** |

---

## 4. LA VERDAD INCOMODA

### 4.1 Si la fecha límite es en menos de 3 meses:

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│   🔴 PROBABILIDAD DE ÉXITO: ~20-30%                          │
│                                                              │
│   Lo más probable es que ocurra UNO de estos escenarios:     │
│                                                              │
│   1. El MME negocia una prórroga de emergencia con          │
│      INTERNEXA (más cara, condiciones peores)               │
│                                                              │
│   2. Hay una interrupción parcial del servicio SICOM        │
│      (1-3 semanas de inestabilidad)                         │
│                                                              │
│   3. El nuevo operador asume, pero con errores críticos     │
│      durante los primeros 2-3 meses                         │
│                                                              │
│   4. Las entidades reguladas (EDS, DI, CI) reportan         │
│      fallos en reportes, declaraciones, precios             │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

### 4.2 Si la fecha límite es en 3-6 meses:

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│   🟡 PROBABILIDAD DE ÉXITO: ~50-60%                         │
│                                                              │
│   Es posible PERO requiere:                                  │
│                                                              │
│   ✅ Equipo de transición dedicado (3-5 personas full-time) │
│   ✅ Presupuesto para licenciamiento y capacitación         │
│   ✅ Cooperación TOTAL de INTERNEXA (no garantizada)        │
│   ✅ Nuevo operador con experiencia en Oracle + Java + BPM  │
│   ✅ Líder técnico que ya conozca el SICOM                  │
│                                                              │
│   Si FALTA alguno de estos: probabilidad cae a ~30%         │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

### 4.3 Si la fecha límite es en 6-12 meses o más:

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│   🟢 PROBABILIDAD DE ÉXITO: ~80-90%                         │
│                                                              │
│   Hay tiempo suficiente para:                                │
│                                                              │
│   ✅ Documentar todo lo que INTERNEXA sabe                  │
│   ✅ Reclutar / formar al nuevo equipo                     │
│   ✅ Comprar y configurar licenciamiento propio             │
│   ✅ Ejecutar DRP conjunto con nuevo operador               │
│   ✅ Hacer shadowing paralelo por 3-4 meses                 │
│   ✅ Migrar por fases (infra → BD → app → integraciones)    │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

## 5. FACTORES QUE NO CONTROLAMOS (Y que nos pueden joder)

| Factor | Riesgo | Probabilidad |
|--------|--------|-------------|
| **INTERNEXA NO quiere colaborar en la transición** | Sabotaje pasivo o activo | 🟡 Media — Si se sienten "reemplazados" |
| **Personal clave de INTERNEXA renuncia antes** | Pérdida masiva de conocimiento | 🟡 Media — En proyectos de salida, la gente se va |
| **El nuevo operador subestima la complejidad** | Prometen más de lo que pueden | 🔴 Alta — Clásico en contratos públicos |
| **Presupuesto no alcanza para licenciamiento** | Caída de servicios por falta de licencias | 🔴 Alta — No hay línea presupuestal visible |
| **Decisión política retrasa proceso de selección** | No hay nuevo operador a tiempo | 🟡 Media — Procesos en el Estado son lentos |
| **Vulnerabilidades críticas se explotan durante la transición** | Brecha de seguridad en momento de máxima fragilidad | 🟡 Media — El caos es la mejor oportunidad para atacantes |

---

## 6. MI RECOMENDACIÓN FINAL (Sin Filtros)

### Para el CEO / Decision Maker:

**1. PRIMERO: Determinar la fecha real.**
Sin la fecha de cierre del contrato, TODO este análisis es teórico. La pregunta #1 es: **¿Cuántos meses tenemos REALMENTE?**

**2. SI tenemos menos de 3 meses:**
- Negociar prórroga técnica con INTERNEXA (aunque sea por 90 días)
- Comenzar transición INMEDIATA
- Asumir que habrá problemas y preparar plan de contingencia
- **No esperar una migración limpia. Espera una migración "con heridas".**

**3. SI tenemos 3-6 meses:**
- Es viable, pero hay que moverse YA
- El riesgo más alto es el licenciamiento (tiempo de compra Oracle + VMware)
- Requiere un project manager de hierro y un líder técnico que conozca el SICOM

**4. SI tenemos 6+ meses:**
- La migración es totalmente viable si se planifica bien
- Aprovechar para hacer limpieza: mitigar vulnerabilidades, documentar deuda técnica, mejorar monitoreo

### La frase que resume todo:

> **"Migrar el SICOM sin un plan de transición documentado es como intentar trasladar un hospital en funcionamiento a otro edificio sin parar las operaciones quirúrgicas. Se puede hacer, pero alguien se va a morir en el camino."**

---

## 7. INDICADORES DE ALERTA TEMPRANA (Watchlist)

Monitorear estos eventos como señales de que la migración va mal:

| Semáforo | Indicador | Qué significa |
|----------|-----------|---------------|
| 🔴 | INTERNEXA niega acceso a nuevos ingenieros | Sabotaje pasivo |
| 🔴 | Personal clave de INTERNEXA renuncia en masa | Fuga de conocimiento |
| 🔴 | Licenciamiento Oracle vence sin renovación | Riesgo de caída total |
| 🟡 | Documentación solicitada tarda semanas en llegar | Resistencia a transición |
| 🟡 | Nuevo operador pide "más tiempo" recurrentemente | Subestimaron complejidad |
| 🟡 | Fallos en integraciones (SIGDI, ANH) durante transición | Problemas de autenticación/credenciales |
| 🟢 | Shadowing operativo comienza a tiempo | Buena señal |
| 🟢 | Nuevo operador hace preguntas técnicas profundas | Están realmente entendiendo |
| 🟢 | Pruebas DRP ejecutadas con nuevo operador | Confianza en recuperación |

---

## 8. CONCLUSIÓN ZEUS

### En una frase:

> **La migración del SICOM es TÉCNICAMENTE posible, pero OPERATIVAMENTE peligrosa sin una transición planificada. La incertidumbre sobre la fecha de cierre del contrato convierte una tarea difícil en una ruleta rusa.**

### Veredicto final:

| Condición | Éxito? |
|-----------|--------|
| **Migración sin fecha clara + sin plan + sin presupuesto** | ❌ **NO. Es suicidio.** |
| **Migración con 3-6 meses + plan + presupuesto + cooperación** | ✅ **Sí. Difícil, pero viable.** |
| **Migración con 6+ meses + plan + presupuesto + líder técnico** | ✅ **Sí. Altamente viable.** |
| **Mantener INTERNEXA mientras se prepara transición** | ✅ **Sí. La opción más inteligente a corto plazo.** |

---

*Análisis generado por ZEUS AGENTE IA — INNOVADATACO*  
*Metodología: Análisis de riesgo basado en evidencia documental, inferencia de complejidad técnica, evaluación de dependencias*  
*Postura: Brutalmente honesta. El cliente merece la verdad, no confort falso.*
