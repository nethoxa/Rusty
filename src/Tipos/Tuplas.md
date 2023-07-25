# Tuplas

Esta parte es muy sencilla. Básicamente te permiten meter y hacer lo que quieras con las tuplas. Se suelen usar como returns de funciones al permitirte meter cosas de diferentes tipos

```rust, ignore
let random = ((1u8, 2u16, "ajsdas"), (true, -1i8), 'o');
```

Para sacarlos, podemos hacer un `random.INDEX.SUBINDEX.SUBSUBINDEX...` como si fuese una matriz rara
