# Modules, `use` y Visibility

El sistema de modules organiza nombres y visibility dentro de un crate. Los items son private por defecto y `pub` los expone según el boundary. `use` trae un path al scope sin cambiar ownership.

```rust
pub mod api {
    pub fn run() {}

    fn internal() {}
}

use crate::api::run;
```

Diseña modules por responsabilidades coherentes y expón la superficie mínima. `pub use` puede crear una facade pública limpia mientras los implementation modules quedan private.
