# Destructuring e Pattern Bindings

Patterns aparecem além de `match`: `let`, `for` e constructs condicionais podem destructure valores. `..` ignora partes, `_` ignora um valor e `@` pode bindar valor enquanto testa subpattern.

```rust
struct Point {
    x: i32,
    y: i32,
}

let point = Point { x: 3, y: 4 };
let Point { x, y } = point;

let (first, .., last) = (1, 2, 3, 4);
```

Destructure quando expõe apenas dados necessários. Evite patterns enormes que duplicam toda estrutura do domínio; helper method ou match na fronteira pode ser mais claro.
