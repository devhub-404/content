# Inferencia y anotaciones de tipo

TypeScript puede inferir tipos a partir de initializers, flujo de control, retornos, contexto y relaciones genéricas. No hace falta anotar cada variable; repetir información obvia suele añadir ruido y hacer refactors más costosos.

```ts
const count = 3;           // inferred as 3
let total = 0;             // inferred as number

function add(a: number, b: number) {
  return a + b;            // return type inferred as number
}
```

Las anotaciones son más valiosas en fronteras: parámetros públicos, APIs exportadas, variables intencionalmente amplias o puntos donde la inferencia no expresa el diseño. Un return type explícito en una función pública también puede estabilizar el contrato y detectar cambios accidentales.
