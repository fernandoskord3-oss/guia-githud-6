# Diagrama de clases del proyecto 

Notación UML: `#` = protected, `-` = private, `+` = public. El triángulo vacío (`<|--`) representa la relación "es un".

Elementos abstractos: la clase *Persona* se marca con la etiqueta `<<abstract>>` y sus métodos abstractos (*calcularBeneficioAnual()* y *describirActividad()*) se dibujan en cursiva, que es la convención UML para lo abstracto.

```mermaid
classDiagram
    class Persona {
        <<abstract>>
        #String nombre
        #String dui
        +presentarse() String
        +calcularBeneficioAnual()* double
        +describirActividad()* String
    }
    class Cliente {
        -String telefono
        -double comprasAnuales
        +calcularBeneficioAnual() double
        +describirActividad() String
    }
    class Empleado {
        -double salario
        +calcularBeneficioAnual() double
        +describirActividad() String
    }
    class Estudiante {
        -String carnet
        -String carrera
        -double promedio
        +calcularBeneficioAnual() double
        +describirActividad() String
    }
    class Docente {
        -String especialidad
        -int aniosExperiencia
        +impartirClase(String materia) void
        +calcularBeneficioAnual() double
        +describirActividad() String
        +toString() String
    }
    class Voluntario {
        -double horasServicio
        +calcularBeneficioAnual() double
        +describirActividad() String
        +toString() String
    }
    class Proveedor {
        -double montoFacturado
        +calcularBeneficioAnual() double
        +describirActividad() String
        +toString() String
    }

    Persona <|-- Cliente
    Persona <|-- Empleado
    Persona <|-- Estudiante
    Persona <|-- Docente
    Persona <|-- Voluntario
    Persona <|-- Proveedor
```

## Resumen de la jerarquía

| Clase | Relación | Atributos propios | Implementa los métodos abstractos |
|---|---|---|---|
| *Persona* (abstracta) | Superclase | `#nombre`, `#dui` | Los declara: *calcularBeneficioAnual()*, *describirActividad()* |
| `Cliente` | es una `Persona` | `telefono`, `comprasAnuales` | Sí |
| `Empleado` | es una `Persona` | `salario` | Sí |
| `Estudiante` | es una `Persona` | `carnet`, `carrera`, `promedio` | Sí |
| `Docente` | es una `Persona` | `especialidad`, `aniosExperiencia` | Sí |
| `Voluntario` | es una `Persona` | `horasServicio` | Sí |
| `Proveedor` | es una `Persona` | `montoFacturado` | Sí |