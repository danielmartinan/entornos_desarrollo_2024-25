# ED04_1  Sistema para un Videojuego de Aventura

## Introducción

Estás desarrollando un videojuego de aventuras en 2D con mecánicas clásicas (estilo Super Mario Bros, Sonic, etc). El objetivo es modelar los elementos principales del juego y sus interacciones en un diagrama de clases detallado. A continuación, se describen los requisitos del sistema:

## Mundo y Progresión

El juego se organiza en mundos, que contienen varias fases. Cada fase tiene enemigos, ítems y objetivos específicos. Al completar una fase, el personaje del jugador avanza a la siguiente, acumulando puntos y desbloqueando nuevas áreas.

### Personaje

El jugador controla un personaje, que se representa como un "muñequito" en pantalla. Este personaje tiene un nombre, una posición en la pantalla, un contador de anillos y un número de vidas.

- Cada vez que recolecta 100 anillos, gana una vida adicional, y el contador de anillos vuelve a cero.  
- El personaje puede moverse por la pantalla, recolectar ítems y enfrentar enemigos.

## Ítems

En el juego existen tres tipos principales de ítems:

- **Monedas:** Cada moneda tiene un valor en puntos que el personaje puede sumar a su puntuación. En cada fase hay un número máximo de 10 monedas. Dependiendo de cuantas monedas recoja el personaje en la fase, conseguirá más o menos puntos.  
- **Anillos:** Además de otorgar puntos, los anillos contribuyen al contador que permite ganar vidas.  
- **Power-Ups:** Estos ítems otorgan al personaje un poder especial (por ejemplo, invulnerabilidad temporal o mayor velocidad).

Cada ítem tiene una posición específica en la pantalla, y el personaje debe interactuar con ellos para recolectarlos.

## Enemigos

Los enemigos en el juego presentan desafíos para el personaje. Hay dos tipos principales: enemigos comunes y jefes.

- Los enemigos comunes tienen un nivel de dificultad y un rango de movimiento en la pantalla.  
- Los jefes son más poderosos, pueden tener habilidades especiales y, en algunos casos, subordinados (enemigos comunes) que actúan como sus protectores.  
- Los enemigos atacan al personaje reduciendo sus vidas, y al ser derrotados otorgan puntos al jugador.

## Pantalla

La pantalla del juego muestra todos los elementos visibles, como el personaje, los enemigos y los ítems.

- Cada elemento visible en la pantalla tiene una posición representada por coordenadas X e Y.  
- El sistema debe calcular la distancia entre los elementos para verificar interacciones, como recoger un ítem o ser atacado por un enemigo.  
- Todos los elementos visibles comparten propiedades comunes, como su posición en la pantalla, y deben ser modelados adecuadamente.

## Gestión de Puntos y Récords

El juego debe llevar un registro de los puntos acumulados por el jugador durante una partida.

- Se debe mantener un sistema de récords, que almacene el nombre del jugador y su mejor puntuación en cada mundo.  
- Al final de cada fase, el juego debe mostrar los puntos acumulados, los enemigos derrotados y los ítems recolectados.

## Funcionalidades Adicionales

- El personaje puede interactuar con múltiples enemigos y recolectar varios ítems durante una fase.  
- Cada fase debe registrar el progreso del jugador, incluyendo enemigos derrotados, puntos acumulados y los ítems recolectados.  
- Los cálculos de distancia entre elementos, así como la validación de interacciones, deben implementarse mediante un método reutilizable.

Este modelo debe ser lo suficientemente flexible para permitir la adición de nuevos tipos de ítems o enemigos en el futuro, así como la implementación de mecánicas avanzadas como habilidades adicionales para el personaje o nuevos modos de juego.

## Instrucciones de la práctica

Realiza el diagrama de clases cumpliendo con las funcionalidades y requisitos definidos previamente. Realiza un análisis exhaustivo de los requisitos, siguiendo los [pasos sugeridos](/UD4%20-%20Introducción%20a%20POO,%20diagramas%20UML%20y%20diagramas%20de%20clases/ud04_2_notacion_uml_diagramas_clases.md/#19-cómo-crear-un-diagrama-de-clases-a-partir-de-la-descripción-de-un-problema) en los apuntes. Añade las aclaraciones que consideres necesarias mediante el uso de notas dentro del propio diagrama.

Una vez analizado el problema, realiza el diagrama en **Visual Paradigm**. Revisa cómo generar un diagrama de clases en Visual Paradigm siguiendo [este pequeño tutorial](https://www.visual-paradigm.com/tutorials/uml-class-diagram-in-diff-programming-languages.jsp).

Una vez realizado el diagrama deberás entregar el proyecto ()

Deberás comprimir ambos archivos en uno único y con el nombre siguiendo el formato **apellidos_nombre_ED04_2.zip**

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