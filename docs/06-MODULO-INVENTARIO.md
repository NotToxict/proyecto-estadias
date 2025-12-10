# 📦 Módulo de Inventario

> Gestión de piezas, stock, solicitudes, alertas y reconstrucciones.

---

## 📋 ¿Qué incluye este módulo?

- Registro y catálogo de refacciones (piezas, consumibles, fusores, tambores, etc.)
- Control de stock por marca, modelo y ubicación
- Solicitud y aprobación de piezas para servicios
- Notificaciones de stock (mínimo, crítico, agotado)
- Sugerencias automáticas de pedido
- Historial de movimientos (entradas, salidas, reconstrucciones)
- Compatibilidad con lectura por OCR y escaneo

---

## 🗂️ Estructura del inventario

| Campo                | Tipo       | Obligatorio | Descripción                                    |
|----------------------|------------|:-----------:|------------------------------------------------|
| Número de parte      | Texto      | ✅          | Identificador único de la pieza                 |
| Nombre (Descripción) | Texto      | ✅          | Ej. Fusor, Tambor                              |
| Marca                | Selector   | ✅          | Ricoh, Sharp, Xerox, Samsung                   |
| Modelos compatibles  | Texto      | ✅          | MP 2555, MP 3055, etc                          |
| Cantidad actual      | Número     | ✅          | Existencia disponible                          |
| Stock mínimo         | Número     | ✅          | Nivel para alerta de pedido                    |
| Stock crítico        | Número     | ✅          | Nivel para alerta urgente                      |
| Ubicación almacén    | Texto      | ✅          | Ej. Estante 3, Nivel 2, Caja Ricoh             |
| Estado               | Selector   | ✅          | Activo, agotado                                |
| Historial movimientos| Lista      | ✅          | Entradas, salidas, reconstrucciones            |

---

## 🔄 Flujo de Solicitud y Entrega

```
1. Técnico solicita pieza desde módulo de servicio
2. Inventario recibe solicitud
   ├── Puede aprobar, rechazar, o marcar como “Tómala directo” (con mensaje y ubicación)
3. El técnico recibe la notificación y recoge la pieza
4. Al recoger, confirma “Ya la tomé” y la pieza se descuenta del inventario
5. Todo movimiento queda registrado
```

---

## ⚠️ Sistema de stock mínimo y sugerencias

- Alertas cuando el stock llega al nivel mínimo o crítico
- Notificaciones a inventario y supervisor
- El sistema sugiere la cantidad a pedir, basada en la configuración y consumo histórico
- Permite generar reporte PDF/lista para empresa que gestiona las compras

---

## 📊 Ejemplo de Alertas

- Stock: 10 ✅ (Todo bien)
- Stock: 5 ⚠️ (Mínimo, sugerir pedido)
- Stock: 2 🔴 (Crítico, urgente)
- Stock: 0 ❌ (Agotado, no asignar en servicios)

---

## 🧾 Historial de Movimientos

Cada pieza tiene historial completo con:

| Fecha / Hora      | Tipo     | + / - | Usuario        | Motivo / Servicio            |
|-------------------|----------|-------|---------------|------------------------------|
| 10/12/2025 14:30  | Salida   | -1    | Pedro López   | Servicio #1234               |
| 09/12/2025 16:00  | Entrada  | +5    | Inventario    | Compra empresa hermana        |
| ...               | ...      | ...   | ...           | ...                          |

---

## 🔄 Reconstrucciones

- Módulo especial para piezas usadas/rehabilitadas
- Vinculado a máquina/servicio
- Segregación contable si aplica

---

## 🔗 Relación con otros módulos

| Módulo      | Relación                                         |
|-------------|--------------------------------------------------|
| Servicios   | Solicitud y consumo de piezas                    |
| Máquinas    | Compatibilidad y uso                             |
| Reportes    | Análisis de consumo, piezas más usadas, etc      |
| Notificaciones | Alertas automáticas                         |

---

[← Anterior: Servicios](05-MODULO-SERVICIOS.md) | [Inicio](../README.md) | [Siguiente: Contadores →](07-MODULO-CONTADORES.md)