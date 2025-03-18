# UD6 - Optimización y Documentación

- [1. Herramientas basadas en Markdown](#1-herramientas-basadas-en-markdown)
- [2. Markdown en Github](#2-markdown-en-github)
  - [2.1. GitHub Wikis](#21-github-wikis)
    - [2.1.1. Casos de uso](#211-casos-de-uso)
    - [2.1.2. Ejemplo de uso](#212-ejemplo-de-uso)
  - [2.2. GitHub Pages](#22-github-pages)
    - [2.2.1. Características principales](#221-características-principales)
    - [2.2.2. Casos de uso](#222-casos-de-uso)
    - [2.2.3. Ejemplo de uso](#223-ejemplo-de-uso)
- [2.3. MkDocs y Sphinx](#23-mkdocs-y-sphinx)
  - [2.3.1. MkDocs](#231-mkdocs)
- [2.4. AsciiDoc vs Markdown](#24-asciidoc-vs-markdown)
  - [2.4.1. Ejemplo de AsciiDoc](#241-ejemplo-de-asciidoc)

## 1. Herramientas basadas en Markdown

Markdown es un lenguaje de marcado ligero ampliamente utilizado en documentación técnica y desarrollo de software. Su simplicidad lo hace ideal para escribir textos estructurados sin necesidad de conocimientos avanzados en HTML o LaTeX. Sin embargo, su potencial se amplía cuando se combina con herramientas que permiten gestionar, publicar y visualizar documentos de forma más avanzada.  

En este apartado se presentan diversas herramientas basadas en Markdown que facilitan la creación, organización y publicación de documentación en proyectos de software.

## 2. Markdown en Github

Como ya hemos visto en unidades didácticas previas, Github es una plataforma de desarrollo colaborativo que permite alojar proyectos de software y gestionar su ciclo de vida. Una de las características más destacadas de Github es su integración con Markdown, que permite documentar los proyectos de forma sencilla y eficaz.

Los repositorios de Github permiten incluir archivos Markdown en la raíz o en carpetas específicas, que se renderizan automáticamente en la interfaz web. Existen algunos archivos Markdown especiales que se utilizan para documentar proyectos de software:

- **README.md**: es el archivo principal de documentación de un proyecto. Suele contener una descripción general del proyecto, instrucciones de instalación y uso, ejemplos de código y enlaces a recursos adicionales.
- **CONTRIBUTING.md**: contiene información sobre cómo contribuir al proyecto, incluyendo pautas de estilo, instrucciones para enviar pull requests y normas de conducta.
- **LICENSE.md**: incluye la licencia de uso del proyecto, especificando los derechos y restricciones de distribución y modificación.
- **CHANGELOG.md**: registra los cambios realizados en cada versión del software, incluyendo nuevas funcionalidades, correcciones de errores y mejoras de rendimiento.
- **CODE_OF_CONDUCT.md**: establece las normas de conducta y convivencia en la comunidad de desarrollo, promoviendo un entorno inclusivo y respetuoso.
- **SUPPORT.md**: proporciona información sobre cómo obtener soporte técnico para el proyecto, incluyendo enlaces a la documentación, foros de discusión y canales de comunicación.
- **CONTRIBUTORS.md**: lista a los colaboradores que han contribuido al proyecto, reconociendo su trabajo y aportaciones.
- **ACKNOWLEDGEMENTS.md**: agradece a las personas, organizaciones o proyectos que han contribuido de alguna manera al desarrollo del software.
- **ISSUE_TEMPLATE.md**: define las plantillas para crear nuevos issues en el repositorio, facilitando la comunicación entre los usuarios y los desarrolladores.

Puedes encontrar más información sobre los archivos markdown más comunes en un repositorio de GitHub en la [documentación oficial de GitHub](https://docs.github.com/es/github/creating-cloning-and-archiving-repositories/creating-a-repository-on-github/about-readmes), [aquí](https://github.com/kmindi/special-files-in-repository-root/blob/master/README.md) o [aquí](https://docs.github.com/es/github/creating-cloning-and-archiving-repositories/licensing-a-repository).

### 2.1. GitHub Wikis

GitHub Wikis es una funcionalidad integrada en los repositorios de GitHub que permite a los desarrolladores documentar sus proyectos de manera estructurada utilizando Markdown. Sus características principales son:

- **Edición colaborativa**: cualquier miembro del equipo puede agregar o modificar contenido.  
- **Estructura organizada**: permite crear múltiples páginas enlazadas entre sí.  
- **Historial de cambios**: cada modificación queda registrada con control de versiones basado en Git.  
- **Accesibilidad**: la documentación es visible desde la interfaz web de GitHub.  

#### 2.1.1. Casos de uso

✅ Documentación interna del proyecto (guías de instalación, convenciones de desarrollo).  
✅ Manuales de uso y tutoriales para los colaboradores.  
✅ Registro de decisiones de diseño y cambios en el software.  

#### 2.1.2. Ejemplo de uso

Para clonar una wiki en local y editarla con Git:  

```sh
git clone https://github.com/usuario/proyecto.wiki.git
cd proyecto.wiki
echo "## Nueva página" > NuevaPagina.md
git add NuevaPagina.md
git commit -m "Añadir nueva página"
git push origin main
```

### 2.2. GitHub Pages

GitHub Pages permite publicar sitios web estáticos directamente desde un repositorio de GitHub. Es una solución ideal para alojar documentación generada en Markdown.  

#### 2.2.1. Características principales

- **Integración con Jekyll, MkDocs, Docusaurus...**: permite convertir archivos Markdown en páginas HTML estructuradas.  
- **Despliegue automático**: cualquier cambio en el repositorio se refleja en la web.  
- **Personalización**: posibilidad de añadir CSS y plantillas personalizadas.  

#### 2.2.2. Casos de uso

✅ Publicación de documentación técnica de proyectos de software.  
✅ Creación de blogs técnicos y manuales de usuario.  
✅ Alojar portfolios o sitios web personales.  

#### 2.2.3. Ejemplo de uso

Para habilitar GitHub Pages en un repositorio:  

1. Ir a `Settings > Pages`.  
2. Seleccionar la rama (`main` o `gh-pages`).  
3. Configurar el dominio si es necesario.  

Ejemplo de generación de una página usando Jekyll:  

```sh
gem install jekyll bundler
jekyll new mi-documentacion
cd mi-documentacion
bundle exec jekyll serve
```

## 2.3. MkDocs y Sphinx

MkDocs y Sphinx son generadores de documentación que permiten convertir archivos Markdown en sitios web navegables.  

### 2.3.1. MkDocs

- Diseñado para documentación técnica, especialmente en proyectos Python.  
- Ofrece plantillas predefinidas y una estructura fácil de mantener.  

## 2.4. AsciiDoc vs Markdown

AsciiDoc es un lenguaje de marcado más avanzado que Markdown, diseñado para documentación técnica compleja. Se utiliza en entornos como OpenAPI y Red Hat.  Diferencias con Markdown:

| Característica  | Markdown | AsciiDoc |
|----------------|---------|----------|
| Simplicidad   | Alta    | Media    |
| Soporte de tablas | Básico  | Avanzado |
| Extensibilidad  | Baja    | Alta     |

### 2.4.1. Ejemplo de AsciiDoc

```asciidoc
= Documentación con AsciiDoc
Autor: Juan Pérez
Fecha: 2024-06-15

== Introducción
Este es un documento en AsciiDoc.
```

[Guía completa de Mkdocs](ud6_5_mkdocs.md)