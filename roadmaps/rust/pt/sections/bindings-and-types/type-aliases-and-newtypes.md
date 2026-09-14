# Type Aliases e Newtypes

Type alias cria outro nome para o mesmo tipo sem nova identidade. Newtype envolve um valor em tuple struct e cria tipo distinto que pode separar domínios e definir traits/methods próprios.

```rust
type UserIdText = String;

struct UserId(String);

fn load_user(id: UserId) {
    // ...
}
```

Use aliases para legibilidade sem mudar compatibilidade. Use newtypes quando dois valores têm mesma representação mas não devem se misturar, ou quando precisa implementar traits respeitando coherence/orphan rules.
