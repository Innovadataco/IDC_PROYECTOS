# DEFINICIÓN DE EQUIPOS ITS — TRAMO 1
## Variante Chía – Glorieta Norte | 7.134 km | 2 subtramos

**Proyecto:** APP-CHIA-GIRARDOT  
**Código:** PROYECTO-001-2026-APP-CHIA-GIRARDOT  
**Entregable:** E5-Diseños-ITS / Tramo-01  
**Fecha:** 2026-06-02  
**Versión:** 1.0 — Definición para validación  
**Elabora:** ZEUS — InnovaDataCo

---

## 1. FICHA RÁPIDA DEL TRAMO

| Dato | Valor |
|------|-------|
| Código | T-01 |
| Nombre | Variante Chía – Glorieta Norte |
| Longitud | 7.134 km |
| Subtramos | 2 |
| Tipo de vía | Variante rápida periurbana |
| Velocidad diseño | 80 km/h |
| Topografía | Plana (Altiplano Cundiboyacense) |
| Elementos | 2 glorietas, 0 túneles, 0 peajes, 0 puentes mayores |

---

## 2. SUBTRAMOS

### T-01-S01 — Variante Chía (3.086 km)
De Av. Pradilla a Glorieta Av. Chilacos. Vía de variante que evita el tráfico urbano de Chía. Periurbana, zona residencial en expansión. 1 glorieta al final.

### T-01-S02 — Conexión Chía-Cota (4.048 km)
De Glorieta Av. Chilacos a Glorieta Norte Cota. Continuación de la variante. Transición Chía-Cota. 1 glorieta al final.

---

## 3. EQUIPOS ITS DEFINIDOS PARA ESTE TRAMO

**15 componentes de campo aplican.** Tabla consolidada:

| CC | Equipo | Cantidad | ¿Dónde va? | Función |
|----|--------|----------|------------|---------|
| **CC-01** | CCTV | 6 cámaras | 3 por subtramo: entrada, intermedio, glorieta | Ver lo que pasa en la vía |
| **CC-02** | AID | 2 sistemas | 1 por subtramo en punto crítico | Detectar incidentes sin que el operador esté viendo pantallas |
| **CC-03** | DMS/VMS | 1 panel | Entrada desde Av. Pradilla | Informar al conductor antes de entrar |
| **CC-04** | ECS/SOS | 4 columnas | 2 por subtramo, cada ~2 km | Que el usuario pueda pedir ayuda si algo le pasa |
| **CC-05** | VDS/TDS | 4 sensores | 2 por subtramo, por sentido | Saber cuántos carros pasan y a qué velocidad |
| **CC-06** | ESS/RWIS | 1 estación | Punto medio del tramo (km ~3.5) | Medir temperatura, lluvia, visibilidad. **Pendiente:** ¿se justifica en Chía? |
| **CC-13** | SPD | 1 radar | Entrada a la variante (km 0.5) | Mostrarle al conductor su velocidad para que frene solo |
| **CC-14** | VSL | 2 señales | 1 por subtramo en la entrada | Cambiar el límite de velocidad desde el centro de control |
| **CC-20** | VIS/LGS | Variable | Todo el tramo si no hay alumbrado | Que haya luz donde están los equipos y el conductor vea. **Pendiente:** ¿ya hay alumbrado público? |
| **CC-23** | FOC | 7.1 km | Tendido continuo por todo el tramo | La fibra que lleva datos de todos los equipos al centro de control |
| **CC-24** | RCS | 2 radios | 1 en cada nodo de comunicación | Si se corta la fibra, que el radio mantenga la comunicación |
| **CC-33** | LCS/SIG | 8 señales | 4 por cada glorieta (2 glorietas) | Semáforos o flechas que organizen el flujo en las glorietas |
| **CC-34** | PSS | ~50 postes | Cada 100–200 m según equipos | Los postes que sostienen cámaras, paneles, antenas |
| **CC-35** | UPS/EPS | 2 gabinetes | 1 en cada nodo de comunicación | Que los equipos no se apaguen cuando se va la luz |
| **CC-41** | E-LOG | 1 sistema | Centro de control regional (compartido con otros tramos) | Organizar grúas, ambulancias, camiones de mantenimiento |

---

## 4. DISTRIBUCIÓN POR SUBTRAMO

### T-01-S01 — Variante Chía (3.086 km)

| Equipo | Cantidad | Ubicación exacta (km) | Nota |
|--------|----------|----------------------|------|
| CCTV | 3 | 0.5 (Av. Pradilla), 1.5, 2.8 (Glorieta Av. Chilacos) | 2 PTZ + 1 fija |
| AID | 1 | 1.5 | Integrado con CCTV-02 |
| DMS/VMS | 1 | 0.3 | Antes de entrar a la variante |
| ECS/SOS | 2 | 1.0, 2.5 | Alternados por sentido |
| VDS/TDS | 2 | 0.5, 2.8 | Por sentido |
| SPD | 1 | 0.5 | Junto a la entrada |
| VSL | 1 | 0.3 | Al inicio de la variante |
| LCS/SIG | 4 | 2.8 | Glorieta Av. Chilacos |
| ESS/RWIS | 1 | 1.5 | Si se confirma necesidad |
| VIS/LGS | Variable | Todo el subtramo | Si no hay alumbrado existente |
| FOC | 3.1 km | Todo el subtramo | Hasta el Nodo S-01 |
| UPS/EPS | 1 | 2.8 | Gabinete en glorieta Av. Chilacos |
| PSS | ~22 | Cada 140 m aprox. | Postes de soporte |

### T-01-S02 — Conexión Chía-Cota (4.048 km)

| Equipo | Cantidad | Ubicación exacta (km) | Nota |
|--------|----------|----------------------|------|
| CCTV | 3 | 3.5, 5.5, 7.0 (Glorieta Norte Cota) | 1 fija + 2 PTZ |
| AID | 1 | 5.5 | Punto intermedio |
| ECS/SOS | 2 | 4.0, 6.5 | Alternados por sentido |
| VDS/TDS | 2 | 3.5, 7.0 | Por sentido |
| VSL | 1 | 3.5 | Al inicio del subtramo |
| LCS/SIG | 4 | 7.0 | Glorieta Norte Cota |
| FOC | 4.0 km | Todo el subtramo | Desde Nodo S-01 hasta S-02 |
| UPS/EPS | 1 | 7.0 | Gabinete en glorieta Norte Cota |
| PSS | ~28 | Cada 140 m aprox. | Postes de soporte |

---

## 5. RED DE COMUNICACIONES

**Dos nodos, fibra óptica principal, radio como respaldo.**

| Nodo | Ubicación | Equipos que conecta | Salida hacia |
|------|-----------|---------------------|--------------|
| **S-01** | Glorieta Av. Chilacos (km 3.086) | Todo T-01-S01 | S-02 + Centro de Control |
| **S-02** | Glorieta Norte Cota (km 7.134) | Todo T-01-S02 | Tramo 2 + Centro de Control |

| Medio | Función | Tendido |
|-------|---------|---------|
| **FOC** | Transportar datos (video, conteos, alarmas) | 7.1 km, fibra monomodo 12 fibras |
| **RCS** | Respaldo si se corta la fibra | 2 radios, cobertura por zona |

**Nota:** ¿Tendido aéreo o subterráneo? Pendiente definir con el diseño vial y derechos de vía.

---

## 6. PENDIENTES PARA DEFINIR

| # | Pregunta | Quién responde | Impacto |
|---|----------|---------------|---------|
| 1 | ¿La variante ya tiene alumbrado público? | Diseño vial / IDU | Si sí, no va VIS/LGS. Si no, hay que ponerlo. |
| 2 | ¿Se necesita estación meteorológica en Chía? | Validación técnica | Si no, se quita CC-06. Chía tiene clima estable. |
| 3 | ¿La vía es bidireccional con entradas separadas? | Plano geométrico | Si sí, DMS/VMS necesita 2 paneles (uno por sentido). |
| 4 | ¿Las glorietas son circulares tradicionales o semaforizadas? | Plano de intersección | Si son circulares sin semáforos, LCS/SIG puede no aplicar. |
| 5 | ¿Qué densidad de cámaras pide la norma? | ANSV / IDU | Estándar: ¿cada 500 m, 1 km o 2 km? |
| 6 | ¿FOC aéreo o enterrado? | Contrato de obra / IDU | Afecta costo y permisos. |

---

## 7. NOTA TÉCNICA

Se revisó la carpeta de diseños del corredor en Drive. Los archivos de cantidades existentes ("Canditades") solo contienen obra civil: señalización, delineadores, tachas, barreras, defensas. **No contienen equipos ITS.** Por eso, este documento define la propuesta de equipos ITS para el Tramo 1 basándose en la infraestructura real del tramo (variante rápida, 2 glorietas, sin túneles, sin peajes) y en estándares de diseño ITS. Las cantidades son propuesta para que el equipo de diseño valide y ajuste.

---

*Documento práctico de definición. Sin justificaciones de lo que no se usa.  
ZEUS — InnovaDataCo. 2026-06-02*
