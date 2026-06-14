# Uso del sistema

Esta sección describe el flujo básico de uso del Sistema de Ventas Simple.

## Flujo general

El sistema se organiza en tres procesos principales:

1. Registro de productos.
2. Registro de clientes.
3. Registro de ventas.

!!! tip "Recomendación"
    Antes de registrar una venta, verifica que el producto y el cliente ya existan en el sistema.

## Ejemplo de operación

Una venta básica puede seguir este flujo:

| Paso | Acción | Resultado |
| ---- | ------ | --------- |
| 1 | Registrar producto | El producto queda disponible para la venta. |
| 2 | Registrar cliente | El cliente queda guardado en el sistema. |
| 3 | Crear venta | Se registra la compra realizada. |
| 4 | Consultar reporte | Se visualiza el resumen de ventas. |

## Ejemplo de estructura de datos

Un producto puede representarse de la siguiente manera:

```json
{
  "id_producto": 1,
  "nombre": "Mouse inalámbrico",
  "precio": 15.99,
  "stock": 25
}
```

## Ejemplo de consulta SQL

Para consultar las ventas registradas:

```sql
SELECT 
    id_venta,
    fecha,
    cliente,
    total
FROM ventas
ORDER BY fecha DESC;
```

## Publicación del sitio

Para publicar la documentación en GitHub Pages, se puede ejecutar:

```bash
mkdocs gh-deploy
```

Este comando genera el sitio y lo publica en la rama `gh-pages`.

## Volver al inicio

Regresa a la página principal desde este enlace: [Inicio](index.md).