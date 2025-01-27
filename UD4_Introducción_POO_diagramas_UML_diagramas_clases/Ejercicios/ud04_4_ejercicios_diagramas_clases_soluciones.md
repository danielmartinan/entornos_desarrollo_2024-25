# Soluciones propuestas a los ejercicios de diagramas de clases

## Web de deportes

```mermaid
classDiagram
    %% Clases principales
    class Deporte {
        -nombre : String
        -descripcion : String
        +agregarCompetición(Competición) void
        +consultarCompeticións() List~Competición~
    }

    class Competición {
        -nombre : String
        -pais : String
        -temporada : String
        +agregarEquipo(Equipo) void
        +listarEquipos()  List~Equipo~
        +agregarJugador(Jugador) void
        +listarJugadores() List~Jugador~
    }
    class Equipo {
        -nombre : String
        -ciudad : String
        -estadio : String
        +añadirJugador(Jugador) void
        +consultarEstadisticas() Map<String, Integer>
    }
    class Jugador {
        -nombre : String
        -posicion : String
        -numero : Integer
    }
    class Noticia {
        -titulo : String
        -contenido : String
        -fechaPublicacion : Date
        -etiquetas : List~String~
        +actualizarEtiquetas(List~String~) void
    }
    class Usuario {
        -nombre : String
        -email : String
        -contraseña : String
        -fechaRegistro : Date
        +realizarComentario(Comentario) void
        +consultarHistorialComentarios() List~Comentario~
    }
    class Comentario {
        -contenido : String
        -fecha : Date
        +editarComentario(String) void
        +eliminarComentario() void
    }
    class Administrador {
        -nombre : String
        -email : String
        -rol : String
        +añadirDeporte(Deporte) void
        +eliminarDeporte(Deporte) void
        +añaadirCompetición(Competición) void
        +eliminarCompetición(Competición) void
        +añadirEquipo(Equipo) void
        +eliminarEquipo(Equipo) void
        +añadirJugador(Jugador) void
        +eliminarJugador(Jugador) void
        +publicarNoticia(Noticia) void
        +eliminarNoticia(Noticia) void
        +listarNoticias() List~Noticia~
        +buscarNoticias(String) List~Noticia~
        +actualizarSistema(String, Object) void
        +añadirUsuario(Usuario) void
        +eliminarUsuario(Usuario) void
        +editarUsuario(Usuario) void
        +eliminarComentario(Comentario) void
    }

    %% Relaciones
    Deporte "1" --> "*" Competición : contiene
    Competición "1" *-- "*" Equipo : participa
    Competición "1" *-- "*" Jugador : participa
    Equipo "1" --> "*" Jugador : contiene
    Noticia "*" --> "*" Equipo : menciona
    Noticia "*" --> "*" Jugador : menciona
    Noticia "*" --> "*" Deporte : menciona
    Usuario "1" --> "*" Comentario : realiza
    Comentario "1" --> "1" Noticia : pertenece a
    Administrador ..> Deporte : gestiona
    Administrador ..> Competición : gestiona
    Administrador ..> Equipo : gestiona
    Administrador ..> Jugador : gestiona
    Administrador ..> Usuario : gestiona
    Administrador ..> Noticia : edita
    Administrador ..> Comentario : modera

    note for Competición "O participan equipos o participan jugadores, relación exclusiva"

```

### 2. **Red Social**  

```mermaid
classDiagram
    %% Clases principales
    class UsuarioBase {
        <<abstract>>
        -id: String
        -nombre: String
        -apellidos: String
        -foto: String
        +bloquearUsuario(UsuarioBase) void
        +agregarContacto(UsuarioBase, String) void
    }

    class UsuarioEstandar {
        -direccion: String
        -telefonos: List~String~
        -email: String
    }

    class UsuarioCelebridad {
        -nombreArtistico: String
    }

    class Contacto {
        -comentario: String
    }

    class Grupo {
        -nombre: String
        +agregarContacto(Contacto) void
    }

    class Publicacion {
        -texto: String
        -imagen: String
        +restringirVisibilidad(List~UsuarioBase~) void
    }

    %% Relaciones
    UsuarioBase <|-- UsuarioEstandar : hereda
    UsuarioBase <|-- UsuarioCelebridad : hereda
    Contacto <|-- UsuarioBase
    UsuarioBase "1" --> "0..*" Contacto : tiene
    UsuarioBase "1" --> "0..*" Grupo : organiza
    Grupo "0..*" --> "1..*" Contacto : contiene
    UsuarioBase "1" --> "0..*" Publicacion : publica
    Publicacion "1" --> "0..*" UsuarioBase : visiblePara

    %% Notas
    note for UsuarioCelebridad "Celebridad no tiene email, dirección ni teléfono"
```

### 3. **Empresa de Comidas**  

```mermaid
classDiagram
    class Empleado {
        -dni: String
        -nombre: String
        -apellidos: String
        -numeroSeguridadSocial: String
        -telefonoFijo: String
        -telefonoMovil: String
    }
    class Cocinero {
        -anosServicio: int
    }
    class Pinche {
        -fechaNacimiento: Date
    }
    class Plato {
        -nombre: String
        -precio: double
        +agregarIngrediente(Ingrediente)
    }
    class Ingrediente {
        -nombre: String
        +actualizarStock(int)
    }
    class IngredientePlato {
        -cantidad: int
    }
    class Almacen {
        -nombre: String
        -numero: int
        -descripcion: String
    }
    class Estante {
        -codigo: String 
        -tamano: int
        +agregarIngrediente(Ingrediente)
        +actualizarStockIngrediente(Ingrediente, int)
        +cogerIngrediente(Ingrediente, int)
        +listarIngredientes() List~Ingrediente~
        +listarIngredientesYStock() Map~Ingrediente, int~
    }

    Empleado <|-- Cocinero
    Empleado <|-- Pinche
    Cocinero "1" --> "0..*" Pinche : supervisa
    Plato "1" --> "1..*" IngredientePlato : contiene
    IngredientePlato "1" --> "1" Ingrediente : tiene
    Almacen "1" *-- "1..*" Estante : tiene
    Estante "1" --> "0..*" Ingrediente : almacena
    Cocinero "1" --> "0..*" Plato : puedePreparar

    note for Estante "El código es de dos letras"
```

### 4. **Empresa de Software**  

```mermaid
classDiagram
    class Empresa {
        -cif: String
        -nombre: String
        -telefono: String
        -codigo: String
    }
    class Proyecto {
        -fechaInicio: Date
        -fechaPrevistaFin: Date
        -fechaFin: Date
        -horasPorTrabajador: map~Trabajador, int~
        +calcularHorasTrabajadas() int
    }
    class Trabajador {
        -codigo: String
        -dni: String
        +asignarProfesion(Profesion)
    }
    class Profesion {
        -codigo: String
        -nombre: String
    }

    Empresa "1" --> "1..*" Proyecto : contrata
    Proyecto "1" --> "1..*" Trabajador : involucra
    Trabajador "1" --> "1..*" Profesion : desempeña
    Proyecto "1" --> "1..*" Profesion : requiere

    %% Restricción
    note for Profesion "La profesión 'administrador de diseño' no ha sido desempeñada por ningún trabajador"
```

### 5. **Vuelos**

**PENDIENTE DE TERMINAR**

```mermaid
classDiagram
    class Cliente {
        -dni: String
        -tarjetaCredito: String
        +generarTarjetaEmbarque() TarjetaEmbarque
    }
    class Reserva {
        -numPlazas: int
        +asignarAsiento(Asiento)
    }
    class Vuelo {
        -codigo: String
        -fechaSalida: DateTime
        -fechaLlegada: DateTime
        +obtenerAeropuertos() Aeropuerto[]
    }
    class Aeropuerto {
        -codigo: String
        -nombre: String
        -localidad : String
        -pais: String
    }
    class Asiento {
        -fila: int
        -columna: int
        -planta: int
    }

    Cliente "1" --> "0..*" Reserva : realiza
    Reserva "1" --> "1..*" Asiento : incluye
    Vuelo "1" --> "1" Aeropuerto : sale
    Vuelo "1" --> "1" Aeropuerto : llega

    note for Vuelo "Un vuelo sale de un aeropuerto y llega a otro diferente"
    
```

### 6. **Accidentes Geográficos**

### 7. **Horario Escolar**

### 8. **Inmuebles**

### 9. **Olimpiadas**
