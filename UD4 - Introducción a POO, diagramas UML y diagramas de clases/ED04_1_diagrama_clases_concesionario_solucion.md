# ED04_1 Sistema de Gestión para un Concesionario de Vehículos

## Solución propuesta

```mermaid
classDiagram
    %% Clases principales
    class Concesionario {
        - nombre: String
        - ubicacion: String
        + totalVentas: double
        + registrarVenta(venta: Venta): void
        + obtenerGanancias(): double
    }

    class GestorInventario {
        + buscarVehiculo(tipo: String): Vehiculo
        + agregarVehiculo(vehiculo: Vehiculo): void
        + eliminarVehiculo(vehiculo: Vehiculo): void
    }

    class GestorVentas {
        + registrarVenta(venta: Venta): void
        + calcularGanancias(): double
    }

    class GestorClientes {
        + registrarCliente(cliente: Cliente): void
        + obtenerDescuento(cliente: Cliente): double
    }

    class Vehiculo {
        <<abstract>>
        - marca: String
        - modelo: String
        - precio: double
        + obtenerDetalles(): String*
    }

    class VehiculoMotocicleta {
        - cilindrada: int
        + obtenerDetalles(): String
    }

    class VehiculoCamion {
        - capacidadCarga: double
        + obtenerDetalles(): String
    }

    class VehiculoCoche {
        - numeroPuertas: int
        + obtenerDetalles(): String
    }

    class Cliente {
        <<abstract>>
        - nombre: String
        - dni: String
        + calcularDescuento(): double
    }

    class ClienteFrecuente {
        - puntosFidelidad: int
        + calcularDescuento(): double
    }

    class ClienteOcasional {
        + calcularDescuento(): double
    }

    class Venta {
        - fecha: Date
        - vehiculo: Vehiculo
        - cliente: Cliente
        + calcularPrecioFinal(): double
    }

    class DescuentoAplicable {
        <<interface>>
        + calcularDescuento(): double
    }

    %% Relaciones
    Concesionario --> GestorInventario : "gestiona"
    Concesionario --> GestorVentas : "gestiona"
    Concesionario --> GestorClientes : "gestiona"

    GestorInventario *-- Vehiculo
    GestorClientes *-- Cliente
    GestorVentas *-- Venta

    Venta o-- Cliente : "se refiere a"
    Venta o-- Vehiculo : "se refiere a"

    Vehiculo <|-- VehiculoMotocicleta
    Vehiculo <|-- VehiculoCamion
    Vehiculo <|-- VehiculoCoche

    Cliente <|-- ClienteFrecuente
    Cliente <|-- ClienteOcasional

    ClienteFrecuente ..|> DescuentoAplicable
    ClienteOcasional ..|> DescuentoAplicable
```
