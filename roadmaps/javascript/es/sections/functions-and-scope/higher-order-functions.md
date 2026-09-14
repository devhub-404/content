# Callbacks y funciones de orden superior

Las funciones son valores de primera clase: pueden almacenarse, pasarse, retornarse y colocarse en estructuras de datos. Un callback es una función que otra operación invocará, y una función de orden superior recibe o devuelve funciones. Array methods, eventos, promises y middleware usan este modelo.

```js
function repeat(times, action) {
  for (let i = 0; i < times; i++) {
    action(i);
  }
}

repeat(3, index => console.log(index));
```

Un callback puede ejecutarse ahora, más tarde, una vez o muchas, según la API. Pasar una función no implica asincronía. Mantén claro qué estado captura y, si aparecen demasiados niveles de callbacks, extrae pasos con nombres o usa una abstracción mejor como composición de promises.
