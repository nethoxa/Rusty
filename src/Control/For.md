# For

Lo único relevante es el tema de los rangos:

```rust, ignore
// el rango va de [inicio, fin)
for i in inicio..fin {
    cositas
}

// el rango va de [inicio, fin]
for i in inicio..=fin {
    cositas
}

// recorrer cosas
for elemento in iterador {
    cositas
}
```

Respecto al caso de los iteradores, pueden ser:

- `.iter()` => &cada elemento, de manera que se puede reutilizar la colección después del bucle
- `.into_iter()` => consume la colección, por lo que desaparece después de finalizar el bucle
- `.iter_mut()` => como `.iter()` pero con la posibilidad de modificar los elementos
