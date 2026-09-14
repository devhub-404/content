# Interop con Observables

Solid puede conectar external reactive sources a su graph. Helpers como `from` adaptan subscribable/observable sources a accessors que las computations pueden rastrear. Esto ayuda al integrar una state library existente o un browser stream.

```tsx
const temperature = from(sensorObservable);

createEffect(() => {
  console.log("temperature", temperature());
});
```

La adapter boundary debe encargarse del cleanup de la subscription y del initial-value behavior. No dupliques el mismo external state en otro signal sin una razón real de transformación/ownership; el mirroring innecesario crea problemas de sincronización.
