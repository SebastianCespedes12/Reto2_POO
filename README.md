# Reto2_POO
>1.Elija un problema de la vida real (sistema de gestión de biblioteca, negocio de compra-venta, automóvil, etc) que se pueda modelar a través de objetos y clases. Plantee las relaciones de clases, composiciones, propiedades y comportamientos del sistema en uno mas diagramas tipo UML.
```mermaid
classDiagram
    class Biblioteca {
        +libros
        +usuarios 
        +prestamos
        +buscarLibro(titulo: String)
        +registrarUsuario(usuario: Usuario)
        +generarReportePrestamos()
    }

    class Libro {
        +titulo
        +autor
        +isbn
        +disponible
        +prestar()
        +devolver()
    }

    class Usuario {
        +nombre
        +id
        +prestamosActivos: List<Prestamo>
        +tomarPrestado(libro: Libro)
        +devolverLibro(libro: Libro)
    }

    class Bibliotecario {
        +registrarLibro()
        +eliminarLibro()
    }

    class Prestamo {
        +libro
        +usuario
        +fechaPrestamo
        +fechaDevolucion
        +calcular_multa_retraso()
    }

    Biblioteca *-- Libro
    Biblioteca *-- Usuario
    Biblioteca *-- Prestamo

    Prestamo <-- Usuario
    Prestamo *-- Libro

    Usuario <|-- Bibliotecario

```
Se creo un sistema de gestion de biblioteca, la cual esta compuesta por: Libros, usuarios, prestamos. El bibliotecario hereda atributos del usuario y el usuario interactua con el prestamo.
