# `allowJs` y `checkJs`

TypeScript puede incluir archivos JavaScript con `allowJs` y type-checkarlos con `checkJs`, lo que permite migración gradual sin renombrar todo a `.ts`. Los tipos pueden inferirse de JavaScript, JSDoc, imports y declaration files.

```ts
{
  "compilerOptions": {
    "allowJs": true,
    "checkJs": true,
    "noEmit": true
  }
}
```

El checking de JS es algo más flexible para acomodar patrones dinámicos reales. Migra por fronteras: activa checks, documenta APIs importantes, corrige errores reales y convierte archivos cuando la sintaxis TypeScript aporte valor. Renombrar todos los archivos de golpe no mejora el diseño por sí mismo.
