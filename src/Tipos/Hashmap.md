# Hashmap

Los `dict` de Python. Se inicializan con `Hashmap::new()` y se usan de la siguiente manera:

```rust
use std::collections::HashMap;

fn main() {
    let mut hm = HashMap::new();
    
    hm.insert("HOLO", 122);
    hm.insert("SADA", 8217);
    
    hm.remove("SADA");
    
    println!("key={} y value={:?}", "HOLO", hm.get(&"HOLO").unwrap())
}
```
