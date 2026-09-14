# Modules, `use`, and Visibility

The module system organizes names and controls visibility within a crate. Items are private by default, and `pub` exposes them according to the selected visibility boundary. `use` brings a path into scope without changing ownership or copying the item.

```rust
pub mod api {
    pub fn run() {}

    fn internal() {}
}

use crate::api::run;
```

Design module trees around coherent responsibilities and expose the smallest public surface that callers need. Re-exporting with `pub use` can create a clean public facade while implementation modules remain private.
