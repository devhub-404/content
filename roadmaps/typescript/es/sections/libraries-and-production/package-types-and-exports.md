# Tipos de paquete y export maps

Un paquete publicado debe alinear sus entry points de JavaScript con los de tipos. Los export maps modernos pueden exponer subpaths y condiciones, y el resolver de TypeScript interpreta ese metadata según el entorno configurado.

```ts
{
  "name": "example-lib",
  "type": "module",
  "exports": {
    ".": {
      "types": "./dist/index.d.ts",
      "import": "./dist/index.js"
    }
  }
}
```

No publiques un `.d.ts` para una ruta que no existe en runtime ni una ruta runtime sin sus tipos si prometes soporte TypeScript. Prueba el paquete empaquetado desde un pequeño proyecto consumidor; aliases locales pueden ocultar errores que solo aparecen tras instalar.
