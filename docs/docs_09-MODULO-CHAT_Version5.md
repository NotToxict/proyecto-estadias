# 💬 Módulo de Chat interno y Soporte

> Comunicación en tiempo real entre usuarios del sistema: equipo interno (técnicos, coordinación, inventario, supervisor) y clientes.

---

## 📋 ¿Qué incluye este módulo?

- Chat integrado para comunicación operativa
- Conversaciones 1 a 1, grupales y chats rápidos por servicio/reportes
- Chat cliente–soporte para seguimiento de tickets
- Notificaciones de mensajes nuevos con badges y alertas push/email
- Adjuntos: fotos, archivos PDF e imágenes de servicios
- Histórico de conversaciones por usuario/reportes
- Moderación: bloqueo, historial, reporte de abuso
- Botón de acceso rápido desde cualquier pantalla del sistema

---

## 🗂️ Tipos de chat y usuarios

| Tipo                | ¿Quién conversa?                          | Acceso desde              |
|---------------------|-------------------------------------------|---------------------------|
| Equipo Interno      | Técnicos, Coordinadora, Inventario, Sup.  | Panel, servicios, tickets |
| Chat por Servicio   | Técnico asignado, coord., supervisores    | Detalle servicio/ticket   |
| Chat con Cliente    | Cliente, coordinadora, supervisor         | Portal cliente, tickets   |
| Grupal (broadcast)  | Todo el equipo (avisos, alertas, etc.)    | Panel general             |

---

## 🔄 Flujo típico de uso

```
1. Se asigna un servicio
2. El técnico recibe el ticket y la conversación queda abierta
3. Cliente puede responder (portal, WhatsApp, web)
4. Todos los mensajes quedan en el historial del ticket
5. Coordinadora puede intervenir en cualquier momento
6. Cierre de chat al resolver servicio (no se borra historial)
```

---

## 🖥️ Interfaz y características

### Lista de conversaciones

- Listado de chats activos con orden por últimos mensajes
- Badge de mensajes nuevos/no leídos
- Búsqueda por usuario, ticket, cliente o palabra clave

### Vista de chat

- Burbujas con nombre, avatar, marca de hora/fecha
- Estado: enviado, entregado, leído
- Botón para adjuntar foto, archivo, QR o ubicación
- Posibilidad de bloquear o reportar abuso

### Integraciones

- Envío de mensajes a WhatsApp (cliente)
- Notificaciones push/web/email según usuario
- Notificaciones en escritorio web

---

## 📊 Reportes y registros

- Historial completo de conversaciones por ticket/cliente
- Exportación de chats a PDF para control/auditoría
- Registro de intervenciones (quién, cuándo, tipo de mensaje)
- Analítica: mensajes enviados por usuario, promedio de respuesta, tiempo a primer contacto

---

## 🔒 Privacidad y seguridad

- Chats cifrados entre usuarios internos
- Control de permisos para leer/editar/conversar
- Auditoría de accesos y exportación
- Políticas de retención y eliminación según RGPD o política interna
- Reglamentos de uso y conductas

---

## 👤 Roles y permisos

| Rol          | ¿Qué puede hacer en el chat?                                           |
|--------------|-----------------------------------------------------------------------|
| Técnico      | Chatear con coordinadora, supervisor y equipo                         |
| Coordinadora | Chatear con técnicos, supervisor, inventario, clientes                |
| Inventario   | Solo chat interno, acceso a historial propio                          |
| Supervisor   | Acceso a todos los chats, puede moderar y exportar                    |
| Cliente      | Solo tickets propios, puede enviar archivos y notificaciones          |

---

## 🖼️ Ejemplo de interfaz

```
┌──────────────────────────────────────────────────────────────┐
│ 💬 Chat de Servicio #1247                                    │
├──────────────────────────────────────────────────────────────┤
│ Técnico Pedro [09:45]                                        │
│  “Estoy en camino, llego en 10 min.”                         │
│ Coordinadora Laura [09:46]                                   │
│  “¡Gracias! Confirma al llegar, por favor.”                  │
│ Cliente XYZ [09:53]                                          │
│  “¿Pueden avisar cuando esté resuelto?”                      │
│ ...                                                          │
├──────────────────────────────────────────────────────────────┤
│ [ Adjuntar foto/archivo ]  [ Escribir mensaje...  ] [🚀]      │
└──────────────────────────────────────────────────────────────┘
```

---

[← Anterior: Personal](08-MODULO-PERSONAL.md) | [Inicio](../README.md) | [Siguiente: Mapas →](10-MODULO-MAPAS.md)