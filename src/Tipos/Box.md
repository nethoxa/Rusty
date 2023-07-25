# Box

Se almacenan en el heap y tienen un funcionamiento interesante. Al ir fuera de scope, se llama a su destructor y se libera la memoria asociada de forma automática. Son los punteros de siempre, accediendo al valor con `*`:

```rust, igore
let ptr: Box<TIPO> = Box::new(TIPO);
let value = *ptr; 
```

pudiendo ser `TIPO` otro `Box<TIPO>` random a un struct o lo que sea. Es un `malloc`, más o menos. El resto de variables se almacenan en el stack
