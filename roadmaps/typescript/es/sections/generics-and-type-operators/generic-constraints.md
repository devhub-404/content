# Generic constraints

Un constraint limita qué tipos pueden sustituir un type parameter y a la vez preserva información del tipo concreto. `T extends { length: number }` permite cualquier valor con length numérico y hace esa propiedad segura dentro de la función.

```ts
function getLength<T extends { length: number }>(value: T) {
  return value.length;
}

getLength("hello");
getLength([1, 2, 3]);
```

El constraint debe expresar la capacidad mínima que necesita la implementación. Exigir una interface enorme porque los callers actuales la tienen reduce reutilización e inferencia. Diseña la restricción a partir de lo que el algoritmo realmente usa.
