# Instalación del entorno

Esta sección explica cómo preparar el entorno para ejecutar y documentar el Sistema de Ventas Simple.

## Requisitos previos

Antes de iniciar, se recomienda tener instalado:

- Python
- pip
- Git
- Visual Studio Code
- Una cuenta de GitHub

!!! warning "Importante"
    En Windows, al instalar Python, marca la opción **Add Python to PATH**. Esto permite ejecutar comandos como `python`, `pip` y `mkdocs` desde la terminal.

## Crear entorno virtual

=== "Windows"

    ```powershell
    python -m venv .venv
    .venv\Scripts\activate
    pip install mkdocs mkdocs-material pymdown-extensions
    ```

=== "macOS / Linux"

    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    pip install mkdocs mkdocs-material pymdown-extensions
    ```

## Verificar instalación

Ejecuta el siguiente comando:

```bash
mkdocs --version
```

Si todo está correctamente instalado, deberías ver la versión de MkDocs.

## Ejecutar el sitio localmente

Para visualizar la documentación en el navegador:

```bash
mkdocs serve
```

Luego abre esta dirección:

```text
http://127.0.0.1:8000
```

## Generar el sitio estático

Cuando la documentación esté lista, puedes generar la versión final con:

```bash
mkdocs build
```

Este comando crea la carpeta `site/`, donde se almacena el sitio listo para publicar.

## Siguiente paso

Después de instalar el entorno, revisa la sección de [Uso del sistema](uso.md).