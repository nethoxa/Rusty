# Numéricos

Sintaxis general:

```rust
let MODIFICADOR VARIABLE: TIPO = VALOR;
```

Sin `MODIFICADOR`, la `VARIABLE` es inmutable por defecto, esto es, como un `const` en C. Por tanto, para hacerlas mutables, necesitamos el modificador `mut`. También hay `const` y `static`, siendo ambas inmutables, con la única diferencia que la primera lo es en toda la ejecución del programa y la segunda sólo en el periodo de vida inferido.

Los casting se hacen con `as TIPO`, al igual que se pueden definir nuevos tipos con `type NUEVO = VIEJO`.

Respecto a los tipos numéricos:

- Con signo -> XTAM -> `i8`, `i16`, `i32`, `i64`, `i128` y `isize`
- Sin signo -> ^^   -> `u8`, `u16`, `u32`, `u64`, `u128` y `usize`
- Flotantes -> ^^   -> `f32` y `f64`

Podemos poner `_` entre medias de los números para hacerlos más legibles sin modificar su valor:

```rust, ignore
let _var = 1_000_000;
let var = 1000000;
```

Luego tenemos los `char` que son UNICODE, ergo, 4 bytes
