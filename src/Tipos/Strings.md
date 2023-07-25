# Strings

Hay dos tipos de strings:

- `String`, que es un vector de `u8` codificados a UTF-8, almacenada en el heap, mutable y no termina en `\0`.
- `&str`, es un array `&[u8]` que apunta a una secuencia UTF-8 válida. Vamos, en C++ tenemos los `std::vector`, que sería en nuestro caso el `String`, mientras que el `v[i]` sería el `&str`, más o menos

Las funciones implementadas en ambas son las de siempre. En el caso de `str`:

- `.len()` => devuelve el tamaño en BYTES, no caracteres
- `.is_empty()` => `true` si tiene un tamaño de 0 bytes
- `.as_bytes()` => devuelve una secuencia de bytes, un `&[u8]`
- `.as_bytes_mut()` => lo mismo pero mutable y debe estar dentro de un `unsafe{...}`
- `.as_ptr()` => devuelve un puntero al inicio
- `.as_mut_ptr()` => lo mismo pero mutable
- `.get(INDEX)` => es la versión segura de `str[INDEX]`, devolviendo `None` en caso de OOB, mientras que en segundo caso hubiera hecho un `panic!`. Podemos ver si es `None` o no con `.is_none()` justo después
- `.get_mut(INDEX)` => lo mismo pero mutable
- `.split_at(INDEX)` => un `split` de toda la vida, está también implementado como en todos lados
- `.split_at_mut(INDEX)`
- `.chars()` => devuelve un iterador de `char`
- `.bytes()` => devuelve un iterador de `bytes`
- `.split_whitespace()` => `.split(" ")` pero teniendo en cuenta de todo, es decir, multi espacios, `\t`...
- `.lines()` => `.split("\n")` además de `\r`
- `.find(PATTERN)` => RE, caracteres, strings... pero sólo la primera ocurrencia (la última con `rfind`)
- `.matches(PATTERN)` => devuelve un iterador con todas las ocurrencias

y muchas más. En el caso de `String` son algunas de arriba con funciones típicas de los vectores. Paso de ponerlas, la verdad (hay un `.replace(str, str)` que cambia las ocurrencias del primero por el segundo). Lo importante es saber cómo inicializar los `String`, que suele ser con

```rust, ignore
let var = String::from("ahjsdgashd");
```

o haciendo un casting a un entero

```rust, ignore
let var = "543354".parse::<i32>();
```

También está el raw para no hacer escapes de caracteres especiales con `r`
