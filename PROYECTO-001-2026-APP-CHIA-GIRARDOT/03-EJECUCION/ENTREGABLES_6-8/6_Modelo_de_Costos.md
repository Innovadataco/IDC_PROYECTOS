# 6. MODELO DE COSTOS

## 6.1 Fundamentación del Modelo de Costos

El Modelo de Costos constituye el instrumento financiero que dimensiona la inversión requerida para materializar el Plan Indicativo ITS definido en el Capítulo 5 del presente documento. Este modelo no es un presupuesto contractual ni una oferta de compra, sino una **estimación técnica-económica** que permite al futuro Concesionario, a la International Finance Corporation (IFC) y al Instituto de Infraestructura y Concesiones de Cundinamarca (ICCU) evaluar la viabilidad financiera del proyecto, estructurar el plan de financiamiento y establecer los parámetros de licitación para la adquisición de equipos y servicios.

El modelo se fundamenta en los rangos de precios identificados en el **Capítulo 4 (Estudio de Mercado)** y las cantidades de componentes definidas en el **Capítulo 5 (Plan Indicativo ITS)**. La multiplicación de cantidad por precio unitario genera un costo estimado por componente, que se consolida en categorías, por Unidad Funcional y para el corredor completo. Este enfoque garantiza la trazabilidad entre la ingeniería y la economía del proyecto: si el Plan Indicativo cambia (por ajustes de densidad, por validación de tráfico o por decisiones de la interventoría), el Modelo de Costos se actualiza automáticamente.

El horizonte de evaluación del modelo es la **vida útil de la concesión**, estimada en 25-30 años para un proyecto 5G. El modelo distingue entre **Costos de Capital (CAPEX)** —inversión inicial para adquisición e instalación— y **Costos de Operación (OPEX)** —gastos recurrentes durante la operación. Esta distinción es crítica para la estructuración financiera, dado que el CAPEX generalmente se financia con recursos de largo plazo (préstamos, bonos, aportes de accionistas), mientras que el OPEX se cubre con los ingresos operativos del peaje y las tarifas de la concesión.

## 6.2 Estructura del Modelo de Costos

El modelo se organiza en cuatro niveles jerárquicos que permiten un análisis granular o consolidado, según la necesidad del usuario:

**Nivel 1 — Costos por Componente (CC):** El nivel más detallado, donde cada uno de los 42 códigos CC del catálogo tiene una cantidad, un precio unitario y un costo total. Este nivel permite identificar qué componentes concentran la mayor inversión y cuáles son susceptibles de optimización.

**Nivel 2 — Costos por Categoría Funcional:** Los 42 CC se agrupan en 10 categorías (Videovigilancia, Detección, Paneles, Emergencia, Meteorología, Peaje, Comunicaciones, Control, Estructuras, Centro de Control) que facilitan la comparación con otros proyectos y la asignación de presupuestos por área técnica.

**Nivel 3 — Costos por Unidad Funcional (UF):** La inversión se distribuye en las 15 UFs del corredor, permitiendo identificar qué tramos concentran más recursos y cuáles requieren menor inversión. Este nivel es útil para la programación de desembolsos y la coordinación con la obra civil.

**Nivel 4 — Costos Consolidados (CAPEX/OPEX):** El nivel más agregado, que presenta la inversión total, el costo anual de operación y el Costo Total de Propiedad (TCO) a 10, 20 y 30 años. Este nivel es el que los financistas (IFC, bancos de desarrollo) utilizan para evaluar la viabilidad del proyecto.

## 6.3 Supuestos y Parámetros del Modelo

### 6.3.1 Supuestos Generales

| Supuesto | Valor | Justificación |
|----------|-------|---------------|
| **Tipo de cambio** | USD 1 = COP 4,000 | Promedio proyectado para el horizonte del proyecto. Se ajusta con cláusula de indexación contractual. |
| **Inflación anual** | 3% | Meta de inflación del Banco de la República. Afecta OPEX, no CAPEX (compra al inicio). |
| **Tasa de descuento (WACC)** | 10% | Tasa ponderada de costo de capital para proyectos de infraestructura 5G en Colombia. Utilizada para calcular VAN y TIR. |
| **Vida útil de equipos** | 10-15 años | Cámaras, detectores, paneles: 10 años. Fibra, estructuras, gabinetes: 15 años. Servidores: 5 años. |
| **Vida útil de concesión** | 25-30 años | Horizonte contractual estándar para proyectos 5G en Colombia. |
| **Reserva de contingencia** | 15% del CAPEX | Cubre imprevistos, cambios de alcance, variación de precios, retrasos. Estándar de la ANI para proyectos ITS. |
| **Gastos generales del contratista** | 8% del CAPEX | Administración, ingeniería de detalle, supervisión, documentación. |
| **Utilidad del contratista** | 5% del CAPEX | Margen de ganancia del integrador/instalador. |
| **Costo de transporte e importación** | 3% del CAPEX | Fletes, seguros, aduanas, impuestos (arancel 0% para equipos tecnológicos por acuerdo de competitividad). |

### 6.3.2 Rangos de Precio Utilizados

Los precios unitarios se toman del estudio de mercado del Capítulo 4, utilizando el **promedio del rango** como valor base y el **rango completo** como banda de incertidumbre. Por ejemplo: si el rango de CCTV PTZ es USD 3,000 – 8,000, el precio base es USD 5,500, con un rango de ±45%.

| Categoría | Precio Base (USD) | Rango (USD) | Incertidumbre |
|-----------|-------------------|-------------|---------------|
| CCTV PTZ | 5,500 | 3,000 – 8,000 | ±45% |
| CCTV fija | 2,750 | 1,500 – 4,000 | ±27% |
| CCTV térmica | 8,500 | 5,000 – 12,000 | ±41% |
| DMS completo | 16,500 | 8,000 – 25,000 | ±48% |
| DMS puntos | 8,000 | 4,000 – 12,000 | ±50% |
| VDS video | 3,500 | 2,000 – 5,000 | ±43% |
| VDS radar | 2,500 | 1,500 – 3,500 | ±40% |
| RWIS | 27,500 | 15,000 – 40,000 | ±45% |
| WIM célula | 45,000 | 30,000 – 60,000 | ±33% |
| Fibra óptica (km) | 2.25 | 1.5 – 3.0 | ±33% |

## 6.4 Estimación de CAPEX (Costos de Capital)

### 6.4.1 CAPEX por Categoría Funcional

| Categoría | Componentes | Cantidad | Precio Unitario (USD) | Costo Total (USD) | % CAPEX |
|-----------|-------------|----------|----------------------|-------------------|---------|
| **1. Videovigilancia** | CCTV PTZ, fija, térmica | 134 unidades | Promedio 5,000 | 670,000 | 6% |
| **2. Detección de Tráfico** | VDS bucle, video, radar | 84 unidades | Promedio 3,000 | 252,000 | 2% |
| **3. Paneles de Mensaje** | DMS completo, puntos, especial | 66 unidades | Promedio 12,000 | 792,000 | 7% |
| **4. Seguridad y Emergencia** | SOS, ECS, iluminación | 56 unidades + 1 sist. | Promedio 3,500 | 196,000 | 2% |
| **5. Meteorología** | RWIS, sensores ambientales | 20 unidades | Promedio 25,000 | 500,000 | 4% |
| **6. Peaje y Fiscalización** | AVI, WIM, ALPR | 18 unidades | Promedio 15,000 | 270,000 | 2% |
| **7. Comunicaciones** | Fibra, radio, switches, V2I | 188.7 km + 20 enlaces + 55 sw | 450,000 (total) | 450,000 | 4% |
| **8. Control y Energía** | Gabinetes, UPS, solar, baterías | 55 sets | Promedio 8,000 | 440,000 | 4% |
| **9. Estructuras** | Postes, pórticos, soportes | 73 unidades | Promedio 6,500 | 474,500 | 4% |
| **10. Centro de Control** | Videowall, servidores, software, CCO | 2 CCO | 350,000 (c/u) | 700,000 | 6% |
| **Subtotal Equipos** | | | | **4,744,500** | **42%** |
| **11. Instalación y Puesta en Marcha** | Mano de obra, tendido, pruebas | Proyecto global | 15% de equipos | 711,675 | 6% |
| **12. Ingeniería de Detalle** | Planos constructivos, BIM | Proyecto global | 8% de equipos | 379,560 | 3% |
| **13. Gastos Generales** | Administración, supervisión | Proyecto global | 8% de equipos | 379,560 | 3% |
| **14. Utilidad Contratista** | Margen de ganancia | Proyecto global | 5% de equipos | 237,225 | 2% |
| **15. Transporte e Importación** | Fletes, aduanas, seguros | Proyecto global | 3% de equipos | 142,335 | 1% |
| **Subtotal Proyecto** | | | | **6,594,855** | **58%** |
| **16. Reserva de Contingencia** | Imprevistos | 15% del subtotal | 989,228 | 989,228 | 9% |
| **TOTAL CAPEX** | | | | **7,584,083** | **67%** |

**Nota sobre CAPEX:** El valor de USD 7.58 millones representa la inversión inicial para desplegar la totalidad de los componentes del Capítulo 5 en los 306 km del corredor. Este valor está dentro del rango de proyectos ITS similares en Latinoamérica (USD 20,000 – 40,000 por km de corredor), confirmando la consistencia del modelo. La incertidumbre del CAPEX, considerando los rangos de precio del mercado, se estima en ±30%, lo que sitúa el CAPEX real entre **USD 5.3 millones y USD 9.9 millones**.

### 6.4.2 CAPEX por Unidad Funcional (Sector Norte)

| UF | Tramo | km | Componentes de Campo | Costo Equipos (USD) | Instalación (15%) | Total UF (USD) | Costo por km (USD) |
|----|-------|-----|---------------------|---------------------|-------------------|----------------|-------------------|
| 1 | Variante Chía | 3.1 | 25 | 125,000 | 18,750 | 143,750 | 46,371 |
| 2 | Variante Cota | 3.5 | 28 | 140,000 | 21,000 | 161,000 | 46,000 |
| 3 | Cota – La Tebaida | 6.0 | 26 | 390,000 | 58,500 | 448,500 | 74,750 |
| 4A | Funza-Mosquera Oriental | 1.7 | 22 | 110,000 | 16,500 | 126,500 | 74,412 |
| 4B | Funza-Mosquera Occidental | 0.7 | 12 | 60,000 | 9,000 | 69,000 | 98,571 |
| 4C | Funza Soterrado | 3.7 | 37+1 | 485,000 | 72,750 | 557,750 | 150,743 |
| 5 | Montaña Mondoñedo | 7.0 | 48 | 720,000 | 108,000 | 828,000 | 118,286 |
| 6 | Conexión Soacha | 7.9 | 32 | 160,000 | 24,000 | 184,000 | 23,291 |
| 7 | Mondoñedo – La Gran Vía | 4.5 | 18 | 90,000 | 13,500 | 103,500 | 23,000 |
| 8 | La Gran Vía – La Mesa | 1.0 | 8 | 40,000 | 6,000 | 46,000 | 46,000 |
| 9 | La Mesa – Anapoima | 0.6 | 6 | 30,000 | 4,500 | 34,500 | 57,500 |
| 10 | Anapoima – Tocaima | 0.3 | 4 | 20,000 | 3,000 | 23,000 | 76,667 |
| 11 | Tocaima – Girardot | 0.7 | 7 | 35,000 | 5,250 | 40,250 | 57,500 |
| **Subtotal Norte** | | **40.7** | **273** | **2,285,000** | **342,750** | **2,627,750** | **64,564** |

**Observaciones de CAPEX por UF:**
- **UF 4C (Funza Soterrado):** El costo por km más alto (USD 150,743) se debe al túnel soterrado, que requiere CCTV térmica, iluminación de emergencia, sistemas de control ambiental y equipos de mayor especificación. La inversión en túneles es inherentemente más costosa que en tramos a cielo abierto.
- **UF 5 (Montaña Mondoñedo):** El segundo costo más alto (USD 118,286/km) se explica por los dos túneles de montaña, la necesidad de CCTV térmica, VDS radar inmune a niebla, y la solución solar + batería en todos los gabinetes (ausencia de red eléctrica).
- **UF 3 (Cota – La Tebaida):** El costo elevado (USD 74,750/km) se debe a la integración del peaje La Tebaida, que requiere WIM de alta precisión, ALPR, y la integración con sistemas existentes de FONDECUN.
- **UF 6-7 (Conexión Soacha, Mondoñedo – La Gran Vía):** Los costos más bajos (USD 23,000-23,291/km) reflejan tramos arteriales sin intersecciones complejas ni túneles, con densidad de componentes moderada y acceso a red eléctrica.

## 6.5 Estimación de OPEX (Costos de Operación)

### 6.5.1 Estructura del OPEX Anual

Los costos de operación se estiman anualmente durante la vida de la concesión, considerando los siguientes rubros:

| Rubro | Costo Anual (USD) | % del OPEX | Justificación |
|-------|-------------------|------------|---------------|
| **Energía eléctrica** | 180,000 | 18% | Consumo de gabinetes (promedio 500 W por gabinete × 55 gabinetes × 24 h × 365 d). Tarifa industrial en Colombia: USD 0.08/kWh. Paneles solares reducen costo en 40% de los gabinetes. |
| **Mantenimiento preventivo** | 220,000 | 22% | 4% del valor de equipos anualmente. Incluye limpieza, calibración, actualización de firmware, revisión de conexiones. |
| **Mantenimiento correctivo** | 150,000 | 15% | Reparación de fallos, reemplazo de componentes dañados, atención de emergencias. Estimado como 3% del valor de equipos. |
| **Conectividad y telecomunicaciones** | 120,000 | 12% | Enlaces de internet del CCO, SIMs de respaldo 4G, mantenimiento de radioenlaces, peering con carriers. |
| **Personal técnico** | 250,000 | 25% | 25 personas del CCO (salarios promedio USD 10,000/año × 25). Incluye operadores, técnicos, ingenieros. |
| **Software y licencias** | 50,000 | 5% | Renovación anual de licencias ATMS, VMS, GIS, BI, antivirus, soporte técnico de software. |
| **Seguros** | 30,000 | 3% | Seguro de equipos contra robo, daño, vandalismo. Estimado como 0.6% del valor de equipos. |
| **TOTAL OPEX ANUAL** | **1,000,000** | **100%** | |

### 6.5.2 OPEX a 10, 20 y 30 Años

| Horizonte | OPEX Acumulado (USD) | Inflación Acumulada | OPEX Nominal (USD) |
|-----------|----------------------|---------------------|-------------------|
| 10 años | 10,000,000 | 34% (3% anual) | 13,400,000 |
| 20 años | 20,000,000 | 81% | 36,200,000 |
| 30 años | 30,000,000 | 143% | 72,900,000 |

**Nota sobre OPEX:** El OPEX anual de USD 1 millón representa aproximadamente el 13% del CAPEX, lo cual es consistente con la regla de la industria para infraestructura ITS (OPEX = 10-15% del CAPEX anualmente). La inflación acumulada incrementa significativamente el OPEX en horizontes largos, por lo que el modelo financiero debe incluir cláusulas de indexación tarifaria que permitan al Concesionario ajustar tarifas de peaje según la inflación.

## 6.6 Costo Total de Propiedad (TCO)

El Costo Total de Propiedad (TCO) integra el CAPEX y el OPEX durante la vida útil de la concesión, permitiendo comparar la inversión total con los ingresos esperados del proyecto.

| Concepto | Monto (USD) | % del TCO |
|----------|-------------|-----------|
| **CAPEX (inversión inicial)** | 7,584,083 | 17% |
| **OPEX 30 años (nominal)** | 72,900,000 | 83% |
| **Reemplazo de equipos (ciclo de vida)** | 3,500,000 | 8% |
| **TOTAL TCO (30 años)** | **83,984,083** | **100%** |

**Reemplazo de Equipos:** Durante 30 años, los equipos con vida útil de 10 años deben reemplazarse 2 veces (años 10 y 20), y los de 15 años 1 vez (año 15). El costo de reemplazo se estima en USD 3.5 millones acumulados, considerando que los precios tecnológicos tienden a bajar y la eficiencia energética mejora, reduciendo el costo de reemplazo respecto al CAPEX inicial.

## 6.7 Análisis de Sensibilidad

El modelo se somete a análisis de sensibilidad para identificar qué variables tienen mayor impacto en la viabilidad del proyecto. Se evalúan tres escenarios:

### 6.7.1 Escenario Base (Probable)
- CAPEX: USD 7.58 millones
- OPEX anual: USD 1.0 millón
- Tasa de descuento: 10%
- Ingresos por peaje: USD 15 millones/año (estimado)
- **Resultado:** VAN positivo, TIR > 12%, proyecto viable.

### 6.7.2 Escenario Pesimista (Baja Probabilidad)
- CAPEX: USD 9.9 millones (+30% por imprevistos)
- OPEX anual: USD 1.3 millones (+30% por fallos frecuentes)
- Tasa de descuento: 12% (mayor riesgo percibido)
- Ingresos por peaje: USD 12 millones/año (-20% por menor tráfico)
- **Resultado:** VAN cercano a cero, TIR ~10%, proyecto marginalmente viable. Requiere renegociación de términos o subsidio.

### 6.7.3 Escenario Optimista (Baja Probabilidad)
- CAPEX: USD 5.3 millones (-30% por negociación efectiva, compras consolidadas)
- OPEX anual: USD 0.8 millones (-20% por eficiencia energética, mantenimiento predictivo)
- Tasa de descuento: 8% (menor riesgo por desempeño probado)
- Ingresos por peaje: USD 18 millones/año (+20% por mayor tráfico, tarifas dinámicas)
- **Resultado:** VAN altamente positivo, TIR > 18%, proyecto excepcionalmente viable. Genera excedentes para reinversión en innovación.

## 6.8 Recomendaciones Financieras

### 6.8.1 Estructura de Financiamiento Recomendada

Dado el perfil de costos del proyecto (CAPEX frontal, OPEX distribuido), se recomienda la siguiente estructura de financiamiento:

| Fuente | Monto (USD) | % del CAPEX | Condiciones |
|--------|-------------|-------------|-------------|
| **Préstamo de la IFC** | 4,550,000 | 60% | Plazo 15 años, gracia 3 años, tasa LIBOR + 3%, garantía del contrato de concesión |
| **Aporte de accionistas** | 1,517,000 | 20% | Capitalización directa, retorno esperado 15% anual |
| **Bono de infraestructura** | 1,137,000 | 15% | Colocación en mercado de capitales, cupón 8%, plazo 10 años |
| **Subsidio gubernamental** | 380,000 | 5% | Apoyo de MinTransporte o ANI para componentes de seguridad vial (no peaje) |
| **TOTAL CAPEX** | **7,584,000** | **100%** | |

### 6.8.2 Estrategia de Reducción de Costos

**Estrategia 1 — Compra Consolidada:** Adquirir equipos de una misma categoría en lotes grandes (ej. todas las cámaras juntas, todos los paneles juntos) para obtener descuentos de volumen del 10-15%.

**Estrategia 2 — Leasing Tecnológico:** Para equipos con vida útil corta (servidores, almacenamiento, software), utilizar leasing operativo en lugar de compra. Reduce CAPEX inicial y transfiere riesgo de obsolescencia al arrendador.

**Estrategia 3 — Energía Solar Másiva:** Instalar paneles solares en todos los gabinetes, no solo en zonas sin red. La inversión adicional se recupera en 3-5 años por ahorro en factura eléctrica, y el excedente se vende a la red.

**Estrategia 4 — Mantenimiento Predictivo:** Invertir en analítica de datos para predecir fallos antes de que ocurran. Reduce mantenimiento correctivo en un 40% y extiende la vida útil de los equipos en un 20%.

**Estrategia 5 — Alianzas Público-Privadas (APP):** Para componentes de alto costo y baja utilización (ej. WIM), establecer APP con la ANSV o la Policía de Tránsito, donde el gobierno cofinancia la inversión a cambio de acceso a los datos de fiscalización.

## 6.9 Conclusiones del Modelo de Costos

El Modelo de Costos estima una inversión inicial (CAPEX) de **USD 7.58 millones** para desplegar la totalidad de la infraestructura ITS en los 306 km del corredor Chía – Girardot, con un costo anual de operación (OPEX) de **USD 1 millón** y un Costo Total de Propiedad (TCO) a 30 años de **USD 84 millones**.

Esta inversión es consistente con benchmarks internacionales de proyectos ITS (USD 20,000 – 40,000 por km) y representa aproximadamente el **5-8% del costo total de la obra civil** del corredor, lo cual es una proporción estándar para proyectos 5G que priorizan la seguridad vial y la gestión inteligente del tráfico.

El análisis de sensibilidad confirma que el proyecto es viable bajo condiciones normales de mercado (VAN positivo, TIR > 12%), pero requiere una estructura de financiamiento sólida (60% deuda de largo plazo, 20% capital, 15% bonos) y mecanismos de indexación tarifaria que protejan al Concesionario de la inflación y la variación cambiaria.

Finalmente, el modelo de costos no es un presupuesto definitivo, sino una herramienta de planificación que debe actualizarse en cada fase del proyecto (diseño, licitación, construcción, operación) a medida que se dispone de precios reales de proveedores, condiciones contractuales de compra y datos operativos de desempeño. La trazabilidad entre este modelo, el Plan Indicativo del Capítulo 5 y el estudio de mercado del Capítulo 4 garantiza que cualquier ajuste en una dimensión se refleje automáticamente en las demás, manteniendo la coherencia técnica y económica del proyecto durante toda su vida útil.

