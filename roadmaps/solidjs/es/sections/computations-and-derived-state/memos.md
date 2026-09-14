# Valores Derivados con `createMemo`

`createMemo` crea una derivation reactiva cacheada. Se ejecuta cuando cambia una dependency y notifica downstream solo cuando cambia el resultado según la equality configurada. Es la primitive correcta para derived state leído en varios lugares o suficientemente costoso para cachear.

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

const fullName = createMemo(() => `${first()} ${last()}`);

<p>{fullName()}</p>
```

No uses un effect más otro signal solo para mantener datos derivados sincronizados. Memo expresa la relación directamente y evita otra source escribible. Expressions JSX simples quizá ni necesiten memo porque Solid ya las rastrea con precisión.
