# Tipos primitivos y arrays

TypeScript usa `string`, `number` y `boolean` en minúsculas para los valores primitivos de JavaScript. Los arrays pueden escribirse como `T[]` o `Array<T>`. BigInt, symbol, null y undefined también tienen tipos correspondientes.

```ts
let name: string = "Mina";
let count: number = 3;
let active: boolean = true;

const ids: string[] = ["a", "b"];
const scores: Array<number> = [10, 20];
```

Evita `String`, `Number` y `Boolean` boxed para valores normales. Una anotación describe qué valores acepta el checker, no convierte datos en runtime. Declarar algo como `number` no transforma una string en número; esa conversión sigue siendo lógica JavaScript.
