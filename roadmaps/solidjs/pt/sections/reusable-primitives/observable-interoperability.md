# Interop com Observables

Solid pode conectar external reactive sources ao seu graph. Helpers como `from` adaptam subscribable/observable sources para accessors rastreáveis por computations. Isso ajuda integração com state library existente ou browser stream.

```tsx
const temperature = from(sensorObservable);

createEffect(() => {
  console.log("temperature", temperature());
});
```

A adapter boundary deve cuidar do cleanup da subscription e initial-value behavior. Não duplique o mesmo external state em outro signal sem transformação/ownership real; mirroring desnecessário cria problemas de sincronização.
