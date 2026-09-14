# Imports y exports

Los ES modules intercambian bindings mediante `export` e `import`. Named exports exponen varios nombres y pueden renombrarse; default export destaca un valor principal. Los imports son bindings vivos hacia los exports, no copias aisladas.

```js
// math.js
export const PI = Math.PI;
export function area(radius) {
  return PI * radius ** 2;
}

// app.js
import { PI, area as circleArea } from "./math.js";
```

Named exports suelen hacer más explícitas APIs con varias capacidades; default puede encajar cuando un módulo produce un valor principal claro. Mantén pequeños los efectos colaterales al evaluar un módulo y diseña fronteras de módulo según responsabilidades, no por una cantidad arbitraria de líneas.
