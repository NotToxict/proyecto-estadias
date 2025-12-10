# 📋 Módulo de Servicios

> Gestión de tickets, asignaciones, estados y reportes de servicio.

---

## 📋 Descripción General

Este módulo es el **corazón del sistema**. Gestiona todo el flujo desde que un cliente reporta un problema hasta que el técnico lo resuelve.

---

## 🔄 Flujo de un Servicio

1. Cliente reporta problema
2. Coordinadora recibe ticket
3. Coordinadora asigna técnico
4. Técnico recibe notificación
5. Técnico marca "En camino"
6. Técnico llega y escanea QR
7. Técnico realiza el trabajo
8. Técnico llena reporte y finaliza
9. Servicio completado

---

## 📊 Estados del Servicio

| Estado | Icono | Descripción |
|--------|:-----:|-------------|
| Nuevo | 🆕 | Sin asignar |
| Asignado | 📋 | Tiene técnico |
| En Camino | 🚗 | Técnico en ruta |
| En Proceso | 🔧 | Trabajando |
| Completado | ✅ | Terminado |
| Cancelado | ❌ | Cancelado |
| Pendiente | ⏸️ | Falta algo |

---

## 🎯 Tipos de Servicio

| Tipo | Prioridad |
|------|:---------:|
| 🔧 Reparación | 🔴 Alta |
| 🛠️ Mantenimiento | 🟢 Normal |
| 🖨️ Toner | 🟡 Media |
| 📊 Lectura | 🟢 Normal |
| 📦 Instalación | 🟡 Media |
| 🔄 Retiro | 🟢 Normal |

---

## 📝 Reporte del Técnico

Al completar un servicio, el técnico registra:

- Contadores (B/N y Color)
- Nivel de toners (%)
- Diagnóstico
- Solución aplicada
- Refacciones usadas
- Pendientes (si hay)
- Persona que atendió
- Hora inicio y fin

---

## 🔔 Notificaciones

| Evento | Quién Recibe |
|--------|--------------|
| Nuevo ticket | Coordinadoras |
| Asignado | Técnico |
| En camino | Coordinadora |
| Completado | Coordinadora + Cliente |

---

[← Anterior: Máquinas](04-MODULO-MAQUINAS.md) | [Inicio](../README.md) | [Siguiente: Inventario →](06-MODULO-INVENTARIO.md)