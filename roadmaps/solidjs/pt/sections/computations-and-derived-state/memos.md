# Valores Derivados com `createMemo`

`createMemo` cria derivation reativa cacheada. Ela roda quando dependency muda e notifica downstream apenas quando resultado muda conforme equality configurada. É primitive correta para derived state lido em vários lugares ou caro o bastante para cache.

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

const fullName = createMemo(() => `${first()} ${last()}`);

<p>{fullName()}</p>
```

Não use effect mais signal apenas para sincronizar dado derivado. Memo expressa relação diretamente e evita outra source gravável. Expressions JSX simples podem nem precisar memo porque Solid já as rastreia precisamente.
