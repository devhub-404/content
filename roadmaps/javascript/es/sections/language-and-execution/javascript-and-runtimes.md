# JavaScript y entornos de ejecución

JavaScript es el lenguaje estandarizado como ECMAScript. La especificación define sintaxis, valores, objetos, funciones, promises, módulos y objetos integrados, mientras que el entorno de ejecución aporta las APIs que rodean al lenguaje. Un navegador ofrece DOM, eventos, Fetch y storage; Node.js y otros runtimes ofrecen otro conjunto de APIs.

```js
const total = 2 + 3;
console.log(total);
```

Esta diferencia es fundamental: `Array`, `Promise`, `Map` y `JSON` pertenecen a JavaScript, mientras `document`, `fetch` y `localStorage` pertenecen al navegador. La misma sintaxis puede ejecutarse en hosts distintos aunque cambien los globals disponibles. Aprende primero el lenguaje y después las APIs del entorno en el que corre tu programa.
