# `createMutable` e State Mutation-style

`createMutable` cria proxy profundamente reativo cujas properties podem ser atribuídas diretamente. Pode ser conveniente em integração com código mutation-oriented ou quando direct property syntax combina bem com o domínio.

```tsx
const state = createMutable({ count: 0 });

state.count += 1;
```

O modelo de store setter costuma ser mais auditável porque updates são explícitos. Use mutable proxy intencionalmente em vez de misturar estilos. Passar proxy gravável por boundaries amplas pode dificultar ownership e write authority.
