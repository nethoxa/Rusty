# Enums

Seguimos para bingo. Lo bueno es que podemos hacer un `use ENUM::*` y tenemos valores más explícitos y legibles.

```rust, ignore
enum ENUM {
    Vino,
    Cerveza,
    Ginebra
}

fn main() {
    use ENUM::*;
    
    let vino = Vino;
    let cerveza = Cerveza;
}
```
