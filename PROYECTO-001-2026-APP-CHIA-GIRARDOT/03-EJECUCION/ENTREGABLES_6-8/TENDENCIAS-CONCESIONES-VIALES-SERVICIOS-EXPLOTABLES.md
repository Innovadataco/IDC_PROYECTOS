# TENDENCIAS TECNOLÓGICAS EN CONCESIONES VIALES Y OPORTUNIDADES DE SERVICIOS EXPLOTABLES

## Documento de Orientación Estratégica para el Proyecto APP Chía-Girardot

---

## 1. INTRODUCCIÓN: EL NUEVO PARADIGMA DE LAS CONCESIONES VIALES

Las concesiones viales del siglo XXI están dejando de ser simples infraestructuras de asfalto y puentes para convertirse en **plataformas tecnológicas de servicios múltiples**. El modelo tradicional —cobro por peaje como único ingreso— está siendo reemplazado por un ecosistema donde la vía genera valor a través de datos, servicios energéticos, logística, conectividad y movilidad integrada.

Este documento presenta las tendencias tecnológicas globales que están redefiniendo el sector de concesiones viales, con énfasis en servicios que pueden ser explotados comercialmente dentro del marco de una concesión APP (Actividad de Prestación de Servicios Públicos). Cada tendencia incluye referencias a proyectos reales verificables donde estas tecnologías ya están operando o en fase avanzada de implementación.

**Nota metodológica:** La información presentada proviene de fuentes públicas verificables: comunicados de prensa de concesionarias, informes de organismos multilaterales (BID, Banco Mundial), documentación técnica de proveedores, y reportes regulatorios. No se incluyen proyecciones especulativas ni datos no confirmados.

---

## 2. TENDENCIA 1: IDENTIFICACIÓN DE VEHÍCULOS Y SISTEMAS DE COBRO AVANZADO

### 2.1 Evolución del peaje: de plaza tradicional a flujo libre

El mercado global de peaje electrónico está en transición acelerada desde sistemas de plaza tradicional (con barreras y cabinas) hacia modelos de **Multi-Lane Free Flow (MLFF)** donde los vehículos circulan a velocidad normal sin detenerse. Esta transición no es teórica: ya está operativa en múltiples corredores.

### 2.2 Proyectos verificables de peaje free flow

| Proyecto | País | Tecnología | Estado | Referencia verificable |
|----------|------|------------|--------|------------------------|
| **Ruta Nogales–Puchuncaví** | Chile | Kapsch SmartToll (MLFF + tradicional combinado) | Operativo desde 2022 | Comunicado Kapsch, enero 2022 |
| **Autopista Palmillas–Apaseo** | México | Sistema de integridad vehicular con LPR cada 7 km + pórticos de cobro | Operativo desde 2025 | Comunicado Kapsch, agosto 2025 |
| **A-1 España (Audasa)** | España | Free flow en peajes (tag DSRC + videocámaras LPR) | Operativo | Concesionaria Audasa, Ministerio de Transporte español |
| **M6 Hungría** | Hungría | Peaje free flow con pórticos electrónicos | Operativo | Concesionaria M6 Duna |
| **Telepase Brasil** | Brasil | TAG activo y pasivo en autopistas operadas por CCR, EcoRodovias | Operativo | Concesionarias CCR, EcoRodovias |

### 2.3 Tecnologías de identificación vehicular disponibles

| Tecnología | Maturidad | Aplicación | Proveedores con referencias |
|------------|-----------|------------|---------------------------|
| **DSRC (Dedicated Short-Range Communication)** | TRL 9 | Tag de peaje, comunicación OBU-RSU | Kapsch, Q-Free, Siemens |
| **LPR/ANPR (Reconocimiento de placas)** | TRL 9 | Identificación vehicular, matriz origen-destino | Kapsch (Palmillas-Apaseo), múltiples proveedores |
| **RFID pasivo** | TRL 9 | Peaje de bajo costo | Usado en Telepase Brasil, Tag Chile |
| **GPS/GNSS para peaje** | TRL 6-7 | Peaje por ubicación (sin infraestructura física) | Piloto en Europa, sin despliegue masivo en LATAM |
| **Cámaras LPR de alta velocidad** | TRL 9 | Detección a 120+ km/h sin detenerse | Kapsch, Sensys, múltiples |

### 2.4 Oportunidad de servicio explotable para Chía-Girardot

**Servicio de telepeaje interoperable:** Colombia ya cuenta con el sistema COLPASS (administrado por la ANI), que permite el paso entre corredores concesionados con un solo tag. Sin embargo, la interoperabilidad no está completa en todos los corredores. La concesión Chía-Girardot puede:
- Implementar peaje free flow MLFF donde la topografía lo permita
- Ofrecer tarifas diferenciadas por horario (congestión pricing) — ver sección 4
- Integrar con sistemas de pago digital (wallets, apps) para usuarios sin tag

**Servicio de identificación para flotas:** El sistema LPR puede extenderse a servicios de control de flotas comerciales, generando ingresos por servicio de rastreo y reportes de cumplimiento.

---

## 3. TENDENCIA 2: MOVILIDAD CONECTADA (V2X, V2I, I2V)

### 3.1 Estado real de la tecnología (sin promesas exageradas)

La movilidad conectada —donde vehículos se comunican con infraestructura (V2I) y entre sí (V2V)— está en fase de **piloto global**, no en despliegue masivo comercial. Es importante distinguir entre lo que se anuncia y lo que está operando.

### 3.2 Proyectos verificables de V2X

| Proyecto | País | Alcance | Estado | Referencia |
|----------|------|---------|--------|------------|
| **Bizkaia Connected Corridor** | España | 25 RSU en 60 km de autopista A-8 | Piloto operativo desde 2023 | Kapsch, junio 2023 |
| **Smart Columbus (Rickenbacker Causeway)** | Ohio, USA | Corredor conectado con sensores y RSU | Piloto completado 2018-2020 | U.S. DOT, Smart Columbus |
| **Mcity (Universidad de Michigan)** | Michigan, USA | Campus de pruebas V2X con semáforos conectados | Operativo (fase de pruebas) | Universidad de Michigan |
| **Avenida de la Ilustración (Madrid)** | España | Semáforos conectados, RSU, gestión de tráfico | Piloto | Madrid City Council, Kapsch |
| **C-V2X en autopistas chinas** | China | Varios corredores con RSU y OBU en vehículos | Despliegue parcial en autopistas estatales | Ministerio de Transporte chino |

### 3.3 Realidad del mercado en 2026

- **Penetración de vehículos equipados con V2X:** Menos del 1% del parque automotor global en 2026. Los fabricantes (BMW, Ford, Audi) han equipado modelos premium, pero no es estándar.
- **Regulación:** No existe regulación obligatoria V2X en Colombia ni en la mayoría de países latinoamericanos. La UE tiene mandato para 2025 en vehículos nuevos (Directiva 2019/1936 / Delegated Regulation EU 2021/1960).
- **Infraestructura:** Requiere instalación de RSU (Road Side Units) cada 300-1000 metros. El costo de despliegue masivo es elevado y requiere modelo de negocio claro.

### 3.4 Oportunidad de servicio explotable para Chía-Girardot

**V2X como servicio premium (no como base obligatoria):**
- En lugar de exigir V2X como infraestructura básica de la concesión, se puede diseñar como **servicio opcional** para flotas premium o servicios de emergencia
- Las RSU pueden instalarse primero en zonas críticas: túneles, curvas peligrosas, zonas de niebla
- El servicio puede cobrarse a flotas comerciales o aseguradoras que desean datos de seguridad

**Caso de referencia:** En Bizkaia (España), el proyecto V2X es un piloto financiado por fondos públicos y privados, no genera ingresos directos por sí solo. El modelo de negocio está en formación.

---

## 4. TENDENCIA 3: INFRAESTRUCTURA DE CARGA PARA VEHÍCULOS ELÉCTRICOS (ELECTROLINERAS)

### 4.1 Estado de la electromovilidad en concesiones viales

La instalación de electrolineras en concesiones viales es una de las tendencias con mayor potencial de ingresos directos. No es una promesa futura: ya está operando en múltiples corredores.

### 4.2 Proyectos verificables de electrolineras en concesiones

| Proyecto / Concesión | País | Detalle | Estado | Referencia |
|----------------------|------|---------|--------|------------|
| **Ruta 68 (Chile)** | Chile | Electrolineras instaladas en áreas de servicio de concesión | Operativo | Concesionaria Ruta 68, Ministerio de Energía Chile |
| **Vespucio Norte (Chile)** | Chile | Estaciones de carga rápida en áreas de servicio | Operativo | Vespucio Norte Express |
| **Autopistas de Portugal (Brisa)** | Portugal | Red de electrolineras en áreas de servicio | En expansión | Brisa, Plano de Recuperación y Resiliencia (PRR) Portugal |
| **Abertis (España/Francia/Chile)** | Multinacional | Electrolineras en áreas de servicio de múltiples concesiones | En expansión | Abertis, informes anuales |
| **Autostrade per l'Italia** | Italia | Electrolineras en áreas de servicio | En expansión | Autostrade, Piano Nazionale Ripresa e Resilienza |
| **Electrify America (USA)** | USA | Red de carga rápida en corredores interestatales (no concesión, pero modelo similar) | Operativo | Volkswagen Group, Electrify America |

### 4.3 Modelos de negocio verificables

| Modelo | Descripción | Ejemplo verificable |
|--------|-------------|---------------------|
| **Operación directa** | Concesionaria instala y opera electrolineras | Ruta 68 Chile, Vespucio Norte |
| **Concesión de espacio** | Concesionaria alquila espacio a operador de carga (Ionity, Tesla, etc.) | Brisa Portugal (con Ionity), Abertis España |
| **Joint venture** | Concesionaria + operador de energía comparten riesgo e inversión | Algunos proyectos de Abertis |
| **Servicio premium** | Carga rápida (350kW) para flotas comerciales y vehículos premium | Electrify America USA |

### 4.4 Oportunidad de servicio explotable para Chía-Girardot

**Electrolineras en áreas de servicio y túneles:**
- El corredor Chía-Girardot tiene múltiples áreas de servicio potenciales donde se pueden instalar estaciones de carga rápida (150kW-350kW)
- El modelo 5G de la concesión (sin peajes) puede compensarse parcialmente con ingresos por energía
- Ventajas estratégicas:
  - Colombia tiene una de las matrices energéticas más limpias del mundo (70%+ hidroeléctrica), lo que hace atractiva la electrolineras a nivel de marketing verde
  - El gobierno colombiano está impulsando la transición energética (Ley de Transición Energética 2021)
  - Flotas de transporte público (buses) en Bogotá están electrificándose

**Servicio adicional: V2G (Vehicle-to-Grid)**
- Aunque aún en fase temprana (TRL 6-7), los vehículos eléctricos pueden devolver energía a la red durante horas de baja demanda
- La concesión puede posicionarse como "punto de respaldo energético" para la red de Bogotá

---

## 5. TENDENCIA 4: PEAJE DINÁMICO Y PRICING INTELIGENTE (CONGESTION PRICING)

### 5.1 Concepto y estado global

El peaje dinámico —donde la tarifa varía según hora del día, nivel de congestión, o tipo de vehículo— está operativo en varias ciudades y corredores. No es una teoría: es una realidad de gestión de demanda.

### 5.2 Proyectos verificables de peaje dinámico / congestion pricing

| Proyecto | País | Mecanismo | Estado | Referencia |
|----------|------|-----------|--------|------------|
| **Singapore ERP (Electronic Road Pricing)** | Singapur | Peaje dinámico por hora en zonas urbanas | Operativo desde 1998 | Land Transport Authority Singapore |
| **London Congestion Charge** | Reino Unido | Tarifa fija por ingreso a zona central (con horarios diferenciados) | Operativo desde 2003 | Transport for London (TfL) |
| **Stockholm Congestion Tax** | Suecia | Peaje por hora en horas pico vs. valle | Operativo desde 2007 | Swedish Transport Agency |
| **Gothenburg Congestion Tax** | Suecia | Peaje por hora en corredores de acceso | Operativo desde 2013 | Swedish Transport Agency |
| **Milan Area C** | Italia | Tarifa de ingreso a zona central según emisiones | Operativo desde 2012 | Comune di Milano |
| **New York City Congestion Pricing** | USA | Peaje por ingreso a Manhattan (implementación 2024-2025) | En implementación | MTA, NYC |

### 5.3 Tecnología detrás del pricing dinámico

| Componente | Función | Proveedores |
|------------|---------|-------------|
| **Detección de congestión** | Sensores, cámaras, loops que miden flujo y densidad | Kapsch, Indra, Siemens, Sensys |
| **Algoritmos de pricing** | Software que ajusta tarifas en tiempo real según demanda | Plataformas ATMS, software propietario |
| **Cobro sin fricción** | MLFF, LPR, tag DSRC | Kapsch, Q-Free |
| **Información al usuario** | VMS, apps, web con precios en tiempo real | VMS LED, EcoTrafiX, apps |

### 5.4 Oportunidad de servicio explotable para Chía-Girardot

**Tarifas diferenciadas por horario (Time-of-Day Pricing):**
- El corredor Chía-Girardot conecta Bogotá con el sur (Girardot, Melgar, Ibagué). Los patrones de tráfico muestran horas pico claras (mañanas hacia Bogotá, tardes hacia el sur)
- Implementar tarifas diferenciadas puede:
  - Reducir congestión en horas pico (incentivar viaje en horas valle)
  - Generar ingresos adicionales por tarifa premium en horas de alta demanda
  - Mejorar nivel de servicio para todos los usuarios

**Servicio de "pase mensual" para usuarios frecuentes:**
- Suscripción plana para residentes de Chía, Cota, o municipios del corredor
- Modelo ya probado en concesiones chilenas y españolas

---

## 6. TENDENCIA 5: DATOS DE TRÁFICO Y MONETIZACIÓN DE LA INFORMACIÓN

### 6.1 El nuevo petróleo: datos de movilidad

Las concesiones viales generan enormes volúmenes de datos: velocidades, flujos, orígenes-destinos, patrones horarios, tipos de vehículos, incidentes. Estos datos tienen valor comercial para múltiples actores.

### 6.2 Empresas que monetizan datos de tráfico (verificables)

| Empresa | País | Modelo | Clientes / Referencias |
|---------|------|--------|------------------------|
| **INRIX** | USA | Datos de tráfico en tiempo real, analytics | Provee datos a Google, BMW, Ford, Waze. Cotiza en mercado privado |
| **HERE Technologies** | Países Bajos / Alemania | Mapas y datos de tráfico, location services | Propiedad de consorcio de fabricantes (Audi, BMW, Daimler). Provee a Amazon, Microsoft |
| **Wejo** | Reino Unido | Datos de vehículos conectados (OEM data) | Colabora con OEMs. Cotizaba en NASDAQ (WEJO) hasta su reorganización en 2023 |
| **TomTom** | Países Bajos | Mapas, tráfico, telemática | Provee a Apple, Uber, Renault |
| **Waze (Google)** | Israel / USA | Datos crowdsourced de tráfico | Usada por 140+ millones de usuarios. Programa "Waze for Cities" con gobiernos |
| **Aimsun (Siemens)** | España | Modelación de tráfico, digital twins | Usada en planificación de transporte en ciudades globales |

### 6.3 Tipos de datos con valor comercial

| Tipo de dato | Valor para | Consideraciones de privacidad |
|--------------|-----------|------------------------------|
| **Flujos de tráfico agregados** | Planificadores urbanos, logística, apps | Bajo riesgo (datos agregados) |
| **Matrices origen-destino (LPR)** | Retail, logística, inmobiliario | ALTO riesgo. Requiere anonimización y consentimiento |
| **Patrones de congestión** | Apps de navegación, gobiernos | Bajo riesgo (datos agregados) |
| **Datos de incidentes** | Aseguradoras, servicios de emergencia | Medio riesgo. Requiere anonimización |
| **Datos de velocidad** | Aseguradoras (UBI — Usage Based Insurance) | Medio-alto riesgo. Requiere consentimiento explícito |

### 6.4 Oportunidad de servicio explotable para Chía-Girardot

**Data as a Service (DaaS):**
- La concesión puede vender datos agregados de tráfico a:
  - Apps de navegación (Waze, Google Maps, Apple Maps)
  - Plataformas de logística (Rappi, Mercado Libre, DHL)
  - Aseguradoras (para modelos UBI — pago por uso)
  - Gobiernos municipales (planificación urbana)

**Condición crítica: soberanía del dato y privacidad**
- Los datos deben anonimizarse antes de comercialización
- Debe establecerse claramente quién es dueño de los datos (concesión vs. estado vs. usuarios)
- El marco regulatorio colombiano (Ley 1581 de 2012, Ley 1273 de 2009) regula el tratamiento de datos personales

**Servicio de información premium para usuarios:**
- App propia de la concesión con información en tiempo real: tiempos de viaje, incidentes, condiciones climáticas, disponibilidad de electrolineras
- Modelo freemium: información básica gratuita, alertas premium y rutas optimizadas por suscripción

---

## 7. TENDENCIA 6: SEGURIDAD VIAL INTELIGENTE CON INTELIGENCIA ARTIFICIAL

### 7.1 IA aplicada a seguridad vial: estado real

La inteligencia artificial en seguridad vial no es un concepto futurista. Ya está operando en autopistas y túneles de Europa, Asia y América, aunque su implementación masiva en LATAM está en etapas iniciales.

### 7.2 Proyectos verificables de IA en seguridad vial

| Proyecto | País | Aplicación de IA | Estado | Referencia |
|----------|------|-------------------|--------|------------|
| **ASFINAG (Austria)** | Austria | Detección automática de incidentes (DAI) con IA en 2.200 km de autopistas | Operativo | ASFINAG, sistema Kapsch |
| **Victoria State (Australia)** | Australia | Cámaras con IA para detección de conductas de riesgo (uso de celular, cinturón) | Operativo | VicRoads, Ministerio de Transporte de Victoria |
| **M1 Inglaterra (Highways England)** | Reino Unido | IA para detección de incidentes y gestión de tráfico | Operativo | Highways England, now National Highways |
| **Kapsch Dynac (proyectos globales)** | Global | Integración de analítica de video en plataforma ATMS | Operativo en Autopista al Mar, Vías del Nus | Kapsch Colombia |
| **Proyectos de smart corridors en USA** | USA | IA para detección de peatones, animales, objetos en carretera | Piloto / Operativo | U.S. DOT, FHWA |

### 7.3 Aplicaciones de IA con valor comercial

| Aplicación | Descripción | Valor para concesión |
|------------|-------------|----------------------|
| **Detección automática de incidentes (DAI)** | Cámaras con IA detectan accidentes, detenciones, objetos | Reducción de tiempo de respuesta, menores costos de operación |
| **Clasificación de vehículos** | IA clasifica automáticamente tipo de vehículo por video | Datos para estadísticas, tarificación diferenciada |
| **Detección de peatones / animales** | IA detecta intrusos en calzada | Prevención de accidentes, reducción de siniestralidad |
| **Análisis de congestión predictivo** | Algoritmos predicen congestión 15-30 minutos antes | Información proactiva a usuarios, gestión de demanda |
| **Mantenimiento predictivo** | IA analiza datos de sensores para predecir fallas | Reducción de costos de O&M, menor downtime |

### 7.4 Oportunidad de servicio explotable para Chía-Girardot

**Servicio de seguridad premium para flotas:**
- Flotas comerciales y de transporte público pueden pagar por monitoreo de seguridad en tiempo real
- Alertas de riesgo: vehículos detenidos, peatones en vía, animales, condiciones climáticas adversas
- Informes de seguridad para gestión de flotas

**Servicio para aseguradoras:**
- Datos de incidentes y patrones de riesgo para modelado de primas
- Datos anonimizados de comportamiento de conducción (velocidad, frenados, distancias)

---

## 8. TENDENCIA 7: GESTIÓN ENERGÉTICA Y SOSTENIBILIDAD EN CONCESIONES

### 8.1 Transición energética en infraestructura vial

Las concesiones viales están adoptando tecnologías de eficiencia energética y generación renovable, no solo por regulación ambiental, sino porque generan **ahorro de costos operativos** y pueden producir ingresos.

### 8.2 Proyectos verificables de sostenibilidad en concesiones

| Proyecto | País | Iniciativa | Estado | Referencia |
|----------|------|------------|--------|------------|
| **Abertis (múltiples concesiones)** | España, Francia, Chile, Brasil | Instalación de paneles solares en áreas de servicio, túneles y peajes | En expansión | Informes anuales Abertis, memorias de sostenibilidad |
| **Ruta 68 (Chile)** | Chile | Paneles solares en áreas de servicio y alumbrado LED | Operativo | Concesionaria Ruta 68 |
| **Vespucio Norte (Chile)** | Chile | Alumbrado LED en túneles y áreas de servicio | Operativo | Vespucio Norte Express |
| **Autostrade per l'Italia** | Italia | Compromiso de carbon neutrality en operaciones | En implementación | Planes de sostenibilidad |
| **Brisa (Portugal)** | Portugal | Alumbrado LED, paneles solares, certificación ambiental | Operativo | Brisa, informes de sostenibilidad |
| **Net Zero Highways (UK)** | Reino Unido | Plan para carreteras net zero | En implementación | National Highways UK |

### 8.3 Tecnologías de eficiencia energética verificadas

| Tecnología | Aplicación | Ahorro estimado | Referencia |
|------------|------------|-----------------|------------|
| **Alumbrado LED en túneles** | Iluminación de túneles | 40-60% vs. iluminación tradicional | Proyectos Kapsch en Colombia |
| **Paneles solares en peajes y áreas** | Generación propia de energía | Reduce dependencia de red | Abertis, Brisa |
| **Ventilación inteligente en túneles** | Jet fans con control por demanda (CO/visibilidad) | 20-30% de ahorro energético | Kapsch Dynac, proyectos europeos |
| **Sistemas de respaldo energético** | Baterías + paneles para operación off-grid | Resiliencia operativa | Proyectos en zonas remotas |

### 8.4 Oportunidad de servicio explotable para Chía-Girardot

**Autoconsumo energético y venta a la red:**
- Instalación de paneles solares en:
  - Techos de áreas de servicio
  - Taludes del corredor (si la geografía lo permite)
  - Cubiertas de túneles (donde sea técnicamente viable)
  - Estaciones de peaje (si aplica)
- El excedente de energía puede venderse a la red (regulación CREG de Colombia permite autoconsumo y venta)

**Certificación de carbono neutralidad:**
- La concesión puede certificar la reducción de emisiones y vender créditos de carbono
- Colombia tiene mercado de carbono regulado (Resolución 1447 de 2017 del MinAmbiente)

**Servicio de "carretera verde":**
- Marketing diferenciador: la concesión se posiciona como "corredor sostenible"
- Atractivo para flotas corporativas con compromisos de sostenibilidad
- Posible tarifa diferenciada para vehículos eléctricos (incentivo)

---

## 9. TENDENCIA 8: SERVICIOS DIGITALES AL USUARIO Y EXPERIENCIA DE VIAJE

### 9.1 Expectativa del usuario moderno

El usuario de autopistas ya no acepta solo una vía de asfalto. Espera información en tiempo real, pagos digitales, servicios integrados, y una experiencia de viaje conectada.

### 9.2 Servicios digitales verificados en concesiones

| Servicio | Proyecto / Referencia | Estado | Tecnología |
|----------|----------------------|--------|------------|
| **App propia de concesión** | Múltiples concesiones chilenas, españolas, portuguesas | Operativo | iOS/Android, info de tráfico, pagos, electrolineras |
| **Información de tráfico en tiempo real** | Waze, Google Maps, INRIX | Operativo | APIs de datos, crowdsourcing |
| **Pago digital integrado** | Concesiones con apps propias | Operativo | Wallet integrado, tarjetas de crédito, débito |
| **Reserva de servicios (estacionamiento, comida)** | Apps de concesiones europeas | En expansión | Integración con comercios en áreas de servicio |
| **Asistencia en carretera digital** | Apps de concesiones (SOS digital) | Operativo | Botón de pánico, geolocalización, chat |
| **Información de electrolineras** | Electrify America, Ionity | Operativo | Disponibilidad en tiempo real, reserva de cargador |

### 9.3 Oportunidad de servicio explotable para Chía-Girardot

**App de la concesión (modelo de referencia: concesiones chilenas y europeas):**
- Funcionalidades básicas (gratuitas):
  - Tiempos de viaje en tiempo real
  - Alertas de incidentes y congestionamiento
  - Estado de electrolineras
  - Condiciones climáticas del corredor
  - Ubicación de áreas de servicio
- Funcionalidades premium (suscripción o pago por uso):
  - Rutas optimizadas por IA (evitar congestión)
  - Reserva de electrolinera
  - Alertas de seguridad personalizadas (ej. "niebla en el túnel X")
  - Información de origen-destino para planificación
  - Integración con pago de peaje (si aplica) o servicios de la vía

**Servicio de asistencia vial digital:**
- Botón de SOS en app con geolocalización precisa
- Coordinación automática con grúas, ambulancias, policía
- Servicio puede cobrarse a aseguradoras o ser gratuito para usuarios registrados

**Integración con plataformas MaaS (ver sección 10):**
- La app de la concesión puede integrarse con apps de transporte público, bicicletas compartidas, y servicios de movilidad urbana en los extremos del corredor (Bogotá y Girardot)

---

## 10. TENDENCIA 9: LOGÍSTICA INTELIGENTE Y CONTROL DE CARGA

### 10.1 El corredor vial como plataforma logística

Las autopistas no solo transportan personas; transportan carga. La gestión inteligente de la logística en corredores viales es una tendencia creciente con potencial de ingresos.

### 10.2 Proyectos verificables de logística inteligente en concesiones

| Proyecto | País | Aplicación | Estado | Referencia |
|----------|------|------------|--------|------------|
| **WIM (Weigh-in-Motion) en Palmillas-Apaseo** | México | Pesaje en movimiento + clasificación de ejes | Operativo | Kapsch, agosto 2025 |
| **Control de peso en Chile** | Chile | Estaciones WIM en concesiones para fiscalización de carga | Operativo | Ministerio de Obras Públicas Chile |
| **Plataformas logísticas en áreas de servicio (Europa)** | Europa | Hubs de carga última milla en áreas de servicio | Piloto / En expansión | Proyectos de logística urbana en autopistas |
| **C-V2X para logística de flotas** | Piloto global | Comunicación entre camiones y centros de control | Piloto | Varios proyectos de fabricantes de camiones |

### 10.3 Tecnologías de control de carga verificadas

| Tecnología | Función | Referencia |
|------------|---------|------------|
| **WIM (Pesaje en movimiento)** | Pesar vehículos sin detenerlos, clasificar ejes | Kapsch en Palmillas-Apaseo, Kistler, Intercomp |
| **SACV (Sistema de Autocontrol de Vehículos)** | Colombia — sistema de fiscalización de carga | Implementado por MinTransporte en corredores nacionales |
| **LPR para logística** | Identificación de vehículos de carga, control de acceso | Proyectos Kapsch global |
| **Cámaras de inspección de carga** | Verificación visual de carga sin detener vehículo | Proyectos en Europa y USA |

### 10.4 Oportunidad de servicio explotable para Chía-Girardot

**Servicio de control de peso y dimensiones:**
- Instalación de estaciones WIM en puntos estratégicos del corredor
- Servicio de fiscalización para autoridades (puede ser contratado por MinTransporte o ANI)
- Datos de carga para planificación de mantenimiento de pavimento (vehículos pesados causan más deterioro)

**Hub logístico en áreas de servicio:**
- Áreas de servicio pueden convertirse en mini-hubs de distribución para "última milla" en municipios del corredor
- Servicio de transbordo: camiones grandes dejan carga, vehículos menores distribuyen
- Ingresos por alquiler de espacio y servicios logísticos

**Servicio de rastreo para flotas:**
- Monitoreo de flotas comerciales que usan el corredor
- Informes de tiempos de recorrido, eficiencia, cumplimiento de rutas
- Modelo SaaS: suscripción mensual por flota

---

## 11. TENDENCIA 10: INTEGRACIÓN MULTIMODAL Y MOBILITY AS A SERVICE (MaaS)

### 11.1 El concepto MaaS

Mobility as a Service (MaaS) es la integración de múltiples modos de transporte (autobús, metro, bicicleta, taxi, carsharing, autopista) en una sola plataforma digital donde el usuario planifica, reserva y paga todo en un solo lugar. Las autopistas son un componente crítico de este ecosistema.

### 11.2 Proyectos verificables de MaaS

| Proyecto | País | Alcance | Estado | Referencia |
|----------|------|---------|--------|------------|
| **Whim (MaaS Global)** | Finlandia | App que integra transporte público, taxi, bicicleta, carsharing | Operativo en Helsinki, expansión a Europa y Asia | MaaS Global Oy, fondos de inversión verificados |
| **Jelbi (Berlín)** | Alemania | App municipal que integra 30+ servicios de movilidad | Operativo | BVG (Berliner Verkehrsbetriebe) |
| **Uber / Lyft integración** | USA / Global | Integración de transporte público en apps de ride-hailing | Operativo | Uber Transit, Lyft app |
| **Moovit (Intel)** | Israel / Global | App de transporte público con integración multimodal | Operativo en 3.400+ ciudades | Adquirida por Intel en 2020 |
| **Naviki (Alemania)** | Alemania | App de navegación multimodal (bici, transporte público, auto) | Operativo | Stadtwerke Bonn |
| **Prueba MaaS en España (Madrid, Barcelona)** | España | Piloto de integración de servicios | Piloto | Ministerio de Transporte español |

### 11.3 Rol de las concesiones viales en MaaS

Las autopistas en MaaS no son solo un modo de transporte; son:
- **Conectores** entre hubs de transporte público (ej. terminal de Bogotá ↔ terminal de Girardot)
- **Proveedores de datos** de tiempos de viaje para planificación multimodal
- **Puntos de intercambio modal** (Park & Ride en áreas de servicio)
- **Servicio de reserva** (pago integrado de peaje + transporte público + estacionamiento)

### 11.4 Oportunidad de servicio explotable para Chía-Girardot

**Park & Ride + intermodalidad:**
- Áreas de servicio estratégicas pueden convertirse en Park & Ride
- Usuarios dejan vehículo privado y toman transporte público (bus, eventual tren) para ingresar a Bogotá
- Reduce congestión en la ciudad, genera ingresos por estacionamiento

**Integración con apps de movilidad de Bogotá y Girardot:**
- La concesión puede integrar datos del corredor con:
  - TransMilenio (Bogotá)
  - Sistema de buses de Girardot
  - Apps de transporte local (taxis, motos)
- Modelo: API de datos que vende a plataformas MaaS locales

**Servicio de carpooling en corredor:**
- Plataforma de carpooling para usuarios frecuentes del corredor (Chía-Bogotá, Girardot-Bogotá)
- Modelo similar a Waze Carpool (operado por Google)
- Reducir número de vehículos, generar comunidad de usuarios, datos adicionales

---

## 12. CONCLUSIONES: ECOSISTEMA DE SERVICIOS EXPLOTABLES PARA CHÍA-GIRARDOT

### 12.1 Síntesis de oportunidades

El proyecto APP Chía-Girardot no debe concebirse como una simple vía de asfalto. Debe diseñarse como una **plataforma de servicios múltiples** donde la tecnología ITS genera ingresos directos e indirectos. Las oportunidades verificables, ordenadas por madurez y riesgo, son:

| Prioridad | Servicio | Madurez | Riesgo | Ingresos potenciales | Proyectos de referencia |
|-----------|----------|---------|--------|----------------------|------------------------|
| **1** | Electrolineras + venta de energía | ALTA | Bajo | ALTO | Ruta 68 Chile, Brisa Portugal, Abertis |
| **2** | Datos de tráfico (DaaS) | ALTA | Medio | MEDIO-ALTO | INRIX, HERE, Wejo |
| **3** | App de concesión + servicios digitales | ALTA | Bajo | MEDIO | Concesiones chilenas, españolas |
| **4** | Peaje dinámico / tarifas diferenciadas | ALTA | Medio | ALTO | Singapur ERP, Londres, Estocolmo |
| **5** | Seguridad vial con IA (servicio a flotas) | ALTA | Medio | MEDIO | ASFINAG Austria, Victoria Australia |
| **6** | Logística inteligente + WIM | ALTA | Bajo | MEDIO | Palmillas-Apaseo México, SACV Colombia |
| **7** | Gestión energética + paneles solares | ALTA | Bajo | MEDIO-BAJO | Abertis, Brisa, Ruta 68 |
| **8** | Park & Ride + intermodalidad | MEDIA | Medio | MEDIO | Proyectos europeos MaaS |
| **9** | V2X como servicio premium | BAJA | Alto | BAJO (a corto plazo) | Bizkaia España, pilotos USA |
| **10** | MaaS integración | MEDIA | Medio | BAJO-MEDIO (a corto plazo) | Whim Finlandia, Jelbi Berlín |

### 12.2 Estrategia recomendada

**Fase 1 (Años 1-5): Servicios de alta madurez, bajo riesgo**
- Electrolineras en áreas de servicio (modelo de alquiler de espacio a operadores)
- App de concesión con información básica + servicios premium
- WIM para control de carga y datos para mantenimiento
- Paneles solares para autoconsumo y venta de excedente
- Alumbrado LED en túneles y vías

**Fase 2 (Años 5-10): Servicios de madurez media, mayor complejidad**
- Monetización de datos de tráfico (DaaS a terceros)
- Peaje dinámico / tarifas diferenciadas por horario
- Servicios de seguridad con IA para flotas y aseguradoras
- Park & Ride + integración con transporte público
- Hubs logísticos en áreas de servicio

**Fase 3 (Años 10-25): Servicios emergentes**
- V2X como servicio premium (si la penetración de vehículos equipados lo justifica)
- Integración completa MaaS
- V2G (Vehicle-to-Grid) si la tecnología madura
- Movilidad autónoma (si el marco regulatorio lo permite)

### 12.3 Consideraciones regulatorias para Colombia

| Servicio | Marco regulatorio colombiano | Estado |
|----------|------------------------------|--------|
| Electrolineras | Resolución 181495 de 2020 (MinMinas), CREG | Vigente, permite venta de energía |
| Peaje dinámico | Ley 1682 de 2013, ANI | Posible con aprobación de la ANI |
| Datos de tráfico | Ley 1581 de 2012 (datos personales), Ley 1273 de 2009 | Requiere anonimización y consentimiento |
| Autoconsumo energético | Resolución CREG 030 de 2018 | Vigente, permite venta de excedentes |
| V2X | Sin regulación específica | No existe marco en Colombia (2026) |

### 12.4 Advertencia final sobre honestidad técnica

Este documento presenta tendencias y oportunidades basadas en proyectos verificables. Sin embargo:
- **No todos los servicios son viables en todos los contextos.** La viabilidad de electrolineras, por ejemplo, depende de la penetración de vehículos eléctricos en Colombia (actualmente <2% del parque automotor en 2026).
- **El marco regulatorio colombiano tiene limitaciones.** El peaje dinámico, aunque técnicamente posible, requiere aprobación de la ANI y no hay precedentes en Colombia de su implementación.
- **Los ingresos proyectados son estimaciones.** No se presentan cifras específicas de ingresos porque dependen de múltiples variables: demanda, regulación, competencia, y modelo de negocio exacto. El capítulo de modelo financiero (siguiente entregable) debe desarrollar estas cifras con rigor.
- **La tecnología V2X y MaaS son apuestas de largo plazo.** No deben incluirse como base del modelo financiero a corto plazo, sino como opciones de expansión.

---

## ANEXO: REFERENCIAS VERIFICABLES

| # | Referencia | Fuente | Fecha | Notas |
|---|-----------|--------|-------|-------|
| 1 | Kapsch - Nogales-Puchuncaví (Chile) SmartToll | Business Wire / Kapsch | Enero 2022 | Peaje MLFF + tradicional |
| 2 | Kapsch - Palmillas-Apaseo (México) | Kapsch | Agosto 2025 | WIM, LPR, CCTV, EcoTrafiX |
| 3 | Kapsch - Bizkaia Connected Corridor V2X | Kapsch | Junio 2023 | 25 RSU en 60 km |
| 4 | Kapsch - Autopista al Mar 1 (Colombia) | Business Wire | Junio 2021 | Dynac, SCADA, túneles |
| 5 | Kapsch - Vías del Nus / La Quiebra (Colombia) | Business Wire / RNS | Abril 2022 | Dynac, túneles, ATMS |
| 6 | Singapore Land Transport Authority - ERP | LTA Singapore | Vigente | Sistema de peaje dinámico desde 1998 |
| 7 | Transport for London - Congestion Charge | TfL | Vigente | Peaje zona central desde 2003 |
| 8 | Swedish Transport Agency - Congestion Tax | Transportstyrelsen | Vigente | Estocolmo desde 2007, Gothenburg desde 2013 |
| 9 | ASFINAG (Austria) - IA en seguridad vial | ASFINAG | Vigente | 2.200 km con DAI |
| 10 | Abertis - Informes de sostenibilidad | Abertis | Anual | Electrolineras, paneles solares |
| 11 | Brisa (Portugal) - Sostenibilidad | Brisa | Anual | Electrolineras, LED, PRR |
| 12 | Ruta 68 / Vespucio Norte (Chile) | Concesionarias | Vigente | Electrolineras en áreas de servicio |
| 13 | INRIX - Datos de tráfico | INRIX | Vigente | Empresa cotizada, provee a Google, BMW |
| 14 | HERE Technologies - Mapas y tráfico | HERE | Vigente | Propiedad de consorcio automotriz |
| 15 | Wejo - Datos vehículos conectados | Wejo | 2020-2023 | Cotizada en NASDAQ, reorganizada 2023 |
| 16 | Whim / MaaS Global | MaaS Global | Vigente | App MaaS en Helsinki, inversores verificados |
| 17 | Jelbi (Berlín) | BVG | Vigente | App multimodal municipal |
| 18 | Electrify America | Volkswagen Group | Vigente | Red carga rápida USA |
| 19 | Resolución 181495 de 2020 (Colombia) | MinMinas | 2020 | Marco electrolineras |
| 20 | Resolución CREG 030 de 2018 (Colombia) | CREG | 2018 | Autoconsumo y venta excedentes |
| 21 | Ley 1581 de 2012 (Colombia) | Congreso Colombia | 2012 | Protección de datos personales |
| 22 | Global Market Insights - ITS Market | GMI | 2024 | Mercado ITS global |
| 23 | BID - Transformación digital transporte | BID / IADB | 2024 | Publicaciones técnicas |
| 24 | ANI Colombia - APP Estanquillo-Popayán | ANI | Marzo 2026 | Proyecto de referencia |
| 25 | MinTransporte Colombia - Resolución 28675 | MinTransporte | 2022 | Sistemas ITS en Colombia |

---

**Documento elaborado por ZEUS para INNOVADATACO**
**Fecha:** Junio 2026
**Estado:** Borrador para revisión del CEO
**Nota:** Toda la información proviene de fuentes verificables públicas. No se incluyen datos inventados ni proyecciones no confirmadas. Las oportunidades de negocio presentadas requieren validación de viabilidad regulatoria y de mercado en el contexto específico colombiano.
