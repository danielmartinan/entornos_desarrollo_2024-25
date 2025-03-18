# MkDocs: Guía Completa para Documentación

- [1. MkDocs: Guía Completa para Documentación](#1-mkdocs-guía-completa-para-documentación)
  - [1.1. ¿Qué es MkDocs?](#11-qué-es-mkdocs)
- [2. Preparación del Entorno](#2-preparación-del-entorno)
  - [2.1. Requisitos Previos](#21-requisitos-previos)
  - [2.2. Instalación](#22-instalación)
- [3. Estructura de Proyecto](#3-estructura-de-proyecto)
  - [3.1. Crear Nuevo Proyecto](#31-crear-nuevo-proyecto)
  - [3.2. Estructura de Directorios](#32-estructura-de-directorios)
- [4. Configuración Básica](#4-configuración-básica)
  - [4.1. Archivo mkdocs.yml](#41-archivo-mkdocsyml)
- [5. Creación de Contenido](#5-creación-de-contenido)
  - [5.1. Escribir en Markdown](#51-escribir-en-markdown)
- [6. Comandos Principales](#6-comandos-principales)
  - [6.1. Desarrollo Local](#61-desarrollo-local)
  - [6.2. Construcción del Sitio](#62-construcción-del-sitio)
- [7. Despliegue](#7-despliegue)
  - [7.1. Opciones de Hosting](#71-opciones-de-hosting)
- [8. Características Avanzadas](#8-características-avanzadas)
  - [8.1. Plugins Útiles](#81-plugins-útiles)
  - [8.2. Personalización](#82-personalización)
  - [8.3. Plugins](#83-plugins)

## 1. MkDocs: Guía Completa para Documentación

### 1.1. ¿Qué es MkDocs?

MkDocs es una herramienta de código abierto que permite crear sitios web estáticos a partir de archivos Markdown.

- Generador de sitios web estáticos para documentación
- Convierte archivos Markdown en sitios web profesionales
- Especialmente útil para proyectos de desarrollo web

En los siguientes apartados se detallan los pasos para crear y desplegar un sitio web con MkDocs.

## 2. Preparación del Entorno

### 2.1. Requisitos Previos

- Python (versión 3.7+)
- pip (gestor de paquetes de Python)

### 2.2. Instalación

```bash
# Verificar instalación de Python
python --version

# Instalar MkDocs y tema Material
pip install mkdocs mkdocs-material
```

## 3. Estructura de Proyecto

### 3.1. Crear Nuevo Proyecto

```bash
# Crear directorio de proyecto
mkdocs new proyecto-documentacion
cd proyecto-documentacion
```

### 3.2. Estructura de Directorios

```plaintext
proyecto-documentacion/
│
├── mkdocs.yml       # Archivo de configuración principal
└── docs/            # Carpeta de documentos Markdown
    └── index.md     # Página de inicio
```

## 4. Configuración Básica

### 4.1. Archivo mkdocs.yml

`yaml` es un formato de serialización de datos legible por humanos. Es comúnmente usado para configuraciones y archivos de metadatos. Se utiliza en múltiples escenarios, como archivos de configuración, intercambio de datos y almacenamiento de información.

En mkdocs.yml se configuran aspectos como el nombre del sitio, la descripción, el autor y el tema.

```yaml
# Configuración básica
site_name: Mi Documentación
site_description: Documentación del Proyecto
site_author: Tu Nombre

# Tema
theme:
  name: material
  language: es
  
# Navegación
nav:
  - Inicio: index.md
  - Guía: guia.md
  - Referencia: referencia.md
```

## 5. Creación de Contenido

### 5.1. Escribir en Markdown

- Usar archivos `.md` en la carpeta `docs/`
- Sintaxis Markdown estándar
- Ejemplo de `index.md`:

```markdown
# Bienvenido

## Introducción
Esta es mi primera documentación con MkDocs.

### Características
- Fácil de usar
- Basado en Markdown
- Personalizable
```

## 6. Comandos Principales

### 6.1. Desarrollo Local

```bash
# Iniciar servidor de desarrollo
mkdocs serve
# Acceder en http://127.0.0.1:8000/
```

### 6.2. Construcción del Sitio

```bash
# Generar sitio web estático
mkdocs build
# Genera sitio en directorio 'site/'
```

## 7. Despliegue

### 7.1. Opciones de Hosting

1. GitHub Pages

    Para poder desplegar en GitHub Pages, es necesario configurar el repositorio en GitHub y habilitar GitHub Pages en la configuración del repositorio.

    - Crear un nuevo repositorio en GitHub. Es importante que lo crees como público.
    - Puedes desplegar directamente con el comando `mkdocs gh-deploy`.

    ```bash
    # Desplegar directamente
    mkdocs gh-deploy
    ```

    Esto creará una rama `gh-pages` en tu repositorio y desplegará el sitio web en GitHub Pages.

    - Ve a la configuración de tu nuevo repositorio en GitHub:

        ![Configuracion_repositorio](img/ed06_2_configuracion_repositorio.png)

    - Navega a la sección "Pages". Configura la fuente como "gh-pages".
    - Accede a tu sitio web en `https://tu-usuario.github.io/tu-repositorio`.
  
2. Otros servicios

- Netlify
- Vercel
- Cualquier servicio de hosting estático

## 8. Características Avanzadas

### 8.1. Plugins Útiles

- `mkdocs-material`: Tema moderno que ofrece una apariencia profesional y muchas opciones de personalización.
- `mkdocs-pdf-export`: Permite exportar la documentación a formato PDF, útil para compartir o imprimir.
- `mkdocs-versioning`: Facilita la gestión de diferentes versiones de la documentación, ideal para proyectos que evolucionan rápidamente.
- `mkdocs-mermaid2`: Añade soporte para diagramas de Mermaid, permitiendo incluir diagramas de flujo, gráficos de Gantt, entre otros.
- `mkdocs-macros-plugin`: Permite el uso de macros en los archivos Markdown, ofreciendo mayor flexibilidad y reutilización de contenido.
- `mkdocs-awesome-pages-plugin`: Facilita la organización de la navegación del sitio mediante un archivo de configuración simple.

### 8.2. Personalización

- **Añadir logos**: Puedes personalizar el sitio añadiendo logos en la configuración del tema. Esto se hace en el archivo `mkdocs.yml` bajo la sección del tema.
  
  ```yaml
  theme:
    logo: 'img/logo.png'
  ```

- **Configurar colores**: El tema `mkdocs-material` permite configurar una paleta de colores personalizada para que el sitio se ajuste a la identidad visual del proyecto.

  ```yaml
  theme:
    palette:
      primary: 'indigo'
      accent: 'pink'
  ```

- **Agregar extensiones de Markdown**: MkDocs soporta varias extensiones de Markdown que pueden ser habilitadas en el archivo de configuración para añadir funcionalidades adicionales.

  ```yaml
  markdown_extensions:
    - admonition
    - codehilite
    - toc:
        permalink: true
  ```

### 8.3. Plugins

Podemos instalar plugins para añadir funcionalidades adicionales a MkDocs. Algunos ejemplos de plugins populares son:

- `mkdocs-material`: Tema moderno y altamente personalizable.
- `mkdocs-pdf-export-plugin`: Permite exportar la documentación a formato PDF.
- `mkdocs-mermaid2-plugin`: Añade soporte para diagramas de Mermaid.

Para instalar un plugin, se puede utilizar `pip`:

```bash
pip install mkdocs-material
```

Para habilitar un plugin, se debe añadir su nombre al archivo `mkdocs.yml`:

```yaml
plugins:
  - search
  - mkdocs-material
  - mermaid2
```
