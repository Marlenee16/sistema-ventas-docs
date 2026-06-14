# Uso del sistema

Esta sección describe el flujo básico de uso del **Sistema de Ventas Simple**. El objetivo es explicar cómo un usuario puede registrar productos, administrar clientes, crear ventas y consultar reportes.

## Flujo general

El sistema se organiza en cuatro procesos principales:

1. Registro de productos.
2. Registro de clientes.
3. Registro de ventas.
4. Consulta de reportes.

!!! tip "Recomendación"
Antes de registrar una venta, verifica que el producto tenga stock disponible y que el cliente ya esté registrado en el sistema.

## Registro de productos

El módulo de productos permite guardar la información básica de los artículos disponibles para la venta.

Datos principales de un producto:

| Campo  | Descripción                | Ejemplo           |
| ------ | -------------------------- | ----------------- |
| Código | Identificador del producto | P001              |
| Nombre | Nombre del producto        | Mouse inalámbrico |
| Precio | Precio de venta            | 15.99             |
| Stock  | Cantidad disponible        | 25                |

Ejemplo de estructura de un producto:

```json
{
  "codigo": "P001",
  "nombre": "Mouse inalámbrico",
  "precio": 15.99,
  "stock": 25
}
```

## Registro de clientes

El módulo de clientes permite almacenar información básica de las personas que realizan compras.

Datos principales de un cliente:

| Campo     | Descripción                     |
| --------- | ------------------------------- |
| Nombre    | Nombre completo del cliente     |
| Teléfono  | Número de contacto              |
| Correo    | Dirección de correo electrónico |
| Dirección | Lugar de residencia o entrega   |

!!! note "Nota"
El registro de clientes ayuda a llevar un historial de compras y facilita la generación de reportes.

## Registro de ventas

Para registrar una venta, el usuario debe seleccionar un cliente, elegir uno o más productos y confirmar la operación.

Flujo básico de una venta:

| Paso | Acción                | Resultado                                        |
| ---- | --------------------- | ------------------------------------------------ |
| 1    | Seleccionar cliente   | Se asocia la venta a un cliente registrado.      |
| 2    | Agregar productos     | Se calcula el total de la venta.                 |
| 3    | Confirmar venta       | La venta queda guardada en el sistema.           |
| 4    | Actualizar inventario | Se descuenta el stock de los productos vendidos. |

## Consulta de ventas

El sistema permite consultar las ventas registradas para revisar el historial de operaciones.

Ejemplo de consulta SQL para listar ventas:

```sql
SELECT 
    id_venta,
    fecha,
    cliente,
    total
FROM ventas
ORDER BY fecha DESC;
```

## Reportes disponibles

El sistema puede generar reportes básicos para apoyar el control del negocio.

| Reporte                | Descripción                                         |
| ---------------------- | --------------------------------------------------- |
| Ventas diarias         | Muestra las ventas realizadas en un día específico. |
| Productos más vendidos | Lista los productos con mayor cantidad de ventas.   |
| Inventario bajo        | Identifica productos con poco stock disponible.     |
| Ventas por cliente     | Muestra el historial de compras por cliente.        |

!!! warning "Importante"
Si un producto no tiene stock suficiente, el sistema no debería permitir registrar la venta.

## Buenas prácticas de uso

Para mantener la información organizada, se recomienda:

* Registrar correctamente los datos de productos y clientes.
* Revisar el stock antes de confirmar una venta.
* Consultar los reportes periódicamente.
* Actualizar los precios cuando sea necesario.
* Verificar que los datos de cada venta sean correctos antes de guardarlos.

## Volver al inicio

Regresa a la página principal desde este enlace: [Inicio](index.md).
