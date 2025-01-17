# ED04_1 Sistema de Gestión para un Concesionario de Vehículos

## Introducción

Un concesionario desea implementar un sistema informático para gestionar los vehículos, los clientes y las ventas. El sistema debe ser flexible y permitir futuras extensiones para integrar nuevas funcionalidades.
El objetivo de esta tarea es realizar el diseño de la aplicación haciendo uso de los diagramas de clase UML, siguiendo la notación específica del estándar.
A continuación, se detallan los requisitos del sistema.

## **Contexto General**

El concesionario trabaja con tres tipos de vehículos: **coches**, **motocicletas** y **camiones**. Cada tipo de vehículo tiene características comunes, como marca, modelo, precio base, y fecha de fabricación, pero también posee atributos específicos. Los **coches** tienen número de puertas y tipo de combustible. Las **motocicletas** tienen cilindrada y tipo de transmisión. Los **camiones** tienen capacidad de carga y número de ejes.

El concesionario también trabaja con diferentes **clientes**, que pueden ser **particulares** o **empresas**. Los clientes comparten algunos datos básicos como nombre, identificación (DNI o CIF), y datos de contacto. Las empresas tienen información adicional como nombre comercial y responsable de compras.

## **Funcionalidades del Sistema**

1. **Gestión de Vehículos:**  
   - Permitir agregar nuevos vehículos al inventario.  
   - Consultar vehículos disponibles filtrando por tipo o rango de precio.  
   - Calcular el precio final de un vehículo aplicando descuentos u ofertas específicas.  
2. **Gestión de Clientes:**  
   - Registrar nuevos clientes (particulares o empresas).  
   - Consultar información de clientes registrados.  
   - Identificar clientes frecuentes y asignarles un descuento fijo.  
3. **Gestión de Ventas:**  
   - Registrar una venta, asociándola a un cliente y a un vehículo.  
   - Permitir que un cliente pueda comprar múltiples vehículos en una única transacción.  
   - Registrar la fecha de la venta y calcular el monto total de la misma.  
4. **Facturación y Reportes:**  
   - Generar una factura detallada para cada venta, incluyendo los datos del cliente, los vehículos comprados, y el precio final.  
   - Calcular las ganancias mensuales del concesionario basándose en las ventas registradas.

## **Requisitos Técnicos**

- **Relaciones:**  
  - Los vehículos son **propiedad** del concesionario.  
  - Cada venta está asociada a un cliente y uno o más vehículos.  
  - Los clientes particulares y empresas heredan de una clase abstracta **Cliente**.  
  - Los vehículos tienen una relación jerárquica, ya que comparten características comunes.  
- **Elementos adicionales:**  
  - Implementar una interfaz **DescuentoAplicable** con un método `calcularDescuento` que sea implementado por los clientes frecuentes.  
  - Usar atributos y métodos estáticos para llevar un conteo global del total de ventas realizadas.  
  - Incorporar métodos en las clases, como `registrarVenta` en el concesionario o `calcularPrecioFinal` en los vehículos.
  - Siguiendo las directrices de los principios SOLID, especialmente el de **responsabilidad única**, deben crearse clases con responsabilidades claras, y por tanto, debemos evitar clases con múltiples responsabilidades. Ten esto en cuenta a la hora de realizar el diseño. Puedes hacer un primer diseño y luego, hacer un refinado intentando aplicar estas técnicas.

## Instrucciones de la práctica

Realiza el diagrama de clases cumpliendo con las funcionalidades y requisitos definidos previamente. Realiza un análisis exhaustivo de los requisitos, siguiendo los [pasos sugeridos](/UD4%20-%20Introducción%20a%20POO,%20diagramas%20UML%20y%20diagramas%20de%20clases/ud04_2_notacion_uml_diagramas_clases.md/#19-cómo-crear-un-diagrama-de-clases-a-partir-de-la-descripción-de-un-problema) en los apuntes. Añade las aclaraciones que consideres necesarias mediante el uso de notas dentro del propio diagrama.

Una vez analizado el problema, realiza el diagrama en **draw.io**. Puedes hacerlo tanto en la versióon web como en la versión de escritorio, o incluso en Visual Studio Code, tal y como se define en los [apuntes](/UD4%20-%20Introducción%20a%20POO,%20diagramas%20UML%20y%20diagramas%20de%20clases/ud04_3_editores_uml.md/#).

## Preguntas de reflexión

Responde las siguientes preguntas basándote en tu solución al diagrama de clases:

- ¿Por qué es útil definir la interfaz `DescuentoAplicable` para los clientes?
- ¿Qué ventajas aporta el uso de clases abstractas (`Vehiculo` y `Cliente`) para modelar jerarquías?
- Justifica la relación empleada entre `Venta` y `Vehiculo`/`Cliente` (asociación, composición, agregación...).
- ¿Cómo el uso de interfaces y herencia mejora la extensibilidad del sistema?
- ¿Qué ventajas ofrece dividir la clase `Concesionario` en varios componentes especializados?
- ¿Cómo garantizarías que el sistema sea extensible para incluir nuevos tipos de vehículos o clientes?
- ¿Qué principios SOLID están mejor representados en este diseño y cómo?
- ¿Es recomendable o deseable representar los constructores y getters/setters de las clases en el diagrama de clases? ¿Hay casos donde esa representación tenga más sentido? Justifica si, en tu caso, has decidido incluirlos en el diagrama o no.

## Instrucciones de entrega

Una vez realizado el diagrama, **expórtalo en formato PNG**. Deberás entregar:

- Un **archivo pdf**, respondiendo a las preguntas de reflexión, y con la imagen del diagrama de clases (el PNG previo)
- El archivo .drawio generado por la aplicación

Deberás comprimir ambos archivos en uno único y con el nombre siguiendo el formato **apellidos_nombre_ED04_1.zip**

## **Puntuación Propuesta**

El ejercicio será evaluado considerando los siguientes criterios:

1. **Identificación y uso correcto de relaciones (3 puntos):**  
   - Composición (1 punto).  
   - Asociación con multiplicidad (1 punto).  
   - Herencia y uso de clases abstractas (1 punto).  
2. **Uso de interfaces y elementos estáticos (2 puntos):**  
   - Definición e implementación correcta de la interfaz (1 punto).  
   - Uso de atributos/métodos estáticos en el contexto adecuado (1 punto).  
3. **Implementación de métodos y funcionalidades (3 puntos):**  
   - Métodos adecuados en cada clase (1.5 puntos).  
   - Correcta representación de las funcionalidades del sistema (1.5 puntos).  
4. **Claridad y completitud del modelo (1 punto):**  
   - Representación clara de atributos y métodos.  
   - Inclusión de multiplicidades y anotaciones relevantes.
5. **Respuesta a las preguntas de reflexión (1 punto)**