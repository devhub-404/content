# Coleções Weak

`WeakMap` e `WeakSet` mantêm chaves elegíveis de forma fraca, então a coleção não mantém a chave viva por si só para garbage collection. `WeakMap` é útil para associar metadata auxiliar à identidade de objetos; `WeakSet` registra membership fraco.

```js
const metadata = new WeakMap();

function attachMetadata(element, data) {
  metadata.set(element, data);
}

function getMetadata(element) {
  return metadata.get(element);
}
```

Weak collections intencionalmente não podem ser enumeradas e não expõem `size`, porque garbage collection é não determinístico. Portanto não servem para coleções que precisam ser listadas ou contadas. Sua finalidade é associação amigável ao lifecycle, não cleanup automático de recursos; handles, listeners e subscriptions ainda precisam de ownership e disposal explícitos.
