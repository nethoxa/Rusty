# Métodos

Hay dos tipos de funciones que pueden ser asignadas a un tipo random.

```rust, ignore
// funciones asociadas, las cuales no tienen porqué ser llamadas por una variable ya instanciada, por lo que se suelen usar como constructores
impl TIPO {
    fn FUNC(ARGS) -> TIPO { // si es un constructor, puede no retornar nada
        cositas    
    }
}

// métodos, que cambian las características de una variable ya instanciada
impl TIPO {
    fn FUNC(&self, ARGS) -> LQSEA {
        cositas accediendo a los elementos de la variable con self.ELEMENTO
    }
    
    fn FUNC(mut &self, ARGS) { // si queremos que se modifique a sí mismo
        cositas
    }
    
    fn FUNC(self) { // actúa como destructor al llamar a esta función
        cositas
    }
}
```
