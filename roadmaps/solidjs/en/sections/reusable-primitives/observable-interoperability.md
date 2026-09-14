# Observable Interoperability

Solid can bridge external reactive sources into its graph. Utilities such as `from` adapt subscribable/observable-style sources into accessors so Solid computations can track them naturally. This is useful when integrating an existing state library or browser stream.

```tsx
const temperature = from(sensorObservable);

createEffect(() => {
  console.log("temperature", temperature());
});
```

The adapter boundary should own subscription cleanup and define the initial-value behavior. Do not duplicate the same external state in a second Solid signal unless there is a real transformation or ownership reason; unnecessary mirroring creates synchronization problems.
