# Type Aliases y Newtypes

Un type alias crea otro nombre para el mismo tipo sin nueva identidad. El patrón newtype envuelve un valor en una tuple struct y crea un tipo distinto que puede separar dominios y definir traits/methods propios.

```rust
type UserIdText = String;

struct UserId(String);

fn load_user(id: UserId) {
    // ...
}
```

Usa aliases para legibilidad sin cambiar compatibilidad. Usa newtypes cuando dos valores comparten representación pero no deben mezclarse, o cuando necesitas implementar traits respetando coherence/orphan rules.
