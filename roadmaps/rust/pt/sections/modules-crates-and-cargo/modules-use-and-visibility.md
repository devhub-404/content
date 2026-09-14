# Modules, `use` e Visibility

Sistema de modules organiza nomes e visibility dentro de crate. Items são private por default e `pub` expõe conforme boundary. `use` traz path ao scope sem mudar ownership.

```rust
pub mod api {
    pub fn run() {}

    fn internal() {}
}

use crate::api::run;
```

Projete modules por responsabilidades coerentes e exponha superfície mínima. `pub use` pode criar facade pública limpa enquanto implementation modules ficam private.
