# ⏰ Módulo de Personal (Horarios y Asistencia)

> Control de horarios, asistencia, turnos, registros de entrada/salida y reportes de equipo de trabajo.

---

## 📋 ¿Qué incluye este módulo?

- Registro de jornadas, turnos y asistencia por usuario (coordinadoras, técnicos, inventario)
- Control de entrada y salida (por GPS, código QR o botón)
- Estadística de puntualidad y ausencias
- Gestión de roles y tipo de jornada por perfil
- Rotación de sábado para técnicos
- Permisos especiales, justificaciones y ausencias
- Notificaciones de retardos y ausencias
- Reporte histórico por usuario y por equipo

---

## 🗂️ Estructura de Personal

| Campo                | Tipo       | Obligatorio | Descripción                              |
|----------------------|------------|:-----------:|------------------------------------------|
| Usuario              | Selector   | ✅          | Nombre o identificador interno           |
| Rol                  | Selector   | ✅          | Técnico, coordinadora, inventario, etc   |
| Jornada asignada     | Selector   | ✅          | Horario estándar                        |
| Fecha                | Fecha      | ✅          | Día de operación                         |
| Hora entrada         | Hora       | ✅          | Captura automática/manual                |
| Hora salida          | Hora       | ✅          | Captura automática/manual                |
| Método registro      | Selector   | ✅          | GPS, QR, manual                          |
| Ubicación registro   | Texto/GPS  | ✅          | Dónde se realizó                         |
| Estado asistencia    | Selector   | ✅          | Presente, retardo, falta, permiso        |
| Justificación        | Texto      | ❌         | Adjunta evidencia o comentario           |

---

## 🔄 Flujo de registro de asistencia

```
1. El usuario llega y marca entrada vía App (botón, QR en puerta o validación GPS)
2. El registro almacena fecha/hora, método y ubicación
3. El sistema compara con la hora de jornada asignada
   ├── Si es puntual: “Presente”
   ├── Si es tarde: “Retardo” (+ notificación)
   └── Si no hay registro, marca “Falta” al final del día
4. Al salir, registra la salida (opcional para coordinadoras)
5. La coordinación puede justificar ausencias y permisos
```

---

## 📅 Jornadas y Rotaciones

### Ejemplo de configuración:
- **Coordinación:** Lunes a viernes, 8:00 a 18:00
- **Personal inventario:** Lunes a viernes, 8:00 a 18:00
- **Técnicos:** Lunes a viernes, 8:00 a 18:00
    - Sábado: Solo la mitad del equipo, jornada reducida
    - Rotación automática para sábados

**Vacaciones, incapacidades y permisos se justifican desde la App con aprobación del supervisor.**

---

## 📊 Estadísticas y Reportes

- Panel individual con resumen mensual de asistencias, faltas y retardos
- Panel de supervisor con vista de todo el equipo
- Filtros por mes, rango de fechas, usuario y rol
- Exportación en PDF y Excel

_Ejemplo tabla de asistencia:_

| Día          | Entrada | Salida | Estado      | Justificación         |
|--------------|---------|--------|-------------|----------------------|
| 10/12/2025   | 08:01   | 18:08  | Presente    | -                    |
| 09/12/2025   | 08:24   | 18:03  | Retardo     | “Tráfico”            |
| 08/12/2025   | -       | -      | Falta       | “Enfermedad (just)”  |
| ...          | ...     | ...    | ...         | ...                  |

---

## ⚠️ Notificaciones

- Al usuario: cuando tiene retardo o falta
- A coordinación y supervisor: resúmenes automáticos y alertas configurables
- Informa si un técnico no marca salida

---

## 👤 Roles del módulo

| Rol           | Funcionalidad                                                                                 |
|---------------|----------------------------------------------------------------------------------------------|
| Empleado      | Marcar entrada/salida, ver historial propio, justificar faltas                               |
| Coordinadora  | Ver y justificar asistencias del equipo, aprobar/denegar permisos, revisar reportes          |
| Supervisor    | Todas las funciones, ajustar jornadas, exportar reports, monitoreo en tiempo real            |

---

## 📲 Integración con otros módulos

| Módulo        | Relación                                 |
|---------------|------------------------------------------|
| Servicios     | Técnicos solo pueden iniciar servicio si marcaron entrada|
| Notificaciones| Alertas automáticas                      |
| Usuarios      | Sincroniza alta/baja y rol en Personal   |

---

## 🖥️ Ejemplo de interfaz

### Panel personal
```
┌──────────────────────────────────────────────┐
│      Mi Asistencia —  Dic 2025               │
├────────────┬───────┬───────┬────────┬───────┤
│   Día      │ Ent.  │ Sal.  │ Estado │ Obs.  │
├────────────┼───────┼───────┼────────┼───────┤
│ 10/dic/25  │ 08:01 │ 18:08 │ P      │ -     │
│ 09/dic/25  │ 08:24 │ 18:03 │ R      │ “Tránsito” │
│ 08/dic/25  │ -     │ -     │ F      │ “Enfermo”  │
└────────────┴───────┴───────┴────────┴────────────┘
```

---

[← Anterior: Contadores](07-MODULO-CONTADORES.md) | [Inicio](../README.md) | [Siguiente: Chat →](09-MODULO-CHAT.md)