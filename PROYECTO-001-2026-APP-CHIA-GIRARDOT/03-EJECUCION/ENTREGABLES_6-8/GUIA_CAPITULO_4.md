# GUÍA DE CONTINUIDAD — CAPÍTULO 4: Revisión y Análisis de Tecnologías ITS
## Proyecto: Corredor Chía–Mondoñedo–Girardot (TC-PS-05-917-2026)
### Fecha: 2026-06-03 | Responsable: ZEUS | Estándar: Alto rigor de calidad

---

## 1. ESTRUCTURA OBLIGATORIA DEL CAPÍTULO 4

```
CAPÍTULO 4 — Revisión y análisis de tecnologías ITS, equipamiento de hardware, software y servicios tecnológicos

1. Marco conceptual
2. Propósito
3. Metodología
4. Componente de campo
   ├── CC-01: CCTV (Sistema de Videovigilancia)
   ├── CC-02: VDS (Sistema de Detección de Vehículos)
   ├── CC-03: VMS (Sistema de Mensajería Variable)
   ├── CC-04: SOS (Sistema de Llamada de Emergencia)
   └── CC-05: AID (Sistema de Detección Automática de Incidentes)
5. Ficha técnica de componente de campo (por cada CC-XX)
6. Referencias del mercado
   ├── Proveedores/fabricantes internacionales (3 por componente)
   ├── Proveedores/fabricantes LATAM (3 por componente)
   └── Proveedores/fabricantes nacionales (3 por componente)
7. Análisis comparativo (por cada CC-XX)
8. Conclusiones (por cada CC-XX)
```

---

## 2. CAMPOS OBLIGATORIOS POR PROVEEDOR (11 campos)

Cada proveedor debe incluir obligatoriamente:
1. **Nombre de la solución tecnológica**
2. **Empresa** (nombre legal o comercial)
3. **País** (sede principal o país de origen)
4. **Ciudad** (sede principal o ciudad de operación)
5. **Especialidad** (tipo de empresa: fabricante, integrador, distribuidor, etc.)
6. **Fecha del proyecto implementado** (año real, verificable)
7. **Caso de uso del producto o solución tecnológica** (descripción real del proyecto)
8. **Página web** (URL operativa, validada, certificada, sin inventar)
9. **Nombre del producto** (nombre comercial exacto)
10. **Modelo de regencia** (modelo específico implementado)
11. **Nombre del proyecto donde se implementó la solución tecnológica** (nombre real del proyecto)

---

## 3. REGLAS DE INTEGRIDAD Y NEUTRALIDAD

### 3.1 Prohibiciones absolutas:
- ❌ **Inventar proyectos**: Todo proyecto debe ser real, comprobado y verificable mediante fuente pública (prensa, comunicado oficial, contrato, página web del proveedor).
- ❌ **Inventar URLs**: Todos los enlaces web deben ser validados, certificados y estar operativos. No se permite inventar dominios ni enlaces inexistentes.
- ❌ **Sesgo comercial**: El análisis comparativo y las conclusiones deben ser 100% neutrales. No se permite recomendar, concluir ni sesgar hacia fabricantes o proveedores específicos.
- ❌ **Repetición excesiva de proveedores**: Evitar poner los mismos 3 nacionales (CI2, Deviteck, SIT) y los mismos 2 LATAM (Seguritech, Grupo Masa) en todos los componentes. Cada componente debe tener proveedores distintos según su especialidad real, aunque se permite repetir si está justificado técnicamente.
- ❌ **Alucinar datos**: No inventar especificaciones técnicas, precios, ni características de productos. La ficha técnica debe validarse estrictamente contra el Capítulo 7 del Entregable #1.

### 3.2 Permisos:
- ✅ Pueden ser **fabricantes, integradores o proveedores** — no hay restricción en el tipo de empresa, siempre que el proyecto sea real.
- ✅ Se permite repetir proveedores si está **justificado técnicamente** y el proyecto es diferente.
- ✅ La sección 2.3.2 Variables Críticas de Diseño debe conservar **exactamente** lo definido en el Capítulo 7 del Entregable #1, sin modificar especificaciones.

---

## 4. PROYECTOS REALES VERIFICADOS (BASE DE DATOS)

### CC-01: CCTV (Sistema de Videovigilancia)
| Proveedor | Tipo | Proyecto Real | Verificación |
|-----------|------|--------------|--------------|
| Kapsch | Internacional | Autopista al Mar 1, 59 cámaras, 2018 | Kapsch press release BusinessWire 2021 |
| Axis Communications | Internacional | Programa seguridad vial INVIAS/MinT con SIMS Technologies | Axis case study + Tecnoseguro 2013 |
| Siemens | Internacional | VIITS Colombia 6,000 km (consorcio Kapsch-Deviteck-Seguritech) | Kapsch press release 2021 |
| Seguritech | LATAM | VIITS Colombia 6,000 km, 2022 | Seguritech press release 2022 |
| Grupo Masa | LATAM | Vía al Mar, 2018 | Kapsch press release + otros medios |
| SIMS Technologies | Nacional | Programa seguridad vial INVIAS/MinT con Axis | Axis case study + Tecnoseguro 2013 |
| Deviteck | Nacional | VIITS Colombia | Mencionado en Kapsch press release 2021 |
| CI2 | Nacional | Por verificar proyecto específico | Pendiente |

### CC-02: VDS (Sistema de Detección de Vehículos)
| Proveedor | Tipo | Proyecto Real | Verificación |
|-----------|------|--------------|--------------|
| Iteris | Internacional | Vantage Apex/VantageNext en USA | BusinessWire 2025, sitio iteris.com |
| Siemens | Internacional | ITS Detection Solutions (radar Doppler) | Brochure Siemens assets.new.siemens.com |
| Navtech Radar | Internacional | ClearWay radar en túneles | navtechradar.com (referencia a proyectos) |
| Seguritech | LATAM | VIITS Colombia (componente VDS) | Seguritech press release 2022 |
| Grupo Masa | LATAM | Vía al Mar (componente VDS) | Referencia indirecta |
| Deviteck | Nacional | VIITS Colombia | Kapsch press release 2021 |

### CC-03: VMS (Sistema de Mensajería Variable)
| Proveedor | Tipo | Proyecto Real | Verificación |
|-----------|------|--------------|--------------|
| Daktronics | Internacional | VMS/DMS para highways | daktronics.com (sitio operativo) |
| SWARCO | Internacional | VMS full matrix, paneles LED | swarco.com + brochure VMS 2018 |
| McCain | Internacional | DMS arterial signs | mccain-inc.com (presentación 2023) |
| Seguritech | LATAM | VIITS Colombia (componente VMS) | Seguritech press release 2022 |
| Grupo Masa | LATAM | Vía al Mar (componente VMS) | Referencia indirecta |
| Deviteck | Nacional | VIITS Colombia | Kapsch press release 2021 |

### CC-04: SOS (Sistema de Llamada de Emergencia)
| Proveedor | Tipo | Proyecto Real | Verificación |
|-----------|------|--------------|--------------|
| WHECO | Internacional | Guardian 24 emergency call system | whecocontrols.com (sitio operativo) |
| Daktronics | Internacional | Sistemas de emergencia integrados | daktronics.com |
| SWARCO | Internacional | Sistemas de comunicación vial | swarco.com |
| Seguritech | LATAM | Líneas de emergencia ANI | ani.gov.co 2020 |
| Grupo Masa | LATAM | Sistemas de comunicación en concesiones | Referencia indirecta |
| ANI | Nacional | Líneas de emergencia 123 en concesiones | ani.gov.co 2020 |

### CC-05: AID (Sistema de Detección Automática de Incidentes)
| Proveedor | Tipo | Proyecto Real | Verificación |
|-----------|------|--------------|--------------|
| Kapsch | Internacional | AID en túneles Autopista al Mar | Kapsch press release 2021 |
| Navtech Radar | Internacional | ClearWay AID en túneles | navtechradar.com |
| Iteris | Internacional | Vantage CV sistema de detección | BusinessWire 2023 |
| Seguritech | LATAM | VIITS Colombia (componente AID) | Seguritech press release 2022 |
| Grupo Masa | LATAM | Vía al Mar (componente AID) | Referencia indirecta |
| Deviteck | Nacional | VIITS Colombia | Kapsch press release 2021 |

---

## 5. FUENTES DE VERIFICACIÓN UTILIZADAS

1. **Kapsch BusinessWire 2021**: VIITS Colombia, Autopista al Mar 1, 59 cámaras, 2021
2. **Axis Communications case study**: Programa seguridad vial INVIAS/MinT con SIMS Technologies
3. **Seguritech press release 2022**: VIITS Colombia 6,000 km
4. **ANI.gov.co 2020**: Líneas de emergencia en concesiones
5. **Daktronics.com**: VMS/DMS para highways
6. **SWARCO brochure 2018**: VMS full matrix
7. **Iteris BusinessWire 2025**: Vantage Apex en City of Corona
8. **Siemens brochure**: ITS Detection Solutions radar Doppler
9. **NavtechRadar.com**: ClearWay radar para túneles
10. **WHECOControls.com**: Guardian 24 emergency call system

---

## 6. PROCESO DE VALIDACIÓN POST-ESCRITURA

Antes de entregar el Capítulo 4:
1. [ ] Verificar que cada uno de los 9 proveedores por componente tenga los 11 campos completos
2. [ ] Verificar que todos los enlaces web sean reales y estén operativos
3. [ ] Verificar que los proyectos sean comprobables mediante fuentes públicas
4. [ ] Verificar neutralidad en análisis comparativo y conclusiones
5. [ ] Verificar que no se haya inventado ningún dato técnico
6. [ ] Validar fichas técnicas contra Capítulo 7 del Entregable #1
7. [ ] Revisar ortografía y formato markdown
8. [ ] Subir a GitHub con commit descriptivo

---

## 7. CONTEXTO TÉCNICO DEL PROYECTO

- **Corredor**: Chía–Mosquera–Tocaima–Girardot + Ramal Soacha + Variante Cota + Vías complementarias
- **Longitud**: 306 km
- **Componentes ITS**: 42 componentes según catálogo TransConsult (Tabla 5.3.2)
- **Entregables vinculados**: Entregables 6, 7, 8 del contrato TC-PS-05-917-2026
- **Resolución base**: Resolución 1090 de 2020 del Ministerio de Transporte de Colombia
- **Entregable anterior**: Entregable #1 (Contenido técnico — Capítulo 7 define especificaciones de campo)

---

## 8. NOTAS DE EJECUCIÓN

- **Prioridad**: Fidelidad de información > velocidad de ejecución
- **Estándar**: Alto — la tarea es muy importante
- **Método**: Revisión iterativa con retroalimentación del usuario
- **Almacenamiento**: Archivo `Capitulo_4_Analisis_Tecnologias_ITS.md` en `IDC_PROYECTOS/PROYECTO-001-2026-APP-CHIA-GIRARDOT/03-EJECUCION/ENTREGABLES_6-8/`
- **Repositorio**: https://github.com/Innovadataco/IDC_PROYECTOS.git

---

**Estado**: Guía generada | Próximo paso: Reconstrucción del Capítulo 4 con datos verificados
**Última actualización**: 2026-06-03 | **Próxima revisión**: Al finalizar escritura del capítulo
