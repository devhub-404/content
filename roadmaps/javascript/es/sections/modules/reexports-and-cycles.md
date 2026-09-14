# Re-exports y ciclos

Re-exportar permite construir una superficie pública estable sin obligar al consumidor a conocer todos los archivos internos. `export *` es conciso, pero puede hacer menos evidente qué nombres forman la API y provocar conflictos.

```js
// public-api.js
export { createUser } from "./create-user.js";
export { validateUser } from "./validate-user.js";
export { UserError } from "./errors.js";
```

ES modules soportan dependencias circulares, pero los ciclos estrechos pueden ser difíciles por el orden de inicialización de bindings. Si dos módulos necesitan el estado inicializado del otro, normalmente conviene extraer una responsabilidad inferior compartida.
