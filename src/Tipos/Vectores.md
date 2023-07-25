# Vectores

Hay varias formas de inicializar vectores. La primera es a través de iteradores:

```rust, ignore
let VECTOR: Vec<TIPO> = ITERADOR.collect();
```

pudiendo ser `ITERADOR` una variable random a la que se le ha hecho un `.iter()`. La segunda es con macros:

```rust, ignore
let VECTOR = vec![1, 2, 3, ...];
let VECTOR = vec![VALOR; TAMAÑO];
```
