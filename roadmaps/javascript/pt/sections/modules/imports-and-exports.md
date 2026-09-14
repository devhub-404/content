# Imports e Exports

ES modules trocam bindings por `export` e `import`. Named exports expõem vários nomes explícitos e podem ser renomeados durante import ou re-export. Default export expõe um valor distinguido. Bindings importados são views live dos exports, não cópias.

```js
// math.js
export const PI = Math.PI;
export function area(radius) {
  return PI * radius ** 2;
}

// app.js
import { PI, area as circleArea } from "./math.js";
```

Named exports frequentemente deixam refactoring e APIs públicas mais claros quando um módulo expõe capacidades equivalentes. Default exports servem a módulos com um valor principal óbvio. Mantenha efeitos colaterais de avaliação pequenos para que importar código não mude estado global inesperadamente. A fronteira de módulo deve representar responsabilidade, não quantidade arbitrária de linhas.
