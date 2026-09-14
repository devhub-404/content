# Intersection types

Una intersection `A & B` describe un valor que satisface ambos tipos simultáneamente. En objetos suele combinar conjuntos de propiedades requeridas y resulta útil para composición, helpers o APIs que añaden capacidades a otra forma.

```ts
type Timestamped = {
  createdAt: Date;
};

type Entity = {
  id: string;
};

type StoredEntity = Entity & Timestamped;
```

No es lo mismo que object spread y puede producir un tipo imposible cuando dos propiedades homónimas son incompatibles. Usa unions para alternativas e intersections para requisitos simultáneos, y nombra tipos complejos cuando una composición repetida empiece a ser difícil de leer.
