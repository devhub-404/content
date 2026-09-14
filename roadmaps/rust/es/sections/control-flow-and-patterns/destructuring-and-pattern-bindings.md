# Destructuring y Pattern Bindings

Los patterns aparecen más allá de `match`: `let`, `for` y constructs condicionales pueden destructure valores. `..` ignora partes, `_` ignora un valor y `@` puede bindear un valor mientras prueba un subpattern.

```rust
struct Point {
    x: i32,
    y: i32,
}

let point = Point { x: 3, y: 4 };
let Point { x, y } = point;

let (first, .., last) = (1, 2, 3, 4);
```

Destructure cuando exponga solo los datos necesarios. Evita patterns enormes que dupliquen toda la estructura del dominio; un helper method o match en la frontera puede ser más claro.
