# Documentación de pruebas

- [1. Introducción a la documentación de pruebas](#1-introducción-a-la-documentación-de-pruebas)
  - [1.1. Importancia de documentar las pruebas](#11-importancia-de-documentar-las-pruebas)
  - [1.2. Beneficios de una buena documentación](#12-beneficios-de-una-buena-documentación)
  - [1.3. Relación entre la documentación y la calidad del software](#13-relación-entre-la-documentación-y-la-calidad-del-software)
- [2. Elementos clave de la documentación de pruebas](#2-elementos-clave-de-la-documentación-de-pruebas)
  - [2.1. Plan de pruebas (Test Plan)](#21-plan-de-pruebas-test-plan)
  - [2.2. Casos de prueba (Test Cases)](#22-casos-de-prueba-test-cases)
  - [2.3. Informes de pruebas (Test Reports)](#23-informes-de-pruebas-test-reports)
  - [2.4. Trazabilidad entre requisitos y pruebas](#24-trazabilidad-entre-requisitos-y-pruebas)
- [3. Herramientas para la documentación de pruebas](#3-herramientas-para-la-documentación-de-pruebas)
  - [3.1. Herramientas de gestión de pruebas](#31-herramientas-de-gestión-de-pruebas)
  - [3.2. Integración con herramientas de desarrollo y CI/CD](#32-integración-con-herramientas-de-desarrollo-y-cicd)
  - [3.3. Documentación automatizada](#33-documentación-automatizada)
  - [3.4. Buenas prácticas en el uso de herramientas](#34-buenas-prácticas-en-el-uso-de-herramientas)
- [4. Ejemplos prácticos de documentación](#4-ejemplos-prácticos-de-documentación)
  - [4.1. Ejemplo de un caso de prueba bien documentado](#41-ejemplo-de-un-caso-de-prueba-bien-documentado)
  - [4.2. Ejemplo de un informe de pruebas](#42-ejemplo-de-un-informe-de-pruebas)
  - [4.3. Ejemplo de trazabilidad entre requisitos y pruebas](#43-ejemplo-de-trazabilidad-entre-requisitos-y-pruebas)

## 1. Introducción a la documentación de pruebas

La documentación de pruebas es un aspecto fundamental en el ciclo de vida del desarrollo de software, ya que permite registrar de manera estructurada y detallada todo lo relacionado con las actividades de pruebas. Su objetivo principal es garantizar que el proceso de testing sea transparente, reproducible y fácil de entender para todos los miembros del equipo, así como para otros stakeholders.

### 1.1. Importancia de documentar las pruebas

- **Transparencia y trazabilidad**: La documentación permite rastrear qué pruebas se han realizado, qué requisitos cubren y qué resultados se obtuvieron.  
- **Comunicación efectiva**: Facilita la comunicación entre desarrolladores, testers y otros interesados, asegurando que todos tengan acceso a la misma información.  
- **Reproducibilidad**: Permite repetir las pruebas en el futuro, lo que es especialmente útil en regresiones o al incorporar nuevos miembros al equipo.  
- **Cumplimiento de estándares**: En algunos entornos regulados (como en aplicaciones médicas o financieras), la documentación de pruebas es un requisito legal.  

### 1.2. Beneficios de una buena documentación

- Mejora la calidad del software al asegurar que no se pasen por alto aspectos críticos.  
- Reduce el tiempo de corrección de errores al facilitar la identificación de fallos.  
- Facilita la automatización de pruebas, ya que los casos de prueba bien documentados pueden convertirse en scripts de manera más eficiente.  

### 1.3. Relación entre la documentación y la calidad del software

Una documentación clara y completa contribuye directamente a la calidad del software, ya que asegura que las pruebas se realicen de manera sistemática y que los resultados sean consistentes. Además, ayuda a identificar áreas de mejora en el proceso de desarrollo.

## 2. Elementos clave de la documentación de pruebas

La documentación de pruebas debe incluir una serie de elementos esenciales que permitan cubrir todos los aspectos del proceso de testing. Estos elementos son:

### 2.1. Plan de pruebas (Test Plan)

Es el documento maestro que guía todo el proceso de testing. Incluye:

- **Objetivos**: Define qué se quiere lograr con las pruebas (por ejemplo, validar funcionalidades, detectar errores, asegurar la calidad).  
- **Alcance**: Especifica qué partes del sistema se van a probar (módulos, funcionalidades) y qué se excluye.  
- **Estrategia**: Describe los tipos de pruebas que se realizarán (unitarias, de integración, de sistema, de aceptación) y los criterios de éxito.  
- **Recursos**: Detalla los recursos necesarios, como entornos de prueba, herramientas, y el equipo involucrado.  
- **Cronograma**: Establece fechas y hitos para la ejecución de las pruebas.

### 2.2. Casos de prueba (Test Cases)

Son descripciones detalladas de cómo probar una funcionalidad específica. Cada caso de prueba debe incluir:  

- **Identificador único**: Para facilitar su referencia y trazabilidad.  
- **Descripción**: Breve explicación de lo que se va a probar.  
- **Precondiciones**: Condiciones que deben cumplirse antes de ejecutar la prueba (por ejemplo, datos de entrada o configuraciones específicas).  
- **Pasos**: Secuencia de acciones que se deben seguir para ejecutar la prueba.  
- **Datos de entrada**: Valores o configuraciones necesarias para la prueba.  
- **Resultados esperados**: Qué se espera que ocurra después de ejecutar la prueba.

### 2.3. Informes de pruebas (Test Reports)

Documentan los resultados de las pruebas ejecutadas. Deben incluir:

- **Resumen de ejecución**: Número de pruebas ejecutadas, exitosas, fallidas y omitidas.
- **Incidencias**: Errores detectados, con su nivel de severidad (crítico, alto, medio, bajo) y pasos para reproducirlos.  
- **Evidencias**: Capturas de pantalla, logs o cualquier otro elemento que respalde los resultados.  
- **Conclusiones**: Análisis general de los resultados y recomendaciones para mejorar.  

### 2.4. Trazabilidad entre requisitos y pruebas

Es fundamental mantener un vínculo claro entre los requisitos del sistema y las pruebas realizadas. Esto se logra mediante una **matriz de trazabilidad**, que es una tabla que relaciona cada requisito con los casos de prueba asociados.

## 3. Herramientas para la documentación de pruebas

Existen diversas herramientas que facilitan la creación, gestión y mantenimiento de la documentación de pruebas. Estas herramientas ayudan a automatizar tareas, mejorar la colaboración y garantizar la consistencia de la información.

### 3.1. Herramientas de gestión de pruebas

- [**TestRail**](https://www.testrail.com/): Permite crear y organizar casos de prueba, ejecutar pruebas y generar informes detallados. Se integra con herramientas como Jira y Jenkins. Cubre no solo el proceso de pruebas, sino también tareas de planificación, reportes o seguridad.
- [**Zephyr Scale**](https://marketplace.atlassian.com/apps/1213259/zephyr-scale-test-management-for-jira?tab=overview&hosting=cloud): Una extensión de Jira para la gestión de pruebas, ideal para equipos que ya usan Jira para la gestión de proyectos.  
- [**Xray**](https://marketplace.atlassian.com/apps/1211769/xray-test-management-for-jira?tab=overview&hosting=cloud): Otra herramienta integrada con Jira, enfocada en la trazabilidad entre requisitos y pruebas.  

***¿Qué es Jira?*** Jira es una herramienta de gestión de proyectos y seguimiento de incidencias desarrollada por la empresa **Atlassian**. Es ampliamente utilizada en el ámbito del desarrollo de software, aunque su flexibilidad permite adaptarla a otros tipos de proyectos. Jira está diseñada para facilitar la planificación, organización y seguimiento del trabajo en equipo, especialmente en metodologías ágiles como Scrum y Kanban.

En el contexto de desarrollo de software, Jira permite gestionar **tareas**, **requisitos**, **incidencias** (bugs) y **casos de prueba** de manera centralizada. Los equipos pueden crear "**issues**" (tareas o incidencias) para representar cualquier tipo de trabajo, desde la implementación de una nueva funcionalidad hasta la corrección de un error. Cada "issue" puede ser categorizado, priorizado y asignado a un miembro del equipo, lo que facilita la colaboración y el seguimiento del progreso.

Jira también es conocido por su integración con otras herramientas de desarrollo, como **Confluence** (para documentación), **Bitbucket** (para gestión de código) y herramientas de CI/CD como **Jenkins**. Además, cuenta con un ecosistema de plugins y extensiones, como Zephyr y Xray, que permiten gestionar pruebas de software directamente dentro de la plataforma. Esto hace de Jira una herramienta indispensable para equipos que buscan una solución integral para la gestión de proyectos y la calidad del software.

Con plugins como Zephyr o Xray, los equipos pueden crear y organizar casos de prueba, ejecutar planes de prueba y generar informes detallados. Esto permite mantener una trazabilidad completa entre los requisitos, las pruebas y las incidencias detectadas.

Por ejemplo, si un caso de prueba falla, se puede crear automáticamente una incidencia en Jira para rastrear el problema. Esta incidencia puede ser asignada a un desarrollador, quien la resolverá y la marcará como completada. Una vez resuelta, el tester puede volver a ejecutar el caso de prueba para verificar que el problema ha sido corregido. Este flujo de trabajo integrado mejora la eficiencia y la comunicación entre desarrolladores y testers.

### 3.2. Integración con herramientas de desarrollo y CI/CD
  
- **Jenkins**: Herramienta de integración continua que puede ejecutar pruebas automatizadas y generar informes.  
- **GitLab/GitHub**: Plataformas de gestión de código que incluyen funcionalidades para CI/CD y la ejecución de pruebas automatizadas.  

### 3.3. Documentación automatizada

- **Frameworks de testing**: Herramientas como JUnit (para Java) o pytest (para Python) permiten generar informes de pruebas de manera automática.  
- **Plugins y extensiones**: Por ejemplo, Allure es un framework de reporting que genera informes visuales y detallados a partir de pruebas automatizadas.  

### 3.4. Buenas prácticas en el uso de herramientas

- **Estandarización**: Usar plantillas y formatos consistentes para casos de prueba y informes.  
- **Colaboración**: Asegurar que todos los miembros del equipo tengan acceso y conozcan cómo usar las herramientas.  
- **Automatización**: Aprovechar las herramientas para automatizar la generación de informes y la ejecución de pruebas.  

## 4. Ejemplos prácticos de documentación

En esta sección, se presentan ejemplos concretos de cómo documentar diferentes elementos clave del proceso de pruebas. Estos ejemplos ayudarán a los estudiantes a entender cómo se estructura la documentación en la práctica.

### 4.1. Ejemplo de un caso de prueba bien documentado

> ---
> **Identificador**: TC-001  
> **Descripción**: Verificar que el sistema permite iniciar sesión con credenciales válidas.  
> **Precondiciones**:  
>
> - El usuario debe estar registrado en el sistema.
> - La base de datos debe estar en funcionamiento.  
>
> **Pasos**:
>
> 1. Abrir la aplicación.
> 2. Ingresar el nombre de usuario: "usuario_prueba".  
> 3. Ingresar la contraseña: "clave_segura".  
> 4. Hacer clic en el botón "Iniciar sesión".  
>
> **Datos de entrada**:
>
> - Nombre de usuario: "usuario_prueba".  
> - Contraseña: "clave_segura".  
>
> **Resultados esperados**:
>
> - El sistema redirige al usuario a la página de inicio.  
> - Se muestra un mensaje de bienvenida: "Bienvenido, usuario_prueba".
>
> ---

### 4.2. Ejemplo de un informe de pruebas

> ---
> **Resumen de ejecución**:
>
> - Pruebas ejecutadas: 50  
> - Pruebas exitosas: 45  
> - Pruebas fallidas: 3  
> - Pruebas omitidas: 2  
>
> **Incidencias detectadas**:
>
> 1. **ID**: INC-001
>    **Descripción**: El sistema no redirige al usuario después de iniciar sesión.  
>    **Severidad**: Crítica  
>    **Pasos para reproducir**:  
>    - Seguir los pasos del caso de prueba TC-001.  
>    - Observar que el sistema no redirige a la página de inicio.  
>
> 2. **ID**: INC-002
>    **Descripción**: El mensaje de bienvenida no se muestra correctamente.  
>    **Severidad**: Media  
>    **Pasos para reproducir**:
>  
>    - Seguir los pasos del caso de prueba TC-001.  
>    - Observar que el mensaje de bienvenida no aparece.  
>
> **Evidencias**:
>
> - Captura de pantalla de la pantalla de inicio de sesión.  
> - Logs del sistema que muestran el error.  
>
> **Conclusiones**:
>
> - Se detectaron 3 fallos críticos que impiden el flujo normal de la aplicación.
> - Se recomienda priorizar la corrección de la incidencia INC-001.
>
>---

### 4.3. Ejemplo de trazabilidad entre requisitos y pruebas

**Matriz de trazabilidad**:  

>---
>
> | **ID Requisito** | **Descripción del Requisito**       | **ID Caso de Prueba** | **Estado**   |
> |-------------------|-------------------------------------|-----------------------|--------------|  
> | REQ-001           | El sistema debe permitir iniciar sesión. | TC-001               | Fallido      |  
> | REQ-002           | El sistema debe mostrar un mensaje de bienvenida. | TC-001               | Fallido      |  
> | REQ-003           | El sistema debe validar credenciales incorrectas. | TC-002               | Exitoso      |
>
>---

**Explicación**:

- La matriz muestra qué requisitos están cubiertos por qué casos de prueba y su estado actual.  
- Por ejemplo, el requisito REQ-001 está cubierto por el caso de prueba TC-001, pero actualmente está marcado como "Fallido" debido a la incidencia INC-001.  
