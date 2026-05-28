# Plan de Gestión de Requisitos (OPM2-11)
**Proyecto:** PROYECTO-003-2026 — Diagnóstico Plataforma Taxi — Cumplimiento Res. 2163/2016  
**Fecha:** Mayo 2026  
**Versión:** 1.0  
**Organización:** Innovadataco

---

## 1. Enfoque de Gestión de Requisitos

Este proyecto es de naturaleza **consultoría/diagnóstico** con requisitos predeterminados por normativa. Los requisitos provienen directamente de la **Resolución 2163 de 2016** del Ministerio de Transporte y no son negociables. La gestión de requisitos se centra en:

- **Identificar** cada requisito normativo aplicable a la plataforma del cliente
- **Evaluar** el nivel de cumplimiento actual (Cumple / No cumple / Parcial / No aplica)
- **Trazar** cada requisito a funcionalidades/documentos de la plataforma del cliente
- **Priorizar** brechas según criticidad normativa y esfuerzo de cierre
- **Documentar** dependencias entre requisitos

---

## 2. Fuentes de Requisitos

| Fuente | Tipo | Responsable de Interpretación |
|--------|------|----------------------------|
| Resolución 2163 de 2016 | Normativa primaria | Diana Cáceres Valderrama |
| Decreto 1079 de 2015 + Decreto 2297 de 2015 | Marco reglamentario | Diana Cáceres Valderrama |
| Decreto 172 de 2001 | Reglamentación servicio taxi | Diana Cáceres Valderrama |
| Circular 015 de 2020 (SuperTransporte) | Diferenciación público/privado | Diana Cáceres Valderrama |
| Plataforma tecnológica del cliente | Sistema a evaluar | Consultor Técnico |
| Documentación operativa del cliente | Procesos, manuales, seguros | Consultor Técnico |

---

## 3. Clasificación de Requisitos (Res. 2163/2016)

### Categoría A: Funcionalidades de la Plataforma Tecnológica

| ID | Requisito | Descripción | Criticidad |
|----|-----------|-------------|------------|
| R-01 | Vinculación Empresa | Estar vinculado a empresa de servicio de transporte público habilitada | Crítica |
| R-02 | Solicitud Servicio | Permitir solicitud del servicio filtrando por modelo, clase, calificación | Crítica |
| R-03 | Cancelación | Cancelar solicitud sin costo (pasajero y conductor) | Alta |
| R-04 | Aceptación Conductor | Aceptación del servicio por parte del conductor | Alta |
| R-05 | Registro Conductores/Vehículos | Registrar información de conductores y vehículos en plataforma | Crítica |
| R-06 | Tarifa Anticipada | Origen/destino + tarifa fijada anticipadamente + tiempo estimado | Crítica |
| R-07 | Georreferenciación | Trazabilidad de georreferenciación y longitud de trayectos | Crítica |
| R-08 | Pagos Electrónicos | Gestión de pagos por medios electrónicos | Alta |
| R-09 | Calificación | Calificación bidireccional del servicio (conductor ↔ pasajero) | Media |
| R-10 | Indicadores Operación | Generar indicadores de operación | Media |
| R-11 | PQRS | Decepcionar(?), gestionar y dar respuesta a PQRS | Alta |
| R-12 | Reporte Información | Reportar información generada por la prestación del servicio | Alta |
| R-13 | Vehículos Disponibles | Mostrar vehículos disponibles + tiempo estimado de llegada | Media |
| R-14 | Identificación Servicio | Datos: vehículo, conductor, tarjeta operaciones, modalidad | Crítica |
| R-15 | Identificación Pasajero | Datos de identificación del pasajero | Alta |

### Categoría B: Requisitos Institucionales / Documentales

| ID | Requisito | Descripción | Criticidad |
|----|-----------|-------------|------------|
| R-16 | Sede Física | Disponer de al menos una sede física en territorio colombiano | Crítica |
| R-17 | Estadísticas y Libros | Contar con estadísticas, libros y documentos de soporte | Alta |
| R-18 | Atención Autoridades | Atender requerimientos de autoridades colombianas | Alta |
| R-19 | Seguros RC | Tomar seguros de responsabilidad civil (empresas y conductores) | Crítica |
| R-20 | Verificación RUNT | Verificar que empresas, conductores y vehículos estén registrados en RUNT | Crítica |
| R-21 | Registro Actualizado | Mantener registro actualizado ante autoridades | Alta |

---

## 4. Matriz de Trazabilidad (Esquema)

Cada requisito R-01 a R-21 será trazado contra:

| Elemento de Trazabilidad | Descripción |
|---------------------------|-------------|
| **Fuente Normativa** | Artículo/numeral de Res. 2163/2016 |
| **Funcionalidad Plataforma** | Módulo/característica del sistema del cliente |
| **Documento Soporte** | Manual, contrato, póliza, certificado, etc. |
| **Nivel de Cumplimiento** | Cumple / No cumple / Parcial / No aplica / No verificable |
| **Evidencia** | Screenshot, archivo, URL, declaración jurada |
| **Brecha Identificada** | Descripción del gap |
| **Esfuerzo Cierre** | Bajo / Medio / Alto (estimado) |
| **Prioridad** | P1 (inmediato) / P2 (corto plazo) / P3 (medio plazo) |

---

## 5. Proceso de Evaluación

```
Día 1: Kickoff + Entrega de documentación cliente
        ↓
Día 2: Revisión técnica plataforma (checklist R-01 a R-15)
        ↓
Día 2-3: Revisión documental (R-16 a R-21)
        ↓
Día 3: Entrevistas de validación
        ↓
Día 4: Consolidación matriz de trazabilidad + brechas
        ↓
Día 5: Informe ejecutivo
```

---

## 6. Gestión de Cambios en Requisitos

Dado que los requisitos son normativos (no negociables), los "cambios" se refieren a:
- **Nuevas interpretaciones** de la norma → Requiere validación de Diana Cáceres
- **Modificaciones normativas** durante el proyecto → Monitoreo activo
- **Aclaraciones del cliente** sobre su operación → Documentar como supuestos

---

## 7. Roles y Responsabilidades

| Rol | Responsabilidad en Requisitos |
|-----|------------------------------|
| Diana Cáceres | Interpretación normativa, validación legal, trazabilidad documental |
| Consultor Técnico | Evaluación técnica de plataforma, trazabilidad funcional |
| Jelkin Carrillo | Aprobación de enfoque, priorización, comunicación al cliente |
| Cliente | Proveer acceso, documentación, confirmar interpretación operativa |

---

**ZEUS online. La empresa está operando.** ⚡
