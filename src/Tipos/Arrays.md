# Arrays

Esta parte es muy corta. Básicamente se definen como

```rust, ignore
let NOMBRE: [TIPO; TAMAÑO] = [1, 2, ...]; // con valores
let NOMBRE: [TIPO; TAMAÑO] = [VALOR; TAMAÑO]; // con un valor por defecto
```

El `sizeof()` en Rust se llama con `mem::size_of_val(&NOMBRE)` para devolver el tamaño en BYTES. Hay índices tipo `v[i]` o los `.get(INDEX)`, `.len()` para el número real de elementos...

Para los cortes tipo `[inicio:fin:step]` de Python se puede hacer `[inicio..fin]`, aunque la forma más sencilla es con

```rust
fn main() {
    let numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
    
    let sliced: Vec<_> = numbers[2..8].iter().step_by(3).copied().collect();

    println!("{:?}", sliced); // Output: [2, 5]
}
```
