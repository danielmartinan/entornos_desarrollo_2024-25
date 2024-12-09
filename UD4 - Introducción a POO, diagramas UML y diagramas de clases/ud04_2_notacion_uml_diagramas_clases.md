# **Clases**

Una **clase** es la unidad básica que encapsula toda la información para la representación de un conjunto de objetos que comparten características (**atributos**) y comportamientos (**métodos**).

En UML, una clase se representa con un rectángulo dividido en tres secciones:
    1.  **Nombre de la clase** (parte superior).
    2.  **Atributos** (parte intermedia).
    3.  **Métodos** (parte inferior).

**Ejemplo básico de clase en UML:**

```mermaid

classDiagram
    class Persona {
        -nombre: String
        -edad: int
        +saludar(): void
    }
```

La parte superior contiene el nombre de la clase; la parte intermedia, los atributos (que pueden no existir y, por tanto, se podrían omitir) y la parte inferior, los métodos (que también pueden no existir).

# **Atributos**

Los **atributos** son las propiedades o características que describen a una clase. Se representan en la segunda sección del rectángulo y siguen esta sintaxis:

`[visibilidad] nombre: tipo` 

-   **Visibilidades**:
    -   `+` (pública): el atributo es accesible desde cualquier clase.
    -   `#` (protegida): el atributo es accesible solo desde la clase y sus subclases.
    -   `-` (privada): el atributo es accesible solo desde la propia clase.
    -   `~` (package): el atributo es accesible desde las clases del mismo paquete.

**Ejemplo de atributos en UML (Mermaid):**

Copiar código

``` mermaid
    classDiagram
    class Persona {
        -nombre: String
        +direccion: String
        #telefono: int
    }
```

# **Métodos**

Los **métodos**, también llamados operaciones, son la implementación de un servicio de la clase que muestra un comportamiento común a todos los objetos de dicha clase. Definen cómo interactúa la clase con su entorno. Se representan en la tercera sección del rectángulo y siguen esta sintaxis:

`[visibilidad] nombre(parámetros): tipo_de_retorno` 

**Ejemplo de métodos en UML (Mermaid):**

``` mermaid
classDiagram
    class Persona {
        +saludar() void
        -calcularEdad(fechaNacimiento: Date) int
    }
```

Igual que los atributos, su visibilidad puede ser pública, privada, protegida o de paquete.

# **Relaciones**

En el mundo real, muchos objetos están vinculados o relacionados entre sí. Esas relaciones en UML muestran cómo interactúan las clases entre sí, y se denominan **asociaciones**. Las asociaciones tienen un nombre y poseen una **cardinalidad** o **multiplicidad**.

## **Asociación**

Una **asociación** representa una relación entre dos o más clases. Se dibuja como una línea simple entre las clases.

``` mermaid
classDiagram
    direction LR
    class Persona
    class Vehiculo

    Persona --  Vehiculo
```

## **Cardinalidad o Multiplicidad**

La cardinalidad especifica el número de instancias de una clase que pueden asociarse a otra. Se representa con números en los extremos de las líneas que conectan las clases.

-   **Valores comunes de multiplicidad**:
    -   `1`: Una única instancia.
    -   `0..1`: Ninguna o una instancia.
    -   `0..*` o `*`: Cero o más instancias.
    -   `1..*`: Al menos una instancia.
    -   `N..M`: Entre N y M veces.
    -   `M`: Exactamente M veces.

**Ejemplo de cardinalidad (Mermaid):**

``` mermaid
classDiagram
    direction LR

    class Persona
    class Vehiculo

    Persona "1" --> "1..*" Vehiculo
```

## **Navegabilidad**

La navegabilidad indica si una clase conoce a la otra y puede interactuar con ella. Se representa con una flecha en el extremo de la línea de asociación. De esta manera, la asociación puede ser **unidireccional** o **bidireccional**.
Si se convierte a Java dos clases unidas por una asociación bidireccional, cada una de ellas tendrá un objeto o conjunto de objetos (dependiendo de la multiplicidad entre ellas). 

**Ejemplo de asociación navegable:**

```mermaid
classDiagram
    class Persona
    class Vehiculo

    Persona "1" --> "1..*" Vehiculo: posee` 
```

## **Clase Asociación**

Cuando una relación tiene atributos propios, se puede representar como una **clase asociación**.

**Ejemplo de clase asociación:**

```mermaid
classDiagram
    class Persona
    class Vehiculo
    class Propiedad {
        -fechaAdquisicion: Date
        -precio: float
    }

    Persona "1" --> "1..*" Propiedad
    Propiedad --> Vehiculo`
```
