# Use

Es el import o el include de Python o C/C++ o cualquier lenguaje que se te ocurra (pudiendo usar algo estándar van y hacen el use por la cara).

```rust, ignore
use crate::MOD::FUNC; // una función/elemento
use crate::MOD::{ // para una lista de funciones/elementos
    FUNC,
    ELEM,
    ...,
} 
use crate::MOD::*; // mételo todo papi
```

También está el `use ... as ...` para no tener que escribir las rutas completas cada vez que llames a un lo que sea
