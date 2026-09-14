# Parámetros, defaults y rest

JavaScript no impone aridad en runtime. Parámetros ausentes reciben `undefined`, argumentos extra se permiten, un default sustituye `undefined` y un rest parameter recoge los argumentos restantes en un array real. El rest debe ser el último parámetro.

```js
function format(name, prefix = "User", ...tags) {
  return `${prefix}: ${name} [${tags.join(", ")}]`;
}

format("Mina", undefined, "admin", "active");
```

Las funciones ordinarias también tienen el objeto array-like `arguments`, pero rest es más claro y trabaja bien con métodos de array. Los defaults se evalúan en cada llamada. Cuando una función acumula muchos parámetros, un objeto de opciones suele comunicar mejor nombres y valores opcionales que una lista posicional larga.
