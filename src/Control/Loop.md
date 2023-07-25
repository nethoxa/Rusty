# Loop

Es un `while(true)` pero con un nombre más yqs, son ganas de complicar aún más el vocabulario del lenguaje.

```rust, ignore
loop {
    if TECUENTO {
        break;
    
    } else {
        continue; // redundante, ya lo sé, déjame
    
    }      
}
```

Se pueden meter unos dentro de otros y les podemos asignar nombres (`lifetimes`) para romperlos desde dentro. Mira el ejemplo:

```rust, ignore
'fuera: loop {
    ...
    'dentro: loop {

        break; // rompe 'dentro
        break 'fuera; // rompe ambos
    }
}
```
