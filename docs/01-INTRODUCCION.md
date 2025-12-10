# 📋 Introducción

> Documento que describe el contexto del negocio, la problemática actual y la solución propuesta.

---

## 🏢 Sobre la Empresa

**Multifuncionales y Copiado** es una empresa ubicada en **Nogales, Sonora**, México, dedicada al rubro de equipos de impresión y copiado.

### Giro del Negocio

| Actividad | Descripción |
|-----------|-------------|
| 🛒 **Venta** | Comercialización de impresoras multifuncionales nuevas y reconstruidas |
| 🔄 **Renta** | Arrendamiento de equipos con cobro por contador (copias realizadas) |
| 🔧 **Servicio Técnico** | Reparación y mantenimiento de equipos |
| 🔄 **Reconstrucción** | Restauración de equipos usados para venta o renta |
| 📦 **Refacciones** | Venta de piezas y consumibles |

### Marcas que Manejan

```
┌─────────────────────────────────────────────────────────────────┐
│                      🏭 MARCAS                                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐           │
│   │  SHARP  │  │  XEROX  │  │ SAMSUNG │  │  RICOH  │           │
│   │         │  │         │  │         │  │   ⭐    │           │
│   └─────────┘  └─────────┘  └─────────┘  └─────────┘           │
│                                          (Principal)           │
└─────────────────────────────────────────────────────────────────┘
```

### Cobertura Geográfica

La empresa tiene clientes en múltiples ciudades:

| Estado | Ciudades |
|--------|----------|
| 🇲🇽 **Sonora** | Nogales, Hermosillo, Obregón, Guaymas, Cananea, Agua Prieta, Imuris, Magdalena, Santa Ana, Caborca |
| 🇲🇽 **Baja California** | Mexicali |
| 🇺🇸 **Arizona** | Área fronteriza |
| 🇺🇸 **California** | Calexico |

**Nota:** El sistema iniciará en **Nogales, Sonora** y se expandirá gradualmente.

---

## 👥 Estructura del Personal

```
┌─────────────────────────────────────────────────────────────────┐
│                    🏢 ORGANIGRAMA                               │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  👔 SUPERVISOR (1)                                              │
│      └── Supervisa todas las operaciones                        │
│                                                                 │
│  📞 COORDINACIÓN (2 personas)                                   │
│      ├── Reciben llamadas y WhatsApp de clientes                │
│      ├── Asignan servicios a técnicos                           │
│      └── Coordinan lecturas de contadores para facturación      │
│                                                                 │
│  📦 INVENTARIO (1 persona)                                      │
│      └── Controla stock de piezas y máquinas                    │
│                                                                 │
│  👨‍🔧 TÉCNICOS (4-6 personas)                                     │
│      ├── Realizan servicios y reparaciones                      │
│      ├── Toman lecturas de contadores                           │
│      ├── Mantenimientos preventivos                             │
│      └── Reconstrucción de equipos                              │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Horarios de Trabajo

| Día | Horario | Notas |
|-----|---------|-------|
| Lunes a Viernes | 8:00 AM - 6:00 PM | Horario normal |
| Sábados | 9:00 AM - 12:00 PM | Sistema rotativo (mitad del equipo) |
| Domingos | Cerrado | - |

---

## 😰 Problemática Actual

### 1. Coordinación por WhatsApp

```
PROBLEMA:
- Toda la comunicación es por un grupo de WhatsApp
- Se pierde información importante
- No hay registro formal de asignaciones
- Difícil saber quién está disponible
```

### 2. Reportes en Google Forms

```
PROBLEMA:
- Los técnicos llenan un Google Forms después de cada servicio
- No hay conexión con historial de máquinas
- Se escribe manualmente el cliente, modelo y serie
- Propenso a errores de captura
```

**Campos actuales del Google Forms:**
| Campo | Obligatorio |
|-------|-------------|
| Ciudad | ✅ |
| Cliente | ✅ |
| Modelo | ✅ |
| Serie | ✅ |
| Contador B/N | ✅ |
| Contador Color | ❌ |
| Toner BK (25/50/75/100%) | ✅ |
| Toner C (25/50/75/100%) | ❌ |
| Toner M (25/50/75/100%) | ❌ |
| Toner Y (25/50/75/100%) | ❌ |
| Motivo de llamada | ✅ |
| Diagnóstico | ✅ |
| Solución | ✅ |
| Refacciones utilizadas | ❌ |
| Pendientes | ❌ |
| Persona que atendió | ✅ |
| Hora de inicio | ✅ |
| Hora de finalizado | ✅ |

### 3. Sin Historial de Servicios

```
PROBLEMA:
- No hay forma fácil de consultar servicios anteriores de una máquina
- Los técnicos no saben qué se le hizo antes a un equipo
- Se repiten diagnósticos innecesarios
```

### 4. Control de Inventario Manual

```
PROBLEMA:
- Control de piezas en hojas o sistemas básicos
- No hay alertas de stock bajo
- Las refacciones se piden verbalmente
- No hay trazabilidad de qué pieza se usó en qué servicio
```

### 5. Sin Seguimiento de Técnicos

```
PROBLEMA:
- No se sabe con exactitud dónde está cada técnico
- Difícil asignar servicios al técnico más cercano
- No hay registro de tiempos de traslado
```

### 6. Clientes sin Autoservicio

```
PROBLEMA:
- Los clientes deben llamar o mandar WhatsApp para reportar fallas
- No pueden ver el estado de su solicitud
- No saben cuándo llegará el técnico
```

### 7. Facturación Manual de Contadores

```
PROBLEMA:
- Cada 15-30 días se visita a cada cliente para tomar lectura del contador
- El cálculo de excedentes se hace manualmente
- No hay historial organizado de lecturas
```

---

## ✅ Solución Propuesta

Desarrollo de una **PWA (Progressive Web App)** que integre todas las operaciones del negocio.

### ¿Por qué una PWA?

| Ventaja | Descripción |
|---------|-------------|
| 📱 **Multiplataforma** | Funciona en celular, tablet y computadora |
| 📲 **Instalable** | Se puede instalar como app nativa |
| 🌐 **Sin tiendas** | No requiere publicar en App Store o Play Store |
| 📴 **Offline** | Funciona sin conexión a internet |
| 🔄 **Actualizable** | Se actualiza automáticamente |
| 💰 **Económico** | Un solo desarrollo para todas las plataformas |

### Módulos de la Solución

| # | Módulo | Resuelve |
|---|--------|----------|
| 1 | Usuarios y Roles | Control de acceso por tipo de usuario |
| 2 | Clientes | Base de datos de clientes y ubicaciones |
| 3 | Máquinas | Registro con QR, historial completo |
| 4 | Servicios | Tickets, asignaciones, estados |
| 5 | Inventario | Stock, solicitudes, OCR, alertas |
| 6 | Contadores | Lecturas, facturación, excedentes |
| 7 | Personal | Horarios, asistencia, rotación |
| 8 | Chat | Comunicación interna y con clientes |
| 9 | Mapas | Rutas, GPS, navegación |
| 10 | Notificaciones | Alertas en tiempo real |
| 11 | Portal Cliente | Autoservicio para clientes |
| 12 | Reportes | Estadísticas y dashboards |

---

## 🎯 Alcance del Proyecto

### Incluido (MVP - Producto Mínimo Viable)

- ✅ Sistema de login con roles
- ✅ Gestión de clientes y ubicaciones
- ✅ Registro de máquinas con QR
- ✅ Catálogo de modelos por marca
- ✅ Sistema de tickets/servicios
- ✅ Inventario con solicitudes
- ✅ Lecturas de contadores
- ✅ Chat interno
- ✅ Notificaciones push

### Fase 2 (Posterior)

- 🔜 Portal completo del cliente
- 🔜 Chat con clientes
- 🔜 Mapas y GPS
- 🔜 Reportes avanzados
- 🔜 Expansión a otras ciudades

---

## 📅 Cronograma Tentativo

| Fase | Duración | Actividades |
|------|----------|-------------|
| **Análisis** | Semana 1-2 | Levantamiento de requerimientos, documentación |
| **Diseño** | Semana 3-4 | Base de datos, wireframes, arquitectura |
| **Desarrollo** | Semana 5-12 | Codificación de módulos |
| **Pruebas** | Semana 13-14 | Testing, correcciones |
| **Implementación** | Semana 15-16 | Despliegue, capacitación |

---

[← Volver al inicio](../README.md) | [Siguiente: Usuarios y Roles →](02-USUARIOS-ROLES.md)