# Ownerships

Esto otra fumada. Básicamente es que podemos copiar o mover variables, va ejemplo:

```rust, ignore
let x = 7;
let y = x; // se copia x en i, por lo que ambos se pueden usar indistintamente

let a = Box::new(5);
let b = a; // se mueve el puntero de a a b, por lo que a deja de funcionar y desaparece, o algo así
```

Básicamente es que no va a haber dos punteros apuntando a lo mismo si se han inicializado uno en función del otro (yqs).

No obstante, si se hace la asignación como una `ref`erencia, se puede seguir usando. Mira la [documentación oficial](https://doc.rust-lang.org/rust-by-example/scope/move.html) si ves que no
