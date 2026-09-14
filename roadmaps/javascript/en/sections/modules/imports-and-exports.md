# Imports and Exports

ES modules exchange bindings through `export` and `import`. Named exports expose several explicit names and can be renamed during import or re-export. A default export exposes one distinguished value. Imported bindings are live views of the exported bindings, not copies.

```js
// math.js
export const PI = Math.PI;
export function area(radius) {
  return PI * radius ** 2;
}

// app.js
import { PI, area as circleArea } from "./math.js";
```

Named exports often make refactoring and public APIs clearer when a module exposes peer capabilities. Default exports fit modules with one obvious primary value. Keep module evaluation side effects small so importing code does not unexpectedly mutate global application state. A module's file boundary should represent a responsibility, not an arbitrary line count.
