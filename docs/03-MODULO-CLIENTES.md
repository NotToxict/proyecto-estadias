# 👥 Módulo de Clientes

> Documento que describe la gestión de clientes, ubicaciones y contactos.

---

## 📋 Descripción General

Este módulo permite gestionar toda la información de los **clientes** de la empresa, incluyendo sus **ubicaciones físicas** (pueden tener varias sucursales) y los **contactos** de cada ubicación.

---

## 🏗️ Estructura de Datos

Un cliente puede tener múltiples ubicaciones, y cada ubicación puede tener múltiples máquinas.

### Ejemplo Real

```
🏢 Cliente: Maquiladora XYZ
├── 📍 Ubicación: Planta Norte
│   ├── 🖨️ Ricoh MP 2555 (Recursos Humanos)
│   ├── 🖨️ Ricoh MP 3055 (Contabilidad)
│   └── 🖨️ Sharp MX-2640 (Producción)
│
└── 📍 Ubicación: Planta Sur
    ├── 🖨️ Ricoh MP 2555 (Oficinas)
    └── 🖨️ Xerox WC 7845 (Gerencia)
```

---

## 📝 Datos del Cliente

| Campo | Tipo | Obligatorio | Descripción |
|-------|------|:-----------:|-------------|
| Nombre/Razón Social | Texto | ✅ | Nombre de la empresa |
| RFC | Texto | ❌ | Para facturación |
| Giro | Texto | ❌ | Tipo de negocio |
| Teléfono Principal | Texto | ✅ | Teléfono de contacto |
| Email | Texto | ❌ | Correo electrónico |
| Notas | Texto largo | ❌ | Observaciones generales |
| Estado | Selector | ✅ | Activo / Inactivo |

### Información de Contrato (si aplica)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| Tipo de Servicio | Selector | Renta / Venta / Servicio |
| Copias Incluidas B/N | Número | Para contratos de renta |
| Copias Incluidas Color | Número | Para contratos de renta |
| Precio por Excedente B/N | Número | Costo por copia extra |
| Precio por Excedente Color | Número | Costo por copia extra |

---

## 📍 Datos de Ubicación

| Campo | Tipo | Obligatorio | Descripción |
|-------|------|:-----------:|-------------|
| Nombre de Ubicación | Texto | ✅ | Ej: "Planta Norte" |
| Dirección | Texto | ✅ | Calle y número |
| Ciudad | Selector | ✅ | De la lista de ciudades |
| Coordenadas | GPS | ❌ | Para mapa y rutas |
| Referencias | Texto | ❌ | "Frente a gasolinera" |
| Contacto Principal | Texto | ✅ | Nombre de la persona |
| Teléfono Contacto | Texto | ❌ | Teléfono directo |

---

## 🌆 Ciudades Disponibles

| Ciudad | Estado |
|--------|:------:|
| Nogales | ✅ Activo |
| Hermosillo | 🔜 Próximamente |
| Obregón | 🔜 Próximamente |
| Guaymas | 🔜 Próximamente |
| Cananea | 🔜 Próximamente |
| Agua Prieta | 🔜 Próximamente |
| Otras ciudades | 🔜 Próximamente |

---

## 🖥️ Interfaces de Usuario

### Lista de Clientes
- Búsqueda por nombre
- Filtro por ciudad
- Muestra: nombre, ubicaciones, máquinas, teléfono
- Último servicio realizado

### Detalle del Cliente
- Información general
- Datos de contrato
- Lista de ubicaciones con sus máquinas
- Historial de servicios
- Botón chat con cliente

### Formulario Nuevo/Editar
- Datos generales del cliente
- Ubicación principal
- Opción de marcar en mapa
- Datos de contacto

---

## 🔗 Relaciones con Otros Módulos

| Módulo | Relación |
|--------|----------|
| 🖨️ Máquinas | Cada máquina pertenece a una ubicación |
| 📋 Servicios | Los servicios se realizan en ubicaciones |
| 📊 Contadores | Las lecturas se registran por cliente |
| 💬 Chat | Conversación con soporte |
| 🗺️ Mapas | Coordenadas para rutas |

---

[← Anterior: Usuarios y Roles](02-USUARIOS-ROLES.md) | [Inicio](../README.md) | [Siguiente: Máquinas →](04-MODULO-MAQUINAS.md)