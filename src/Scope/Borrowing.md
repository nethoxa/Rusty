# Borrowing

Para evitar lo dicho en [Ownerships](Ownerships.md), podemos pasar los argumentos por referencia (`&T` en vez de `T`).

```rust
fn FUNC(var: TIPO) { // le quita el dominio al caller de la variable var y la elimina al salir de la función
    cositas
}

fn FUN(var: &TIPO) { // toma una referencia y NO la destruye al salir de la función
    cositas
}
```

El caso de arriba toma referencias inmutables, por lo que para las mutables necesitamos poner `&mut TIPO`. Sin embargo, no se permiten varias referencias mutables al mismo tiempo, lo que significa que primero haces una y la cambias y luego las demás de forma secuencial.

Lo siguiente es equivalente:

```rust, ignore
let ref VAR1 = VAR2;
let VAR1 = &VAR2;
```
