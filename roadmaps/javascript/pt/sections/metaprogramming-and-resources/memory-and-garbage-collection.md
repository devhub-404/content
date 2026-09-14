# Memória e Garbage Collection

Runtimes JavaScript gerenciam memória comum automaticamente. Conceitualmente, valores reachable a partir de roots ativos podem continuar vivos, enquanto valores inacessíveis tornam-se elegíveis para garbage collection. O algoritmo e timing exatos são detalhes de implementação; a correção nunca deve depender da coleta ocorrer em momento específico.

```js
let cache = new Map();

function remember(key, value) {
  cache.set(key, value);
}

function clearCache() {
  cache = new Map();
}
```

Leaks em linguagens gerenciadas normalmente são reachability acidental: Maps, arrays, closures, listeners ou caches long-lived mantêm dados vivos após perderem utilidade. Weak collections podem ajudar com metadata ligada à identidade, mas não substituem design de lifecycle. Use profilers de memória para encontrar objetos retidos em vez de tentar liberar objetos normais manualmente.
