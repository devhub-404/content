# Storage y Web Workers

`localStorage` y `sessionStorage` almacenan pares string clave/valor de forma síncrona. Son apropiados para preferencias o estado pequeño, no grandes bases de datos. Los objetos necesitan serialización y el contenido almacenado nunca debe considerarse confiable automáticamente.

```js
localStorage.setItem("theme", "dark");
const theme = localStorage.getItem("theme");

const worker = new Worker("./worker.js", { type: "module" });
worker.postMessage({ values: largeArray });
```

Web Workers ejecutan JavaScript en otro contexto y pueden sacar computación costosa de la main thread. No acceden directamente al DOM y se comunican por mensajes, structured clone y transferables. Úsalos cuando profiling muestre trabajo de CPU que realmente bloquea la interfaz.
