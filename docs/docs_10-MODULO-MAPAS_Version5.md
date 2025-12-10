# 🗺️ Módulo de Mapas, Rutas y Geolocalización

> Visualización, planeación, historial y reportes por ubicación de clientes, técnicos, servicios y máquinas.

---

## 📋 ¿Qué incluye este módulo?

- **Visualización de ubicaciones:** clientes, máquinas, puntos de entrega en mapa dinámico
- **Planeación y optimización de rutas** para técnicos (por horario, prioridad y cercanía)
- **Consulta rápida** de ubicación, ruta, instrucciones (Google Maps/Waze integrados)
- **Geocodificación automática**: a partir de direcciones y validación por técnico in situ
- **Historial de visitas** por técnico, cliente, máquina o dirección
- **Mapa de calor** de servicios, reportes o incidencias por zona, día, semana, etc.
- **Monitoreo en tiempo real** (si se habilita): localización activa de técnicos en ruta
- **Reportes de cobertura** y zonas de servicio
- **Integración en el módulo de servicios, clientes y logística**

---

## 🌍 Estructura y datos geográficos

| Campo                  | Tipo         | Obligatorio | Descripción                                    |
|------------------------|--------------|:-----------:|------------------------------------------------|
| Cliente/Uso            | Selector     | ✅          | Relación con cliente, servicio, máquina         |
| Dirección (calle, col) | Texto        | ✅          | Campo editable                                 |
| Ciudad                 | Selector     | ✅          | Lista predeterminada                           |
| Estado                 | Selector     | ✅          | Lista predeterminada                           |
| Código postal          | Texto        | ❌         | Opcional, ayuda precisión                      |
| Coordenadas GPS        | Lat/Lon      | ✅          | Captura automática o validación manual          |
| Referencias            | Texto        | ❌         | Ejemplo: “Portón azul”                         |
| Nivel de confianza     | Porcentaje   | ✅          | Validado automáticamente o por operador         |
| Icono/Tipo marcador    | Selector     | ✅          | Cliente, máquina, técnico, evento, etc.         |
| Última visita          | Fecha/Hora   | ❌         | Histórico de operaciones                       |

---

## 🔄 Flujos típicos de uso

### 1. Alta/Actualización de ubicación
- Al registrar cliente/ubicación/máquina se busca dirección, auto-geocodifica y sugiere ubicación en mapa
- Se puede arrastrar el pin si es necesario para colocar coordenadas exactas
- El registro guarda dirección y coordenadas
- Si el técnico visita y valida/actualiza desde su app, se marca “ubicación confirmada por visita”

### 2. Planeación y asignación de rutas técnicas
- La coordinadora selecciona tickets abiertos para el día
- El sistema sugiere ruta óptima, ordena por proximidad/hora crítica
- Se genera la ruta y se visualiza (con opción de descargar a Google Maps/Waze)
- El técnico puede seguir ruta sugerida, ver tiempo estimado, distancia y confirmar llegada desde el mapa

### 3. Mapa de servicios y cobertura
- Visualización rápida de todos los clientes/servicios activos en el mapa
- Filtros por tipo, estado, técnico asignado, rango de fechas
- Visualización de zonas calientes (concentración de reportes/incidentes)
- Exportación de reportes de cobertura o áreas de oportunidad

### 4. Historial y auditoría
- Panel por cliente/ubicación/máquina mostrando todas las visitas en el mapa, con fechas, técnicos y motivo
- Descarga de trazas en PDF/Excel

---

## 🖥️ Ejemplo de interfaz: Panel de rutas

```
┌──────────────────────────────────────────────────────────────┐
│ 🗺️ RUTAS DEL 10/Dic/2025 (Técnico: Pedro)                    │
├──────────────────────────────────────────────────────────────┤
│ Itinerario sugerido:                                          │
│ 1. Maquiladora XYZ – Planta Sur    [8:00]                     │
│ 2. Farmacia ABC – Centro           [10:30]                    │
│ 3. Hospital CIMA – Piso 2          [13:15]                    │
│ 4. Oficina SAT – Zona Industrial   [16:00]                    │
│                                                                │
│ [ Ver ruta en Google Maps ]  [ Descargar PDF de visitas ]     │
└──────────────────────────────────────────────────────────────┘
```

---

## 📊 Reportes y visualizaciones

- Clientes/mapas visitados por periodo (total, por técnico o zona)
- Concentración de incidencias para planeación de expansión o soporte
- Análisis de zonas fuera de margen/servicio/horario
- Panel supervisor para monitoreo y ajuste en tiempo real

---

## ⚠️ Privacidad y seguridad

- Solo roles autorizados pueden ver ubicación en tiempo real de técnicos
- Las localizaciones de técnicos pueden ser desactivadas fuera de horario
- Toda la actividad de geolocalización queda registrada y auditable
- Cumplimiento con políticas de privacidad y avisos internos al personal

---

## 👤 Roles y permisos

| Rol           | Permisos de mapas                                               |
|---------------|---------------------------------------------------------------|
| Técnico       | Ver rutas asignadas, marcar llegada, validar ubicación         |
| Coordinadora  | Visualizar todos los mapas, planear rutas, reasignar           |
| Supervisor    | Acceso a historial, coberturas, monitoreo general y reportes   |
| Inventario    | Ver ubicaciones para entrega/recolección específica            |
| Cliente       | Ver únicamente su(s) ubicaciones y servicios en el portal      |

---

## 🔗 Integración con otros módulos

| Módulo      | Relación                                    |
|-------------|---------------------------------------------|
| Clientes    | Ubicaciones mostradas/validadas en mapa     |
| Máquinas    | Máquinas/sucursales mostradas y localizadas |
| Servicios   | Ruta y geolocalización de atención          |
| Personal    | Tiempos/recorridos de técnicos auditados    |
| Notificaciones | Alertas por cercanía/tiempo/llegada     |

---

[← Anterior: Chat](09-MODULO-CHAT.md) | [Inicio](../README.md) | [Siguiente: Notificaciones →](11-NOTIFICACIONES.md)