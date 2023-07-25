# Option

Consiste en un `enum` que representa un valor por defecto `None` para indicar que algo malo ha pasado y un `Some(VALUE)` para indicar lo contrario, devolviendo el `VALUE`. Es un poco raro, así que he cogido el ejemplo de la documentación original y lo he limpiado:

```rust
fn checked_division(dividend: i32, divisor: i32) -> Option<i32> {
    if divisor == 0 {
        // Error
        None
    } else {
        // Resultado
        Some(dividend / divisor)
    }
}

fn try_division(dividend: i32, divisor: i32) {
    match checked_division(dividend, divisor) {
        None => println!("{} / {} failed!", dividend, divisor),
        Some(quotient) => {
            println!("{} / {} = {}", dividend, divisor, quotient)
        },
    }
}

fn main() {
    try_division(4, 2);
    try_division(1, 0);

    // Asignaciones a variables deben especificar el tipo esperado
    let none: Option<i32> = None;
    let _equivalent_none = None::<i32>;

    let optional_float = Some(0f32);

    // .unwrap() es para sacar el valor del Option
    println!("{:?} unwraps to {:?}", optional_float, optional_float.unwrap());

    // Si es un None, hace un panic!
    println!("{:?} unwraps to {:?}", none, none.unwrap());
}
```

Respecto a `.unwrap()`, devuelve el interior del `Option` o aborta con un `panic!`. Podemos cambiarlo a `.expect()` para que nos de un mensaje en caso de error. Se usa más con el `Result`, al poder meterle texto al `Err`. En el caso del `Option` tenemos los `?`, que devuelven el valor del `Option` o abortan LA FUNCIÓN ACTIVA y devuelven `None`.

También podemos usar `.map(CLOSURE)` para encadenar varios `.map` y sus resultados. Hacerlo secuencial y de forma funcional, vamos:

```rust, ignore
// Peel, chop, y cook secuencialmente
fn process(food: Option<Food>) -> Option<Cooked> {
    food.map(|f| Peeled(f))
        .map(|Peeled(f)| Chopped(f))
        .map(|Chopped(f)| Cooked(f))
}
```

Sin embargo, es un poco meh al ir encadenando `Option<Option<Option...>` hasta el infinito y más allá, por lo que usamos el `.and_then(FUNC)`.

Más en [1](https://doc.rust-lang.org/rust-by-example/error/option_unwrap/defaults.html)
