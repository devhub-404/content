# Batching Updates

`batch` groups several reactive writes so downstream computations observe the final group of changes instead of rerunning after each individual setter. Solid already batches in several framework-managed situations, but explicit batching can help when an application-level operation performs multiple independent writes.

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

batch(() => {
  setFirst("Grace");
  setLast("Hopper");
});
```

Use batching to represent one logical state transition, not to hide an overly fragmented state model. Fine-grained reactivity already minimizes work; measure before adding manual batch boundaries solely for performance. Correctness should not depend on observers seeing impossible intermediate states unless that contract is deliberate.
