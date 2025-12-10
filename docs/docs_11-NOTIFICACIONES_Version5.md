# 🔔 Módulo de Notificaciones

> Sistema centralizado de alertas, recordatorios, avisos y mensajería para usuarios internos y clientes.

---

## 📋 ¿Qué incluye este módulo?

- Envío de notificaciones automáticas y manuales por distintos medios:
  - App web/móvil (modales, banners, badges)
  - Email
  - Push notification (celulares, web)
  - WhatsApp (solo clientes)
- Soporte de diferentes categorías:
  - Recordatorios de servicio/asistencia/lecturas
  - Alertas críticas (stock, excedente, fuera de horario/ruta, etc.)
  - Cambios de estado (servicio asignado, completado, cancelado)
  - Mensajes masivos (avisos corporativos, actualizaciones)

---

## 🗂️ Estructura de una notificación

| Campo            | Tipo      | Obligatorio | Descripción                                   |
|------------------|-----------|:-----------:|-----------------------------------------------|
| ID               | Texto     | ✅          | Identificador único                           |
| Fecha/Hora       | Datetime  | ✅          | Momento de envío o programación               |
| Destinatario     | Selector  | ✅          | Usuario, grupo o cliente específico            |
| Medio            | Selector  | ✅          | App, push, email, WhatsApp                    |
| Categoría        | Selector  | ✅          | Aviso, alerta, recordatorio, incidente        |
| Título           | Texto     | ✅          | Texto corto y descriptivo                     |
| Mensaje          | Texto     | ✅          | Detalle de la notificación                    |
| Estado           | Selector  | ✅          | Enviada, pendiente, leída, fallida            |
| Origen           | Texto     | ❌         | Módulo/campo que genera la alerta             |
| Adjuntos         | Archivos  | ❌         | Imagen, PDF, link                             |

---

## 🔄 Flujos típicos de notificación

### 1. Notificación automática de flujo operativo

- Nuevo servicio asignado → Técnico recibe push/app/email
- Consumibles bajos (stock mínimo) → Inventario recibe alerta
- Lectura de contador pendiente → Coordinadora/técnico recibe recordatorio
- Excedente de copias/facturación → Cliente recibe email
- Asistencia/entrada tarde → Notificación a usuario y Coordinación

### 2. Notificaciones masivas/manuales

- Mensaje para todos (ej. “Mantenimiento de sistemas el sábado”)
- Aviso sectorizado (solo clientes de cierta ciudad o técnicos en turno)
- Recordatorios de actividades no concluidas, incluso tras tiempo configurable

---

## 📊 Reportes y monitoreo

- Registro histórico de todas las notificaciones enviadas
- Panel con filtros por usuario, fecha, estado y medio de envío
- Métricas: entregas exitosas, pendientes, errores, porcentaje de lectura
- Reportes de impacto (quién leyó, cuándo, desde qué dispositivo)

---

## ⚙️ Configuración y reglas

- Horarios “silenciosos” configurables (opción do-not-disturb)
- Niveles de prioridad por tipo/categoría (ej. crítico = push+email)
- Plantillas editables para mensajes frecuentes y multilenguaje
- Vinculación con automatizaciones (disparar flujo extra al hacer clic)

---

## ⚠️ Seguridad y privacidad

- Acceso solo a notificaciones relacionadas al usuario/cliente
- Registro de intentos y fallas de entrega
- Retención y eliminación automatizada según política
- Soporte para notificaciones con contenidos confidenciales/masking

---

## 👤 Roles y permisos

| Rol           | ¿Qué puede hacer?                                              |
|---------------|---------------------------------------------------------------|
| Administrador | Ver y enviar a todos; configuración de plantillas y horarios  |
| Supervisor    | Consulta y envío por segmento; reporte de métricas            |
| Coordinadora  | Puede notificar técnicos/clientes relevantes                  |
| Técnico       | Solo recibe y responde; alerta si hay incidentes              |
| Cliente       | Solo recibe; puede optar por canal preferido                  |

---

## 🖥️ Ejemplos de interfaz

### App interno

```
🔔 [3] Notificaciones

🟠 Servicio #1291 asignado. Ver detalles [09:12]
🔴 Falla detectada en Ricoh 2555. Ir a ticket [08:47]
🟢 Stock “Toner WX100” agotado. Ir a inventario [08:00]
```

### Web cliente

```
🔔 Notificaciones

Servicio #1291 Completado. Descargar reporte [09/dic 18:41]
Su consumo excede el plan contratado. Ver factura [09/dic 14:30]
```

---

## 🔗 Integración con módulos

| Módulo        | Relación                                 |
|---------------|------------------------------------------|
| Servicios     | Notifica estados y acciones clave        |
| Inventario    | Alertas de stock y pedidos               |
| Contadores    | Recordatorios y facturación              |
| Personal      | Asistencia, ausencias y permisos         |
| Mapas         | Alertas por proximidad o fuera de ruta   |
| Chat          | Menciones, mensajes directos             |

---

[← Anterior: Mapas](10-MODULO-MAPAS.md) | [Inicio](../README.md) | [Siguiente: Portal Cliente →](12-PORTAL-CLIENTE.md)