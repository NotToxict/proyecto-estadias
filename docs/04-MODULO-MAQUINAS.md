# 🖨️ Módulo de Máquinas

> Documento que describe la gestión de máquinas, códigos QR, catálogo de modelos y marcas.

---

## 📋 Descripción General

Este módulo gestiona todas las **máquinas/impresoras** de los clientes, incluyendo:
- Registro con código QR único
- Catálogo de modelos por marca
- Historial completo de servicios
- Lecturas de contadores

---

## 🏭 Marcas Disponibles

| Marca | Estado | Notas |
|-------|:------:|-------|
| **SHARP** | ✅ Activo | - |
| **XEROX** | ✅ Activo | - |
| **SAMSUNG** | ✅ Activo | - |
| **RICOH** | ⭐ Principal | Marca más usada actualmente |

---

## 📖 Catálogo de Modelos

Cada marca tiene su propio catálogo con:
- Nombre del modelo
- Tipo (Multifuncional / Impresora)
- Color (B/N / Color)
- Velocidad (ppm)
- Contadores que maneja
- Toners que usa
- Refacciones compatibles
- Manuales/documentos

---

## 📝 Datos de la Máquina

| Campo | Tipo | Obligatorio |
|-------|------|:-----------:|
| Marca | Selector | ✅ |
| Modelo | Selector | ✅ |
| Serie | Texto | ✅ |
| Cliente | Selector | ✅ |
| Ubicación | Selector | ✅ |
| Área/Departamento | Texto | ❌ |
| Código QR | Generado | ✅ |
| Estado | Selector | ✅ |

---

## 📱 Código QR

Cada máquina tiene un código QR único.

### Técnico al escanear:
- Ver información de la máquina
- Ver historial de servicios
- Iniciar nuevo reporte
- Registrar contador

### Cliente al escanear:
- Reportar problema
- Solicitar toner
- Ver tickets abiertos
- Chat con soporte

---

## 🔄 Estados de la Máquina

| Estado | Descripción |
|--------|-------------|
| 🟢 Activa | Funcionando normalmente |
| 🔴 En Reparación | Servicio en proceso |
| ⚪ Inactiva | No está en uso |
| ❌ Baja | Ya no se usa |

---

## 📊 Historial

Cada máquina guarda:
- Servicios realizados
- Refacciones usadas
- Lecturas de contador
- Cambios de toner
- Mantenimientos

---

[← Anterior: Clientes](03-MODULO-CLIENTES.md) | [Inicio](../README.md) | [Siguiente: Servicios →](05-MODULO-SERVICIOS.md)