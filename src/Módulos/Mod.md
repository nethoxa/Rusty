# Mod

Pudiendo hacer librerías como la gente normal y se ponen a rizar el rizo aún más. En fin.

Básicamente lo que vas a utilizar es lo siguiente:

```rust, ignore
mod MOD {
    fn FUNC(ARGS) { // función privada
        // cositas
    }
    
    pub fn FUN(ARGS) { // función pública
        // cositas
    }
    
    pub(crate) fn FUNC(ARGS) { // públicas en el crate y no fuera de él
        // cositas
    }
}
```

Si quieres mirar más, te lees la [documentación oficial](https://doc.rust-lang.org/rust-by-example/mod/visibility.html)
