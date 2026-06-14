# Instalación del sistema

Esta sección explica cómo preparar un entorno local para ejecutar el **Sistema de Ventas Simple**. El objetivo es que el usuario pueda instalar las dependencias básicas, configurar el proyecto y dejarlo listo para pruebas.

## Requisitos previos

Antes de iniciar, se recomienda tener instalado:

* Python
* pip
* Git
* Visual Studio Code
* Un navegador web

!!! warning "Importante"
En Windows, al instalar Python, se recomienda marcar la opción **Add Python to PATH**. Esto permite ejecutar comandos como `python` y `pip` desde la terminal.

## Descargar el proyecto

El primer paso consiste en clonar el repositorio del sistema desde GitHub:

```bash
git clone https://github.com/usuario/sistema-ventas-simple.git
cd sistema-ventas-simple
```

> Reemplaza `usuario` por el nombre real de la cuenta o repositorio correspondiente.

## Crear entorno virtual

Para mantener las dependencias del sistema separadas del resto del equipo, se recomienda utilizar un entorno virtual.

=== "Windows"

````
```powershell
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```
````

=== "macOS / Linux"

````
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
````

## Configurar la base de datos

El sistema puede utilizar una base de datos sencilla para almacenar productos, clientes y ventas. Como ejemplo, se puede usar SQLite para un ambiente de prueba local.

Ejemplo de estructura inicial:

```sql
CREATE TABLE productos (
    id_producto INTEGER PRIMARY KEY,
    nombre TEXT NOT NULL,
    precio REAL NOT NULL,
    stock INTEGER NOT NULL
);

CREATE TABLE clientes (
    id_cliente INTEGER PRIMARY KEY,
    nombre TEXT NOT NULL,
    telefono TEXT,
    correo TEXT
);

CREATE TABLE ventas (
    id_venta INTEGER PRIMARY KEY,
    id_cliente INTEGER NOT NULL,
    fecha TEXT NOT NULL,
    total REAL NOT NULL
);
```

## Ejecutar el sistema

Una vez instaladas las dependencias y configurada la base de datos, se puede iniciar la aplicación con el siguiente comando:

```bash
python app.py
```

Luego, el sistema estará disponible desde el navegador en la siguiente dirección:

```text
http://127.0.0.1:5000
```

## Verificar funcionamiento

Para comprobar que la instalación fue exitosa, se recomienda realizar estas pruebas básicas:

| Prueba             | Resultado esperado                               |
| ------------------ | ------------------------------------------------ |
| Registrar producto | El producto queda guardado en el inventario.     |
| Registrar cliente  | El cliente queda disponible para futuras ventas. |
| Crear venta        | La venta se almacena correctamente.              |
| Consultar reporte  | Se muestra el resumen de ventas realizadas.      |

!!! tip "Recomendación"
Antes de registrar ventas, verifica que existan productos con stock disponible y clientes registrados.

## Siguiente paso

Después de preparar el entorno, puedes continuar con la sección de [Uso del sistema](uso.md).
