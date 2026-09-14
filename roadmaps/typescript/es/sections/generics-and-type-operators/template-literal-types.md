# Template literal types

Los template literal types construyen string literal types interpolando otros literals o unions. Si una posición contiene una union, TypeScript genera las combinaciones correspondientes. Sirven para nombres de eventos, rutas y APIs derivadas de convenciones de strings.

```ts
type EventName<T extends string> = `${T}Changed`;

type Field = "name" | "email";
type FieldEvent = EventName<Field>;
// "nameChanged" | "emailChanged"
```

Describen relaciones en compile time; no validan strings arbitrarias en runtime. Grandes combinaciones pueden crecer demasiado y ralentizar el checker. Cuando el vocabulario es enorme, datos generados o un `string` más simple pueden ser una mejor herramienta.
