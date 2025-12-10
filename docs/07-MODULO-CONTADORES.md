# 07 – MÓDULO CONTADORES

## Tabla de Contenidos
1. [Introducción](#introducción)
2. [Estructuras de Datos](#estructuras-de-datos)
3. [Flujos de Trabajo](#flujos-de-trabajo)
    - [Lectura de Contadores](#lectura-de-contadores)
    - [Gestión de Excedentes](#gestión-de-excedentes)
    - [Facturación](#facturación)
    - [Alertas y Notificaciones](#alertas-y-notificaciones)
    - [Historial y Auditoría](#historial-y-auditoría)
4. [Roles y Permisos](#roles-y-permisos)
5. [Ejemplos de Vistas y Operaciones](#ejemplos-de-vistas-y-operaciones)
6. [Consideraciones Técnicas](#consideraciones-técnicas)

---

## Introducción

El módulo de contadores es responsable de la gestión, control y seguimiento de los consumos medidos por dispositivos de conteo para usuarios, permitiendo administrar lecturas, excedentes, facturación y mantener un historial confiable de las operaciones. Incluye la administración de alertas y permite que diferentes roles interactúen según permisos asignados.

---

## Estructuras de Datos

### Modelo de Contador
- `id`: Identificador único
- `usuario_id`: Usuario asignado
- `ubicacion`: Descripción breve
- `serie`: Nº de serie/dispositivo
- `tipo`: Tipo (agua, energía, etc.)
- `estado`: Operativo, fuera de servicio, etc.
- `fecha_alta`, `fecha_baja`

### Lecturas
- `id`: Identificador
- `contador_id`: Relaciona con contador
- `fecha`: Timestamp lectura
- `lectura`: Valor numérico
- `tipo_lectura`: Manual/automática
- `usuario_lectura_id`: Quién la registró
- `nota`, `evidencia` (foto/documento)

### Excedentes
- `id`, `contador_id`, `periodo`, `exceso_consumo`, `limite`, `monto_excedente`

### Facturación
- `id`, `usuario_id`, `periodo`, `consumo_total`, `monto_total`, `detalles` (desglose por concepto)

### Alertas
- `id`, `contador_id`, `tipo`, `descripcion`, `fecha`, `activo`, `resuelto` (bool)

### Historial
- Todas las operaciones clave quedan registradas para auditoría consultable guiada por usuario, fecha y tipo.

---

## Flujos de Trabajo

### Lectura de Contadores
1. **Registro de Lectura**:
    - Usuario autorizado selecciona contador y agrega valor de lectura (manual o importación automática).
    - Puede adjuntar evidencia (foto, documento).
2. **Validación**:
    - Se valida coherencia con lecturas previas para evitar errores de captura.
3. **Registro**:
    - Se almacena el registro con timestamp, usuario y evidencia.

### Gestión de Excedentes
1. **Definición de Límites**:
    - Cada contador tiene un límite configurado por periodo.
2. **Cálculo de Consumos**:
    - Al registrar lecturas, se calcula el consumo real del periodo y se compara contra el límite.
3. **Detección de Excedentes**:
    - Si el consumo supera el límite, se registra el excedente (exceso_consumo = consumo_real - límite) y se inicia el cálculo de montos asociados.
4. **Registro y Alerta**:
    - Se registra el evento de excedente y, si está configurado, se genera una alerta asociada.

### Facturación
1. **Consolidación de Consumos**:
    - Por periodo y usuario se suman los consumos validados de cada contador.
2. **Aplicación de Tarifas**:
    - Se calcula el monto base, luego los excedentes, y se suman ambos para el total facturable.
3. **Generación de Factura**:
    - El sistema emite una factura detallada (puede incluir desglose por conceptos y evidencia de lecturas).
4. **Registro y Entrega**:
    - Toda factura queda registrada, puede ser notificada vía email o disponible en el portal.

### Alertas y Notificaciones
- Generación de alertas ante:
    - Fallo de lectura / inconsistencia
    - Excedentes detectados
    - Lecturas anómalas o posibles fraudes
    - Periodos sin consumo inusual
- Configuración de recordatorios para toma de lectura y pago de facturación.

### Historial y Auditoría
- Consulta de todos los eventos clave:
    - Lecturas históricas con detalles, evidencias y modificaciones
    - Cambios en configuraciones de límites
    - Facturación y registro de pagos
    - Resolución de alertas y respuestas a las mismas

---

## Roles y Permisos

| Rol              | Acciones permitidas                                                                               |
|------------------|--------------------------------------------------------------------------------------------------|
| Administrador    | Configura contadores, define límites, accede a todos los históricos y gestiona facturas           |
| Usuario estándar | Visualiza sus contadores y consumos, registra lecturas (según configuración), accede a su factura |
| Supervisor       | Valida lecturas, monitorea alertas y excedentes, revisa reportes                                 |
| Facturación      | Accede y gestiona facturación, genera reportes históricos                                         |

---

## Ejemplos de Vistas y Operaciones

### 1. Panel de Lectura de Contadores
```
+-------------------+-----------+------------+----------+----------+
| Contador          | Última    | Lectura    | Estado   |  Acción  |
|                   | Lectura   | Actual     |          |          |
+-------------------+-----------+------------+----------+----------+
| Agua No. 121      | 10/06/25  | 12042      | OK       | Registrar|
| Energía Piso 3    | 10/06/25  | 00384      | OK       | Registrar|
+-------------------+-----------+------------+----------+----------+
```

### 2. Registro de Excedentes
```
+--------------+---------+---------+------------+--------+
| Contador     | Límite  | Actual  | Excedente  | Monto  |
+--------------+---------+---------+------------+--------+
| Agua No. 121 | 6000    | 12042   | 6042       | $904.5 |
+--------------+---------+---------+------------+--------+
```

### 3. Facturación Detallada
```
+-------+-----------+----------+-----------+-----------+
| Item  | Consumo   | Límite   | Excedente | Total $   |
+-------+-----------+----------+-----------+-----------+
| Agua  | 12042     | 6000     | 6042      | $1404,5   |
| Luz   | 384       | 350      | 34        |   $80     |
+-------+-----------+----------+-----------+-----------+
```

### 4. Historial de Lecturas y Eventos
```
+-----+-----------+----------+--------------+---------------+
| ID  | Fecha     | Valor    | Usuario      | Observaciones |
+-----+-----------+----------+--------------+---------------+
| 227 | 10/06/25  | 12042    | Juan Pérez   | Foto adjunta  |
| 228 | 09/05/25  | 11018    | Juan Pérez   | -             |
+-----+-----------+----------+--------------+---------------+
```

---

## Consideraciones Técnicas
- Todas las transacciones clave quedan auditadas en el historial.
- Los excedentes se calculan automáticamente y disparan alertas configurables.
- El sistema debe validar coherencia de lecturas y proteger contra capturas erróneas.
- El módulo permite exportación de historiales y reportes en formatos estándar (PDF, Excel).
- Todas las operaciones se asocian al usuario responsable y quedan firmadas digitalmente si se requiere.

---

**Este documento es una guía exhaustiva para el desarrollo y administración del módulo de contadores, alineada a las mejores prácticas y requerimientos regulatorios.**
