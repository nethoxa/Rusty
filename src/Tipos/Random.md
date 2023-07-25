# Random

Existen los siguientes para los tipos de la libreria estándar, mostrándose con `println!`:

- `{}` ==> `Display` trait
- `{:?}` == `Debug` trait
- `{:x?}` == `Debug` trait con hex en minúsculas
- `{:X?}` == `Debug` trait con hex en mayúsculas
- `{:o}` == Octal
- `{:x}` == Hex en minúsculas
- `{:X}` == Hex en mayúsculas
- `{:b}` == Binario
- `{:e}` == Exponente en minúscula
- `{:E}` ==> Exponente en mayúscula 

Para poder hacer un `.toString()` de los de Java, tenemos que hacer una de dos. O bien usamos el macro `#[derive(Debug)]` y luego un `{:#?}` en el `println!` tipo

```rust
#[derive(Debug)]
struct LQSEA {
    random: u8
}

fn main() {
    let num = 12;
    let var = LQSEA {random: num};
    println!("{:#?}", var);
}
```

teniendo luego que implementar para el resto con

```rust
use std::fmt;

#[derive(Debug)]
struct LQSEA {
    random: u8
}


impl fmt::Display for LQSEA {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        // self.ELEMENTO para acceder a los elementos del struct
        // ten en cuenta que no hay un ; al final, esto es un return implícito, más o menos
        // antes de esto se pueden hacer operaciones como en cualquier función
        write!(f, "PON LO QUE QUIERAS QUE EL ELEMENTO ES {}", self.random)
    }
}


fn main() {
    let num = 12;
    let var = LQSEA {random: num};
    println!("{}", var);
}
```

o bien dejarnos de `#[derive(Debug)]` e implementar todos los formatos con `fmt::FORMAT` tal y como hemos hecho arriba
