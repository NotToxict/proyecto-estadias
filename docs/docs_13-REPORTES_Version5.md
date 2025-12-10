# 📈 Módulo de Reportes y Análisis

> Módulo central de consulta, análisis y exportación de información operativa, técnica, administrativa y comercial. Permite tomar decisiones, justificar ante clientes/auditores, y optimizar procesos internos.

---

## 📋 ¿Qué incluye este módulo?

- Generación y consulta de reportes personalizados y predefinidos (dashboards, tabulares, gráficos)
- Exportación a PDF, Excel, CSV, impresión y envíos automatizados por correo
- Filtros avanzados: fechas, clientes, sucursal, máquina, técnico, estatus, servicio, tipo de incidencia, facturación
- Paneles gráficos, tablas dinámicas y estadísticas clave
- Reportes históricos y de auditoría
- Acceso por permisos/rol (interno, cliente, supervisor)
- Motor de reportes programados (“enviar cada fin de mes a administración”)
- Reportes agregados, detallados, cruzados y por agrupadores configurables

---

## 🗂️ Tipos de reportes

### 1. **Reportes Operativos (Servicios/Tickets)**
| Reporte                        | Descripción                                                     | Detalles/Filtros                 |
|--------------------------------|-----------------------------------------------------------------|-----------------------------------|
| Servicios atendidos            | Listado y gráfico de tickets atendidos (por fecha, cliente, etc)| Cliente, fecha, técnico, tipo     |
| Tiempos de respuesta           | Cuánto se tarda en atender/cerrar tickets                       | Promedio, por cliente/técnico     |
| Incidencias abiertas/cerradas  | Cantidad, % resuelto, tiempo en cada estado                     | Estado, cliente, prioridad        |
| Servicios por estado           | Tickets agrupados por estado y evolución en el mes              | Estado, técnico, zona             |
| Auditoría de cambios           | Cambios en tickets, campo anterior/nuevo, quién y cuándo        | Por ticket, usuario, fecha        |

### 2. **Reportes Técnicos (Máquinas/Equipos)**
| Reporte                 | Descripción                                  | Detalles/Filtros              |
|-------------------------|----------------------------------------------|-------------------------------|
| Máquinas más reportadas | Ranking/estadísticas de equipos problemáticos| Cliente, modelo, serie        |
| Historial de refacciones| Piezas cambiadas en equipos, frecuencia      | Máquina, tipo, técnico        |
| Servicios por equipo    | Servicios asignados/realizados en máquina    | Serie, marca, frecuencia      |
| Cambios de consumible   | Historial y consumo de toner, tambor, fusor  | Equipo, tipo, técnico, fechas |

### 3. **Reportes de Inventario**
| Reporte                | Descripción                                  | Detalles/Filtros              |
|------------------------|----------------------------------------------|-------------------------------|
| Movimientos de stock   | Entradas, salidas por usuario, motivo        | Pieza, fecha, responsable     |
| Alertas de stock       | Niveles críticos, pendientes de compra       | Pieza, almacén, estado        |
| Reconstrucciones       | Registro de piezas rehabilitadas/recuperadas | Máquina, responsable, fechas  |

### 4. **Reportes de Contadores y Consumo**
| Reporte                 | Descripción                              | Detalles/Filtros                  |
|-------------------------|------------------------------------------|-----------------------------------|
| Consumo por máquina     | Evolución de copias/impresiones por mes  | Cliente, equipo, color/B&N        |
| Excedente facturado     | Resumen de excedentes y cobros extras    | Cliente, periodo, tipo            |
| Lecturas pendientes     | Incumplimientos o periodos sin lectura   | Técnico, cliente, equipo          |

### 5. **Reportes de Personal y Asistencia**
| Reporte             | Descripción                               | Detalles/Filtros             |
|---------------------|-------------------------------------------|------------------------------|
| Asistencia del equipo | Entradas, salidas, faltas y tardanzas   | Usuario, fecha, rol, turno   |
| Rondas de sábado    | Equilibrio de tareas y rotaciones         | Técnico, fecha, incidencias  |
| Justificaciones     | Motivos de ausencias, permisos y acciones | Tipo, responsable, fecha     |

### 6. **Reportes de Notificaciones y Comunicación**
| Reporte                | Descripción                              | Detalles/Filtros               |
|------------------------|------------------------------------------|--------------------------------|
| Mensajes enviados      | Cuántas alertas, avisos y por qué cana   | Medio, resultado               |
| Chats por servicio     | Conversaciones y seguimiento              | Cliente, agente, fechas        |
| Impacto de notificaciones | Quién leyó, a tiempo, porcentaje      | Usuario, fecha, urgencia       |

### 7. **Reportes para Cliente**
- Accesibles desde el portal web del cliente
- Personalizados solo con su información (respetando privacidad/rol)
- Visualización clara de todos los temas anteriores
- Exportación directa de historial, facturas, reportes técnicos y encuestas de satisfacción

---

## 📊 Paneles e indicadores KPI

- Cobertura de servicios por zona geográfica
- Promedio de satisfacción del cliente (NPS/encuestas)
- Ratio de cumplimiento vs. SLA
- Costos promedio por servicio/máquina/cliente
- Alertas visuales (stock, tickets críticos, vencimientos)
- Índices de rotación/reporte de personal y equipos

---

## 💡 Personalización avanzada

- Constructor visual de reportes (drag and drop, selección de campos)
- Guardado de vistas y reportes favoritos por usuario
- Programación de reporte automatizado (horario y remitentes)
- Acceso seguro: derechos por rol y por tipo de reporte

---

## 🔄 Exportación y entrega automatizada

- Descarga manual: PDF, Excel, CSV, imagen
- Envío automatizado de reportes programados por email a directivos/clientes
- Integración con panel supervisor, portal cliente y área administrativa
- Firma digital opcional de reportes (auditoría o soporte externo)

---

## 🛡️ Seguridad, auditoría y privacidad

- Registro de todas las descargas, consultas, envíos y alteraciones
- Respeto por privacidad: el usuario solo ve info a la que tiene permiso
- Retención de históricos según política interna, con soporte para auditoría externa
- Acceso a reportes críticos solo previa autenticación reforzada

---

## 🖥️ Ejemplo de interfaz: Dashboard de reportes

```
┌────────────────────────────────────────────────────┐
│         📈 Tablero de Reportes Operativos          │
├────────────────────────────────────────────────────┤
│ Servicios atendidos mes:   104                     │
│ T. prom. cierre (h):       2.8                     │
│ NPS Cliente:               92                       │
│ Excedente facturado:    $27,364                    │
│ Stock crítico (pieza):    Toner 3210D - 4 unidades │
│ ...                                                │
│ [ Descargar Excel ]   [ Enviar PDF ]   [ Filtros ] │
└────────────────────────────────────────────────────┘
```

---

## 👤 Roles y acceso

| Rol           | ¿Qué reportes accede?                                |
|---------------|-----------------------------------------------------|
| Administrador | Todos, incluidos programados y auditoría            |
| Supervisor    | Todos operativos, técnicos, personal, inventario    |
| Coordinadora  | Operativos/técnicos de su equipo y clientes propios |
| Cliente       | Solo propios, acceso desde portal y exportaciones   |

---

## 🔗 Integración con otros módulos

| Módulo        | Relación                                 |
|---------------|------------------------------------------|
| Servicios     | Operativos, tiempos, incidencias         |
| Inventario    | Movimientos, alertas, reconstrucciones   |
| Máquinas      | Técnicos, refacciones, consumos, fallas  |
| Personal      | Asistencia, turnos, rondas, permisos     |
| Notificaciones| Seguimiento de alertas, entregas         |
| Portal Cliente| Historial, facturación y cobertura       |
| Mapas         | Cobertura y georreferencia de datos      |
| Chat          | Seguimiento por servicio/comunicación    |
| Contadores    | Lecturas, excedentes, facturación        |

---

[← Anterior: Portal Cliente](12-PORTAL-CLIENTE.md) | [Inicio](../README.md) | [Siguiente: Extras →](14-EXTRAS.md)