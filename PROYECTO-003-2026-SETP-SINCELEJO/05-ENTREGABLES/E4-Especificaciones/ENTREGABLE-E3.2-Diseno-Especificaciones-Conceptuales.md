# ENTREGABLE 3.2 — DISEÑO Y ESPECIFICACIONES CONCEPTUALES

**Proyecto:** Estructuración de los Componentes Tecnológicos del SETP Sincelejo  
**Cliente:** Metro Sabanas S.A.S.  
**Contratista:** Innovadataco  
**Código:** PROYECTO-003-2026-SETP-SINCELEJO / E3.2  
**Versión:** 1.0  
**Fecha:** 15 de junio de 2026

---

## 1. RESUMEN EJECUTIVO

Este documento presenta el diseño conceptual y las especificaciones técnicas de los componentes tecnológicos y subsistemas ITS del SETP Sincelejo, definiendo hardware, software, interfaces y parámetros de operación.

---

## 2. ESPECIFICACIONES DE SUBSISTEMAS

### 2.1 Subsistema de Gestión de Flota

#### 2.1.1 Hardware Onboard

| Componente | Especificación mínima | Especificación recomendada |
|------------|----------------------|---------------------------|
| **CPU** | ARM Cortex-A53, 4 núcleos @ 1.2 GHz | ARM Cortex-A72, 4 núcleos @ 1.5 GHz |
| **RAM** | 2 GB LPDDR4 | 4 GB LPDDR4 |
| **Almacenamiento** | 32 GB eMMC | 64 GB eMMC |
| **GPS** | U-Blox NEO-M8N, GPS/GLONASS | U-Blox NEO-M9N, multi-GNSS |
| **4G/LTE** | Cat-4, 150 Mbps down | Cat-6, 300 Mbps down |
| **WiFi** | 802.11n | 802.11ac dual-band |
| **Bluetooth** | 4.2 | 5.0 |
| **Entradas digitales** | 4x GPIO | 8x GPIO |
| **Entradas analógicas** | 2x ADC | 4x ADC |
| **Comunicación vehículo** | RS-485 | RS-485 + CAN Bus |
| **Alimentación** | 9-36V DC | 9-36V DC con protección ISO 7637 |
| **Temperatura** | -10°C a +60°C | -20°C a +70°C |
| **Protección** | IP54 | IP65 |
| **Certificación** | FCC, CE | FCC, CE, Anatel (si aplica) |

#### 2.1.2 Software Onboard

| Componente | Especificación |
|------------|---------------|
| **Sistema Operativo** | Yocto Linux 4.0 o Ubuntu Core 22 |
| **Container Runtime** | Docker CE |
| **Orquestación** | K3s (Kubernetes ligero) |
| **Base de datos local** | SQLite / DuckDB |
| **Mensajería** | MQTT Client (Eclipse Paho) |
| **VPN** | WireGuard |
| **Actualizaciones OTA** | Mender / RAUC |

#### 2.1.3 Funciones del Sistema Onboard

```python
# Pseudocódigo de funciones principales

class OnboardUnit:
    def track_location(self):
        """Transmite posición GPS cada 10-30 segundos"""
        pass
    
    def monitor_doors(self):
        """Detecta apertura/cierre de puertas"""
        pass
    
    def count_passengers(self):
        """Cuenta embarques/desembarques"""
        pass
    
    def validate_fare(self):
        """Comunicación con validador de tarifas"""
        pass
    
    def display_route_info(self):
        """Muestra información en pantalla conductor"""
        pass
    
    def emergency_button(self):
        """Gestiona botón de pánico"""
        pass
    
    def offline_mode(self):
        """Operación sin conectividad, sincronización posterior"""
        pass
```

---

### 2.2 Subsistema Centro de Control (CVP)

#### 2.2.1 Infraestructura Servidor

| Componente | Especificación mínima | Especificación recomendada |
|------------|----------------------|---------------------------|
| **Servidor aplicación** | 2x VMs, 4 vCPU, 16 GB RAM | 2x VMs, 8 vCPU, 32 GB RAM |
| **Base de datos** | PostgreSQL 14, 1 instancia | PostgreSQL 15, cluster HA |
| **Almacenamiento** | 500 GB SSD | 2 TB SSD NVMe, RAID 10 |
| **Red** | 1 Gbps, VLAN única | 10 Gbps, VLAN segregada |
| **Firewall** | Básico | Perimetral + WAF |
| **UPS** | 1 kVA, 15 min | 2 kVA, 30 min |
| **Aire acondicionado** | No requerido | Split 12.000 BTU |

#### 2.2.2 Software del Centro de Control

| Módulo | Función | Tecnología |
|--------|---------|-----------|
| **Visualización** | Mapa en tiempo real, tableros | Grafana, Mapbox, Leaflet |
| **Alarmas** | Detección de eventos, notificaciones | Prometheus Alertmanager |
| **Reportes** | Generación de informes operativos | Apache Superset / Metabase |
| **Comunicaciones** | Mensajería con buses | MQTT Broker (EMQ X / Mosquitto) |
| **Video** | CCTV, videovigilancia | ZoneMinder / Shinobi |
| **API** | Integraciones externas | Node.js / Python FastAPI |

---

### 2.3 Subsistema de Pago Electrónico

#### 2.3.1 Validador a Bordo

| Característica | Especificación |
|----------------|---------------|
| **Pantalla** | LCD TFT 5" táctil, 800x480 |
| **Lector NFC** | ISO 14443 A/B, MIFARE DESFire EV2 |
| **Lector QR** | Cámara 2D, lectura < 200 ms |
| **Procesador** | Qualcomm Snapdragon 450 o equivalente |
| **RAM** | 2 GB |
| **Almacenamiento** | 16 GB eMMC |
| **Conectividad** | 4G/LTE, WiFi, Bluetooth |
| **Audio** | Buzzer + altavoz |
| **Indicadores LED** | Rojo/Verde/Azul para estados |
| **Alimentación** | 12V DC, 2A |
| **Temperatura** | 0°C a +50°C |
| **Certificación** | PCI PTS 5.x, EMVCo |

#### 2.3.2 Flujo de Transacción

```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│  Usuario │───>│ Validador│───>│ Backoffice│───>│  Pasarela │
│  Tarjeta │ NFC│  a Bordo │ 4G │   Pagos   │ TLS│   Pagos   │
└──────────┘    └──────────┘    └──────────┘    └────┬─────┘
                                                      │
                                              ┌───────┴───────┐
                                              │  Banco / ACH  │
                                              │  (Redeban)    │
                                              └───────────────┘
```

#### 2.3.3 Backoffice de Pagos

| Función | Descripción |
|---------|-------------|
| **Conciliación** | Emparejamiento de transacciones con banco |
| **Reportes** | Ingresos por línea, bus, conductor |
| **Subsidios** | Gestión de subsidios de transporte |
| **Tarifas** | Configuración de tarifas y excepciones |
| **Blacklist** | Tarjetas bloqueadas o reportadas |

---

### 2.4 Subsistema de Información al Usuario

#### 2.4.1 Aplicación Móvil

| Característica | Especificación |
|----------------|---------------|
| **Plataformas** | iOS 14+, Android 8+ |
| **Tecnología** | Flutter / React Native |
| **Funciones** | Rutas, tiempos, recargas, reportes |
| **Notificaciones** | Push (Firebase Cloud Messaging) |
| **Accesibilidad** | WCAG 2.1 nivel AA |

#### 2.4.2 Pantallas en Paradas

| Característica | Especificación |
|----------------|---------------|
| **Tipo** | LED RGB full color o e-ink (opción solar) |
| **Tamaño** | 32" o 43" (según afluencia) |
| **Conectividad** | 4G/WiFi / Ethernet |
| **Alimentación** | 110-240V AC / Panel solar + batería |
| **Información** | Tiempo estimado, próximos buses, alertas |
| **Actualización** | Tiempo real vía MQTT/WebSocket |

---

## 3. ESPECIFICACIONES DE INTERFACES

### 3.1 API del Sistema

```yaml
# Especificación OpenAPI 3.0
openapi: 3.0.0
info:
  title: SETP Sincelejo API
  version: 1.0.0
paths:
  /buses:
    get:
      summary: Lista de buses en operación
      parameters:
        - name: route
          in: query
          schema:
            type: string
      responses:
        200:
          description: Lista de buses
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Bus'
  
  /buses/{id}/location:
    get:
      summary: Ubicación en tiempo real
      parameters:
        - name: id
          in: path
          required: true
          schema:
            type: string
      responses:
        200:
          description: Coordenadas GPS
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Location'

components:
  schemas:
    Bus:
      type: object
      properties:
        id: { type: string }
        plate: { type: string }
        route: { type: string }
        status: { type: string, enum: [active, inactive, maintenance] }
    Location:
      type: object
      properties:
        lat: { type: number }
        lng: { type: number }
        timestamp: { type: string, format: date-time }
        speed: { type: number }
```

### 3.2 Protocolos de Comunicación

| Protocolo | Uso | Puerto |
|-----------|-----|--------|
| **MQTT** | Telemetría buses | 8883 (TLS) |
| **HTTPS/REST** | API pública y privada | 443 |
| **WebSocket** | Actualizaciones en tiempo real | 443 |
| **NMEA 0183** | GPS | Serial |
| **SAE J1939** | Datos vehículo (CAN) | CAN Bus |
| **Modbus RTU** | Sensores industriales | RS-485 |

---

## 4. ESPECIFICACIONES DE SEGURIDAD

### 4.1 Cifrado

| Capa | Método | Implementación |
|------|--------|----------------|
| **Comunicación** | TLS 1.3 | Certificados Let's Encrypt |
| **Datos sensibles** | AES-256-GCM | Librería libsodium |
| **Contraseñas** | Argon2id | Hashing seguro |
| **Backup** | AES-256-CBC | Cifrado en reposo |

### 4.2 Autenticación

| Componente | Método |
|------------|--------|
| **Usuarios** | OAuth 2.0 + MFA |
| **API** | JWT (RS256) |
| **Dispositivos** | Certificados X.509 |
| **Conductores** | Tarjeta NFC + PIN |

### 4.3 Auditoría

| Evento | Registro | Retención |
|--------|----------|-----------|
| **Inicio sesión** | Usuario, IP, timestamp | 2 años |
| **Transacciones** | ID, monto, estado | 5 años |
| **Cambios config** | Usuario, cambio, anterior | 2 años |
| **Alertas** | Tipo, severidad, respuesta | 1 año |

---

## 5. PLAN DE MIGRACIÓN Y ROLLOUT

### 5.1 Fases de Implementación

| Fase | Duración | Alcance |
|------|----------|---------|
| **Fase 1** | Mes 1-2 | Infraestructura cloud + centro de control |
| **Fase 2** | Mes 3-4 | Instalación onboard 10 buses piloto |
| **Fase 3** | Mes 5-6 | Rollout flota completa (34 buses) |
| **Fase 4** | Mes 7-8 | Pago electrónico + app usuarios |
| **Fase 5** | Mes 9-12 | Optimización, integraciones, analytics |

### 5.2 Estrategia de Go-Live

```
Semana -2: Capacitación conductores y supervisores
Semana -1: Pruebas integrales en ambiente de producción
Semana  0: Go-live con monitoreo intensivo 24/7
Semana +1: Ajustes, resolución de incidentes
Semana +2: Operación normal, reporte de estabilización
```

---

**Preparado por:** Innovadataco  
**Fecha:** 15 de junio de 2026  
**Aprobado por:** _________________________
