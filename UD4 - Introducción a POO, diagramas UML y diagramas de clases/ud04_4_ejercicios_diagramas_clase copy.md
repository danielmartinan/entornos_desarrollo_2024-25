# Ejercicios de diagramas de clases

A continuación se plantean algunos ejercicios sobre la realización de diferentes diagramas de clases para realizar el diseño de diferentes sistemas informáticos.

## Web de deportes

```mermaid
classDiagram
    %% Clases principales
    class Deporte {
        -nombre : String
        -descripcion : String
        +agregarCompetencia(Competencia) : void
        +consultarCompetencias() : List<Competencia>
    }
    class Competencia {
        -nombre : String
        -pais : String
        -temporada : String
        +agregarEquipo(Equipo) : void
        +listarEquipos() : List<Equipo>
    }
    class Equipo {
        -nombre : String
        -ciudad : String
        -estadio : String
        +añadirJugador(Jugador) : void
        +consultarEstadisticas() : Map<String, Integer>
    }
    class Jugador {
        -nombre : String
        -posicion : String
        -numero : Integer
        -estadisticas : Map<String, Integer>
        +actualizarEstadisticas(String, Integer) : void
        +consultarEstadisticas() : Map<String, Integer>
    }
    class Noticia {
        -titulo : String
        -contenido : String
        -fechaPublicacion : Date
        -etiquetas : List<String>
        +filtrarPorEquipo(Equipo) : List<Noticia>
        +actualizarContenido(String, List<String>) : void
    }
    class Usuario {
        -nombre : String
        -email : String
        -fechaRegistro : Date
        +realizarComentario(Comentario) : void
        +consultarHistorialComentarios() : List<Comentario>
    }
    class Comentario {
        -contenido : String
        -fecha : Date
        +editarComentario(String) : void
        +eliminarComentario() : void
    }
    class Administrador {
        -nombre : String
        -email : String
        -rol : String
        +publicarNoticia(Noticia) : void
        +eliminarNoticia(Noticia) : void
        +actualizarSistema(String, Object) : void
    }

    %% Relaciones
    Deporte "1" --> "*" Competencia : contiene
    Competencia "1" --> "*" Equipo : participa
    Equipo "1" --> "*" Jugador : contiene
    Noticia "*" --> "*" Equipo : menciona
    Noticia "*" --> "*" Jugador : menciona
    Usuario "1" --> "*" Comentario : realiza
    Comentario "1" --> "1" Noticia : pertenece a
    Administrador ..> Deporte : gestiona
    Administrador ..> Noticia : edita

```

## Red social

## Empresa de comidas

## Empresa de software

## Vuelos

## Accidentes geográficos

## Horario escolar

## Inmuebles

## Olimpiadas
