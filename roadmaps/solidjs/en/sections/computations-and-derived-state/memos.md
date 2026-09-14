# Derived Values with `createMemo`

`createMemo` creates a cached reactive derivation. It reruns when one of its dependencies changes and notifies downstream computations only when its result changes according to the configured equality behavior. This is the right primitive for derived reactive state that is read in several places or expensive enough to cache.

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

const fullName = createMemo(() => `${first()} ${last()}`);

<p>{fullName()}</p>
```

Do not use an effect plus another signal merely to keep derived data synchronized. A memo expresses the relationship directly and avoids an extra writable state source. Simple one-line JSX expressions may not need a memo because Solid already tracks them precisely.
