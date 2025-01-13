# Soluciones propuestas a los ejercicios de diagramas de clases

## Web de deportes

El periódico digital "Marca" quiere desarrollar un sistema para gestionar su contenido relacionado con deportes, equipos, competiciones y noticias. Este sistema permitirá a los administradores de la web organizar y actualizar la información de manera eficiente, y a los usuarios disfrutar de un acceso estructurado a las noticias y datos deportivos.

Requisitos:

- Deportes y competiciones: La web cubre diferentes deportes como fútbol, baloncesto, tenis, entre otros. Cada deporte tiene una lista de competiciones asociadas (por ejemplo, LaLiga, NBA, Roland Garros). En cada deporte, debemos poder consultar el número de competiciones vinculadas. Para cada competición, debemos poder agregar un equipo y listar los equipos participantes.
- Equipos y jugadores: cada competición tiene varios equipos participantes. Un equipo tiene atributos como nombre, ciudad y estadio.
Cada equipo tiene una plantilla de jugadores, con información como nombre, posición, número de camiseta y estadísticas (goles, asistencias, etc.). Cada equipo debe permitir añadir y eliminar jugadores de su plantilla, así como consultar las estadísticas agregadas de todos los jugadores. De cada jugador nos interesa también poder acceder a sus estadísticas específicas.
- Noticias: el sistema debe permitir gestionar noticias relacionadas con deportes, equipos o jugadores específicos. Cada noticia tiene un título, un contenido, una fecha de publicación y etiquetas relacionadas (por ejemplo, "Fútbol", "Real Madrid"). Una noticia puede referirse a múltiples equipos o jugadores. Debemos poder añadir o eliminar las etiquetas de una noticia.
- Usuarios y comentarios: Los usuarios pueden registrarse en la web para comentar en las noticias. Un usuario tiene atributos como nombre, correo electrónico, contraseña y fecha de registro. Cada comentario pertenece a un usuario y a una noticia específica, y tiene una fecha y contenido. Un usuario debe poder eliminar un comentario realizado.
- Funciones de Administración: los administradores pueden añadir o eliminar deportes, competiciones, equipos, jugadores y noticias.
Los administradores tienen atributos como nombre, correo y rol. 
- Operaciones esperadas del sistema:
  - Listar noticias por deporte, equipo o jugador.
  - Buscar noticias por palabra clave en el título o contenido.
  - Mostrar estadísticas de un equipo o jugador específico.
  - Gestionar usuarios (añadir, editar, eliminar) y comentarios ofensivos.

Tarea: diseña un diagrama de clases UML que modele el sistema descrito. Tu modelo debe:

- Identificar las clases principales y sus atributos.
- Definir las relaciones entre las clases (asociaciones, agregaciones o composiciones según corresponda).
- Indicar la multiplicidad en cada relación.
- (Opcional) Añadir métodos principales a las clases si es relevante para clarificar su propósito.

Consideraciones:

- Piensa en la extensibilidad del sistema: ¿Cómo se podrían agregar nuevos deportes o tipos de contenido?
- Usa abstracciones si es necesario (por ejemplo, clases genéricas para contenido).
- Diseña el modelo para facilitar operaciones futuras, como estadísticas avanzadas o integración con redes sociales.

## Red social

Crear un diagrama de clases que permita modelar un sistema que sirva para simular el funcionamiento de una red social, teniendo en cuenta lo siguiente:

- Los usuarios de la red social se identifican con un identificador y una contraseña. Además, se almacena de ellos: 
  - Su nombre, apellidos, dirección, teléfono (puede tener varios teléfonos) e e-mail (el email no tiene que poder coincidir con el de otro usuario) y una foto
- Si los usuarios son celebridades, de ellos no aparecerá ni el email ni la dirección ni el teléfono.
- Los usuarios pueden tener una serie de contactos, que en realidad son otros usuarios. De cada contacto se puede almacenar un comentario que es personal y que sirve para describir al contacto.
- Los usuarios pueden organizar sus contactos en grupos de los cuales se almacena un nombre y deberemos saber los contactos que contiene. El mismo contacto puede formar parte de varios grupos.
- Además, cada usuario puede tener una lista de usuarios bloqueados a fin de que no puedan contactar con él
- Los usuarios pueden publicar en la red comentarios, los cuales se puede hacer que los vea todo el mundo, que los vea uno o varios de los grupos de contactos del usuario o bien una lista concreta de usuarios. Los comentarios pueden incluir un texto y una imagen.

## Empresa de comidas

Crear un diagrama de clases para una empresa de comidas. En la base de datos tienen que figurar:

- El nombre y apellidos de cada empleado, su dni y su número de SS además del teléfono fijo y el móvil
- Algunos empleados/as son cocineros/as. De los cocineros y cocineras anotamos (además de los datos propios de cada empleado) sus años de servicio en la empresa. 
- Hay empleados/as que son pinches. De los y las pinches anotamos su fecha de nacimiento.
- La mayoría de trabajadores no son ni pinches ni cocineros/as
- En la base de datos figura cada plato (su nombre como “pollo a la carloteña”, “bacalo al pilpil”,…), el precio del plato junto con los ingredientes que lleva. Anotamos también si cada plato es un entrante, un primer plato, segundo plato o postre
- De los ingredientes necesitamos la cantidad que necesitamos de él en cada plato y en qué almacén y estantería del mismo le tenemos. 
- Cada almacén se tiene un nombre (despensa principal, cámara frigorífica A, cámara frigorífica B…), un número de almacén y una descripción del mismo. 
- Cada estante en el almacén se identifica con dos letras y un tamaño en centímetros. Dos almacenes distintos pueden tener dos estantes con las mismas letras.
- Necesitamos también saber qué cocineros son capaces de preparar cada plato. 
- Cada pinche está a cargo de un cocinero o cocinera.
- La cantidad de ingredientes en cada estantería de un almacén se actualiza en la base de datos al instante. Si cogemos dos ajos de un estante, figurará al instante que tenemos dos ajos menos en ese estante. Es necesario por lo tanto saber los ingredientes (cuáles y en qué número) que tenemos en cada estante.

## Empresa de software

Realizar un diagrama de clases que permita modelar el sistema de información de una empresa de software atendiendo las siguientes premisas:

- La empresa crea proyectos para otras empresas. De dichas empresas se almacena el CIF, nombre, dirección y teléfono así como un código interno de empresa. 
- Los proyectos se inician en una determinada fecha y finalizan en otra. Además al planificarle se almacena la fecha prevista de finalización (que puede no coincidir con la finalización real)
- Los proyectos los realizan varios trabajadores, cada uno de ellos desempeña una determinada profesión en el proyecto (analista, jefe de proyecto, programador,…), dicha profesión tiene un código de profesión. En el mismo proyecto puede haber varios analistas, programadores,…
- Todos los trabajadores tienen un código de trabajador, un dni, un nombre y apellidos. Su profesión puede cambiar según el proyecto: en uno puede ser jefe y en otro un programador
- Se anota las horas que ha trabajado cada trabajador en cada proyecto.
- Puede haber varios proyectos que comiencen el mismo día.
- A todas las empresas les hemos realizado al menos un proyecto
- Todos los trabajadores han participado en algún proyecto
- En la base de datos, la profesión “administrador de diseño” no la ha desempeñado todavía ningún trabajador o trabajadora 

## Vuelos

Crear el diagrama de clases que permita gestionar reservas de vuelos, de modo que:

- Los clientes pueden reservar vuelos. Con la reserva se pueden reservar varias plazas, pero no poseeremos el número de asiento hasta obtener la tarjeta de embarque. En ese instante se asignará el asiento que tiene como identificación la fila, columna y la planta en la que está situado.
- Se pueden obtener tarjetas de embarque sin tener reserva
- Las tarjetas de embarque se refieren a un único cliente. De modo que aunque reserváramos nueve plazas, cada cliente podrá sacar su tarjeta de embarque indicando el número de reserva, la fecha de la misma y sus datos personales (dni, nombre, apellidos, dirección y teléfono). Además la persona que reserva debe indicar una tarjeta de crédito que quedará asociada a esa persona.
- El vuelo que se reserva tiene un código único, una fecha y una hora de salida y de llegada y un aeropuerto de salida y otro de llegada
- Los aeropuertos poseen un código único, además del nombre y la localidad y el país en el que se encuentran
- Se guarda información sobre los aviones, código y número de plazas. Los vuelos sólo les puede realizar un avión determinado, pero el mismo avión puede realizar (como es lógico) otros vuelos

## Accidentes geográficos

Realizar un diagrama de clases que sirva para almacenar información geográfica. Para ello hay que tener en cuenta:

- Se almacenan los siguientes accidentes geográficos: ríos, lagos y montañas
- De cada accidente se almacenan su posición horizontal y vertical según el eje de la tierra, además de su nombre
- De los ríos se almacena su longitud, de las montañas su altura y de los lagos su extensión
- Se almacena también información sobre cada país, su nombre, su extensión y su población
- Se desea almacenar información que permite saber en qué país está cada accidente geográfico, teniendo en cuenta que cada accidente puede estar en más de un país.

## Horario escolar

Crear un diagrama de clases que represente el funcionamiento de un centro escolar de formación profesional, teniendo en cuenta que:

- Sólo interesa llevar el control de ocupación de las aulas en el horario escolar
- El horario es de seis horas diarias y en la base de datos simplemente se anota si es la primera, segunda,… y el día de la semana del que hablamos (por ejemplo miércoles a tercera hora)
- Las asignaturas tienen un nombre, un código interno del centro y un código europeo. La misma asignatura se puede impartir en dos ciclos distintos y en ese caso tendría el mismo código europeo y nombre, pero el código interno sería distinto. Hace falta saber en qué curso del ciclo se imparte la asignatura
- Los ciclos tienen un nombre, pueden ser de grado superior,de grado medio o de iniciación profesional; además tienen otro código interno en el centro. 
- Las asignaturas en cada momento ocupan un aula, del que tenemos que almacenar un código de aula, un nombre (que no se repite), un número de aula (que tampoco se repite) y los metros que tiene. A una hora concreta de la semana, el aula puede estar vacia o bien ocuparse, pero sólo se puede ocupar por una asignatura
- Necesitamos saber y anotar en la base de datos si una asignatura requiere que antes se hayan aprobado otras, para poder matricularse en ella. Por ejemplo, **Ampliación de Matemáticas de 2º** a lo mejor requiere aprobar **Matemáticas de 1º**. Puede requerirse terminar más de una asignatura previamente para poder matricularse de una concreta.
- Se entiende que la asignatura sólo la puede impartir un profesor en todo el año, siempre será uno en todo momento el titular
- De los profesores se almacena su nombre, dirección, teléfono, email, DNI, nº de Seguridad Social y un código interno de profesor así como los años que tiene de antigüedad impartiendo cada asignatura. Puede ser cada profesora o profesor, tutora de un curso y también se anota la antigüedad que tiene en esa tarea

Complicamos el esquema anterior en este sentido

- Siendo más realistas, nos damos cuenta de que en un curso escolar, puede haber varios profesores responsables de una asignatura (por bajas, ceses, etc.); por lo que anotamos cuándo empezó a impartir dicho profesor la asignatura y cuando terminó (si no ha terminado, se dejaría vacío)
- Asegurar que podemos averiguar gracias al diseño, que si buscamos a un profesor un día concreto (por ejemplo el 13 de Mayo de 2012\) a una hora concreta (sexta hora), podríamos saber en qué aula va a estar.

## Inmuebles

Crear un diagrama de clases que permita modelar un sistema que sirva para gestionar una empresa que posee inmuebles.  Para ello 

- Se almacenan los clientes usando su DNI, Teléfono fijo, Móvil, Nombre y Apellidos.
- Se almacenan los trabajadores y se almacenan los mismos datos. Ocurre además que un trabajador puede ser un cliente (porque puede alquilar o comprar mediante la inmobiliaria) a veces.
- A cada cliente y trabajador se le asigna un código personal
- Los clientes pueden comprar pisos, locales o garajes. En los tres casos se almacena un código de inmueble (único para cada inmueble), los metros que tienen, una descripción y su  dirección. 
- Los pisos tienen un código especial de piso que es distinto para cada piso. 
- En los locales se indica el uso que puede tener y si tienen servicio o no.
- De los garajes se almacena el número de garaje (podría repetirse en distintos edificios) y la planta en que se encuentra (para el caso de garajes que están en varias plantas). Los garajes además pueden asociarse a un piso y así cuando se alquile el piso se incluirá el garaje.
- La empresa prevé que podría haber inmuebles que podrían no ser ni locales, ni garajes, ni pisos
- Los inmuebles se pueden comprar. Incluso varias veces. Se asigna un código de compra cada vez que se haga, la fecha y el valor de la compra. La compra puede tener varios titulares. 
- Cada inmueble se puede alquilar y en ese caso se asigna un número de alquiler por cada inmueble. Ese número se puede repetir en distintos inmuebles (es decir puede haber alquiler nº 18 para el inmueble 40 y el 35). Pero no se repite para el mismo inmueble.
- Al alquilar queremos saber el nombre del agente de la empresa que gestionó el alquiler así como a qué persona (solo una) estamos alquilando el inmueble.
- Cada pago de cada alquiler será almacenado en la base de datos, llevando el año, el mes y el valor del mismo. 

## Olimpiadas

Las sedes olímpicas se dividen en complejos deportivos. Los complejos deportivos se subdividen en aquellos en los que se desarrolla un único deporte y en los polideportivos. Los complejos polideportivos tienen áreas designadas para cada deporte con un indicador de localización (ejemplo: centro, esquinaNE, etc.). Un complejo tiene una localización, un jefe de organización individual y un área total ocupada.

Los dos tipos de complejos (deporte único y polideportivo) tendrán diferentes tipos de información. Para  cada tipo de sede, se conservará el número de complejos junto con su presupuesto aproximado.

Cada complejo celebra una serie de eventos (ejemplo: la pista del estadio puede celebrar muchas carreras distintas.). Para cada evento está prevista una fecha, duración, número de participantes, número de comisarios. Una lista de todos los comisarios se conservará junto con la lista de los eventos en los que esté involucrado cada comisario ya sea cumpliendo la tarea de juez u observador. Tanto para cada evento como para el mantenimiento se necesitará cierto equipamiento (ejemplo: arcos, pértigas, barras paralelas, etc).
