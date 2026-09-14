# Structs and Tuple Structs

A struct groups related fields into a named type. Named-field structs are good for records with several meaningful parts, tuple structs are useful for newtypes or small positional groupings, and unit structs represent a type with no stored fields.

```rust
struct User {
    id: u64,
    name: String,
}

struct UserId(u64);

let user = User {
    id: 42,
    name: String::from("Mina"),
};
```

Struct update syntax can move non-Copy fields from another value, so understand ownership when reusing an existing struct. Prefer constructors or validation functions when not every combination of public fields would be a valid value.
