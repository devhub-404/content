# Resolución de módulos por el host

ECMAScript define sintaxis y semántica de módulos, pero el host decide cómo un specifier identifica código. Los navegadores resuelven principalmente URLs y otros entornos o bundlers pueden añadir reglas de paquetes, aliases y extensiones.

```js
import { format } from "./format.js";
import { readFile } from "node:fs/promises";
```

Por eso un import puede funcionar en un bundler y no directamente en el navegador. Package names, file extensions, conditional exports y CommonJS interoperability son preocupaciones del entorno alrededor del sistema de módulos. Prueba el código en el mismo runtime y toolchain que usarán los consumidores.
