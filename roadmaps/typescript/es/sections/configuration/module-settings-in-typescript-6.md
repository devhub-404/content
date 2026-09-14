# Configuración de módulos en TypeScript 6.0

La configuración de módulos depende mucho del entorno. Proyectos Node modernos suelen usar modos conscientes de Node, mientras proyectos controlados por bundler pueden usar resolución orientada a bundlers. El setting debe describir cómo el runtime o build system interpreta imports.

```ts
{
  "compilerOptions": {
    "module": "nodenext",
    "moduleResolution": "nodenext",
    "verbatimModuleSyntax": true
  }
}
```

TypeScript 6.0 deprecia varias opciones legacy, entre ellas resoluciones antiguas y ciertos emits históricos. Un proyecto nuevo no debería empezar con una config vieja solo porque aparece en un tutorial antiguo; usa el baseline recomendado actualmente para tu entorno.
