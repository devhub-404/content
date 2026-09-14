# `createMutable` and Mutable-style State

`createMutable` creates a deeply reactive proxy whose properties can be assigned directly. It can be convenient when integrating with mutation-oriented code or when the direct property syntax closely matches the domain.

```tsx
const state = createMutable({ count: 0 });

state.count += 1;
```

The store setter model is often easier to audit because updates are explicit at the call site. Use mutable proxies intentionally rather than mixing update styles unpredictably. Passing a mutable proxy across broad module boundaries can make ownership and write authority harder to understand.
