# Random

Hay una cosa que han hecho bien y es que cuando una variable sale de scope, el sistema o lo que sea libera automáticamente los recursos asignados a dicha variable de forma automática. Esto se debe al trait `Drop`, por lo que para un tipo arbitrario que hayamos definido, podemos customizar su destructor con:

```rust, ignore
impl Drop for TIPO {
    fn drop(&mut self) {
        cositas
    }
}
```
