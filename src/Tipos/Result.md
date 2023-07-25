# Result

Esto es una alternativa al `Option` que es mucho más versátil, al permitirnos devolver un mensaje en caso de error.

- `Ok(VALUE)` => como el `Some`
- `Err(ERROR)` => que devuelve un mensaje de error hecho por nosotros

Se pueden usar con un match tipo el ejemplo de la documentación oficial:

```rust, ignore
// Ignorad el funcionamiento, sólo el uso de Ok y Err
fn op(x: f64, y: f64) -> f64 {
    match checked::div(x, y) {
        Err(why) => panic!("{:?}", why),
        
        Ok(ratio) => match checked::ln(ratio) {
            Err(why) => panic!("{:?}", why),
            
            Ok(ln) => match checked::sqrt(ln) {
                Err(why) => panic!("{:?}", why),
                Ok(sqrt) => sqrt,
            },
        },
    }
}
```

Para evitarnos escribir código similar al de arriba por cada función que devuelva `Ok/Err`, que son muchísismas, existe el operador `?`, que básicamente es lo mismo con la diferencia de que si falla, hace un `return Err(From::from(err))` que viene a ser un return anticipado, un `catch`, vamos.

Hay más ejemplos en la [documentación oficial](https://doc.rust-lang.org/std/result/index.html)
