# 🌐 Módulo Portal del Cliente

> Portal web seguro donde el cliente puede interactuar, consultar información relevante, monitorear tickets/servicios, facturación y recibir atención de soporte.

---

## 📋 ¿Qué incluye este módulo?

- Acceso web seguro con usuario/contraseña y/o SSO (opc.)
- Panel principal con resumen de tickets activos, máquinas y facturación al día
- Consulta de historial de servicios, descargas de reportes y facturas
- Captura de nuevas incidencias y solicitudes (servicio, toner, soporte, lectura contador)
- Seguimiento en tiempo real de tickets (estatus, técnico asignado, historial de mensajes)
- Chat con soporte/coordinadora (responde interno o WhatsApp)
- Consulta de contrato, copias/facturas, excedentes y consumos
- Visualización de sus ubicaciones y máquinas en mapas
- Notificaciones y mensajes directos
- Integración con encuestas de satisfacción post-servicio
- Acceso móvil friendly

---

## 🗂️ Estructura del portal

| Sección             | Descripción                                                  |
|---------------------|-------------------------------------------------------------|
| Inicio/Panel        | Resumen de estado general, alertas, próximos vencimientos   |
| Tickets/Servicios   | Listado, filtrado y detalle de tickets/incidencias          |
| Máquinas            | Inventario del cliente, detalles y estado actual            |
| Facturación         | Facturas emitidas, consumos, descarga de documentos         |
| Lectura de contador | Captura manual (si aplica contrato), histórico              |
| Soporte/Chat        | Opciones de contacto: chat integrado y/o WhatsApp           |
| Contrato            | Consulta condiciones, PDFs, copias incluidas y tarifas      |
| Mapas               | Ubicaciones del cliente y seguimiento de visitas            |
| Notificaciones      | Alertas, mensajes internos y externos                       |
| Encuestas           | Valoraciones post-servicio, historial de NPS                |

---

## 🖼️ Ejemplo de interfaz principal

```
┌────────────────────────────────────────────────────────┐
│ Bienvenido, Cliente XYZ           [Cerrar sesión]      │
├────────────────────────────────────────────────────────┤
│  Tickets activos: 2   |   Máquinas registradas: 5      │
│  Última factura: #1542, pagada el 05/dic/2025          │
├────────────────────────────────────────────────────────┤
│  [ Nueva Solicitud ]  [ Ver Facturas ]  [ Máquinas ]   │
├────────────────────────────────────────────────────────┤
│ ⬇️ Últimas notificaciones                             │
│ 12/dic – Su ticket #1234 fue atendido por Pedro        │
│ 10/dic – Lectura de contador registrada               │
│ ...                                                    │
└────────────────────────────────────────────────────────┘
```

---

## 🏁 Flujo de funcionamiento

1. Cliente accede al portal vía web/móvil (URL segura, contraseña o SSO)
2. Visualiza su panel con estatus, alertas y accesos rápidos
3. Puede realizar solicitudes/reporte de falla, dar lectura y consultar historial
4. Puede chatear con soporte/coordinadora desde cualquier pantalla
5. Recibe y consulta facturas, reportes técnicos y contratos
6. Después de cada servicio puede responder una encuesta de satisfacción

---

## 🔒 Seguridad y permisos

- Cada cliente SOLO accede a su información (multi-empresa opcional: admin con agregados)
- Opcional: autenticación en dos pasos (2FA)
- Historial de accesos y actividades para auditoría
- Los archivos/contratos/facturas son descargables solo por el cliente autorizado

---

## ⚠️ Notificaciones y alertas

- Estado de tickets/servicios e incidencias nuevas
- Facturas emitidas/pagos/pendientes vencimiento
- Recordatorio cuando se requiere lectura de contador
- Aviso post-servicio para encuesta de experiencia

---

## 📲 Integraciones automáticas

| Módulo      | Relación y funciones principales                                 |
|-------------|------------------------------------------------------------------|
| Máquinas    | Solo ve y consulta las propias; trigger de nueva incidencia      |
| Servicios   | Gestión/seguimiento de tickets propios, detalle, historial chat  |
| Facturación | Solo consumo propio, descargas                                   |
| Notificaciones | Push/email internas, avisos                                   |
| Chat/Soporte | Directo en el portal con histórico y adjuntos                   |
| Mapas       | Ver ubicaciones propias, descarga PDF de visitas                 |
| Contratos   | Consulta y descarga, actualización automática                    |
| Contadores  | Registrar lectura y consultar consumos históricos                |

---

## 👤 Roles y permisos

| Rol              | ¿Qué puede hacer?                                          |
|------------------|-----------------------------------------------------------|
| Cliente Regular  | Acceso solo a su empresa (tickets, facturas, chat, etc.)  |
| Cliente Admin    | Administra usuarios internos, ve todos los tickets        |
| Soporte Interno  | Responde tickets/chat, sube archivos, interactúa secamente|
| Coordinadora     | Ve y responde todos tickets/chat de sus empresas asignadas |
| Supervisor       | Accede a vista tablero general de todos (modo sólo lectura)|

---

[← Anterior: Notificaciones](11-NOTIFICACIONES.md) | [Inicio](../README.md) | [Siguiente: Reportes →](13-REPORTES.md)