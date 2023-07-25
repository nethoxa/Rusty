# Match

Un switch, vamos.

```rust, ignore
match VAR {
    VALUE => ..., // un único valor
    VALUE | VALUE | VALUE => ..., // varios valores
    VALUE..VALUE => ..., // rangos
    _ => ... // default
}
```

Lo único interesante que tienen es la forma de acceder al `VAR` desde dentro del `match`. Hay varios casos, que los voy a sacar de la documentación oficial:

```rust, ignore
// Tuplas
match tupla {
    (0, y, z) => println!("First is `0`, `y` is {:?}, and `z` is {:?}", y, z),
    (1, ..)  => println!("First is `1` and the rest doesn't matter"),
    (.., 2)  => println!("last is `2` and the rest doesn't matter"),
    (3, .., 4)  => println!("First is `3`, last is `4`, and the rest doesn't matter"),
    _      => println!("It doesn't matter what they are"),
}


// Arrays
match array {
    [0, second, third] =>
        println!("array[0] = 0, array[1] = {}, array[2] = {}", second, third),

    // Ignoramos valores únicos con _
    [1, _, third] => println!(
        "array[0] = 1, array[2] = {} and array[1] was ignored",
        third
    ),

    [-1, second, ..] => println!(
        "array[0] = -1, array[1] = {} and all the other ones were ignored",
        second
    ),

    // Or store them in another array/slice (the type depends on
    // that of the value that is being matched against)
    [3, second, tail @ ..] => println!(
        "array[0] = 3, array[1] = {} and the other elements were {:?}",
        second, tail
    ),

    // Combining these patterns, we can, for example, bind the first and
    // last values, and store the rest of them in a single array
    [first, middle @ .., last] => println!(
        "array[0] = {}, middle = {:?}, array[2] = {}",
        first, middle, last
    ),
}


// Enums se deducen de lo de arriba
// Los structs tres cuartos de lo mismo, sólo que haciendo una inicialización rara
 match foo {
    Foo { x: (1, b), y } => println!("First of x is 1, b = {},  y = {} ", b, y),
    
    // puedes cambiar el orden
    Foo { y: 2, x: i } => println!("y is 2, i = {:?}", i),
    Foo { y, .. } => println!("y = {}, we don't care about x", y),
}
```

También se puede añadir una condición en los matches antes de los `=>`
