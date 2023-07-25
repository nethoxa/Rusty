# Structs

Lo mismo que en C++, más o menos.

```rust
struct LQSEA {
    random: u8,
    eing: bool
}

fn main() {
    let num = 12;
    let a = false;
    let var = LQSEA {random: num, eing: a};
    println!("random={} y eing={}", var.random, var.eing);
}
```
