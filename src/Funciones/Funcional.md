# Funcional

Básicamente es ir encadenando funciones en vez de hacer cosas imperativas tipo C++. Ejemplo de la documentación oficial:

```rust, ignore
// Calcular la suma de los números impares al cuadrado por debajo de 1000
let upper = 1000;
let mut acc = 0;
for n in 0.. {
    let n_squared = n * n;
    if n_squared >= upper {
        // Break loop if exceeded the upper limit
        break;
        
    } else if is_odd(n_squared) {
        acc += n_squared;
        
    }
}

// Enfoque funcional
let sum_of_squared_odd_numbers: u32 = (0..).map(|n| n * n)                             // función a calcular
                                           .take_while(|&n_squared| n_squared < upper) // condición
                                           .filter(|&n_squared| is_odd(n_squared))     // condición
                                           .sum();                                     // suma
```
