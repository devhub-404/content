# Memoria y garbage collection

Los runtimes gestionan memoria ordinaria automáticamente. Conceptualmente, valores alcanzables desde roots activos pueden seguir vivos y valores no alcanzables pueden recolectarse. El algoritmo y el momento de la recolección son detalles de implementación.

```js
let cache = new Map();

function remember(key, value) {
  cache.set(key, value);
}

function clearCache() {
  cache = new Map();
}
```

Los memory leaks suelen ser reachability accidental: Maps, arrays, closures, listeners o caches long-lived siguen apuntando a datos que ya no sirven. Weak collections ayudan en asociaciones ligadas a identidad, pero no sustituyen diseño de lifecycle. Usa profilers para encontrar objetos retenidos.
