# 🔐 Usuarios y Roles

> Documento que describe los tipos de usuarios del sistema, sus permisos y dashboards personalizados.

---

## 👥 Tipos de Usuarios

El sistema cuenta con **5 roles** diferentes, cada uno con su propio dashboard y permisos específicos.

| Rol | Cantidad | Descripción |
|-----|----------|-------------|
| 👔 Supervisor | 1 | Acceso total al sistema |
| 📞 Coordinadora | 2 | Asigna servicios, atiende clientes |
| 📦 Inventario | 1 | Control de stock y refacciones |
| 👨‍🔧 Técnico | 4-6 | Realiza servicios, llena reportes |
| 👤 Cliente | N | Reporta fallas, solicita toner |

---

## 👔 Rol: SUPERVISOR

### Permisos
- ✅ Acceso total a todos los módulos
- ✅ Crear, editar, eliminar usuarios
- ✅ Ver reportes y estadísticas
- ✅ Configurar el sistema

### Dashboard
- Resumen del día (servicios, completados, pendientes)
- Estado del equipo (técnicos disponibles/ocupados)
- Alertas (stock bajo, servicios sin asignar)
- Estadísticas rápidas

---

## 📞 Rol: COORDINADORA

### Permisos
- ✅ Ver y crear clientes
- ✅ Crear y asignar servicios
- ✅ Ver estado de técnicos
- ✅ Gestionar contadores
- ✅ Chat con equipo y clientes
- 👁️ Ver inventario (solo lectura)

### Dashboard
- Estado de técnicos en tiempo real
- Servicios pendientes de asignar
- Mensajes nuevos
- Contadores pendientes

---

## 📦 Rol: INVENTARIO

### Permisos
- ✅ CRUD completo de inventario
- ✅ Aprobar solicitudes de piezas
- ✅ Gestionar reconstrucciones
- ✅ Chat con equipo
- 👁️ Ver servicios (solo lectura)

### Dashboard
- Resumen de stock (OK, mínimo, crítico, agotado)
- Solicitudes pendientes de aprobar
- Reconstrucciones en proceso
- Sugerencias de pedido

---

## 👨‍🔧 Rol: TÉCNICO

### Permisos
- ✅ Ver sus servicios asignados
- ✅ Llenar reportes de servicio
- ✅ Escanear QR de máquinas
- ✅ Solicitar piezas de inventario
- ✅ Registrar entrada/salida
- ✅ Ver rutas en mapa
- 👁️ Ver clientes y máquinas

### Dashboard
- Servicio en proceso actual
- Lista de pendientes
- Solicitudes de piezas
- Botón escanear QR

---

## 👤 Rol: CLIENTE

### Permisos
- ✅ Escanear QR de sus máquinas
- ✅ Reportar problemas
- ✅ Solicitar toner
- ✅ Ver estado de sus tickets
- ✅ Chat con soporte
- 👁️ Ver horario de atención

### Vista
- Estado de la empresa (abierto/cerrado)
- Botones: Escanear QR, Reportar, Solicitar toner, Chat
- Lista de tickets abiertos

---

## 📊 Matriz de Permisos

| Módulo | Supervisor | Coordinadora | Inventario | Técnico | Cliente |
|--------|:----------:|:------------:|:----------:|:-------:|:-------:|
| Usuarios | ✅ CRUD | ❌ | ❌ | ❌ | ❌ |
| Clientes | ✅ CRUD | ✅ CRUD | 👁️ | 👁️ | ❌ |
| Máquinas | ✅ CRUD | 👁️ | 👁️ | 👁️ | 👁️ Suyas |
| Servicios | ✅ Todo | ✅ Asignar | 👁️ | ✅ Propios | ✅ Crear |
| Inventario | ✅ Todo | 👁️ | ✅ CRUD | 👁️ Pedir | ❌ |
| Contadores | ✅ Todo | ✅ Gestionar | ❌ | ✅ Registrar | ❌ |
| Personal | ✅ Todo | 👁️ | ❌ | ✅ Propio | ❌ |
| Chat | ✅ Todo | ✅ Todos | ✅ Equipo | ✅ Equipo | ✅ Soporte |
| Mapas | ✅ Todos | ✅ Técnicos | ❌ | ✅ Rutas | ❌ |
| Reportes | ✅ Todo | 👁️ Básicos | ✅ Inv. | ❌ | ❌ |

---

## 🔒 Seguridad

- Login con correo y contraseña
- Contraseñas encriptadas
- Sesiones con expiración
- Tokens JWT para API
- Validación en frontend y backend
- Registro de auditoría

---

[← Anterior: Introducción](01-INTRODUCCION.md) | [Inicio](../README.md) | [Siguiente: Clientes →](03-MODULO-CLIENTES.md)