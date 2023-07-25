# Lazos

Para especificar que un tipo genérico tenga implementado algo tipo `Debug` o `Display`, podemos poner:

```rust, ignore
fn FUN<T: Display>(ARG: T) {
    cositas
}

fn FUNC<T: Display + Clone, U: Debug>(ARG: T, ARG: U) {
    cositas
}
```
