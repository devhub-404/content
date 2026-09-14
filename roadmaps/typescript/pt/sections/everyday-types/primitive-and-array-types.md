# Tipos Primitivos e Arrays

TypeScript usa `string`, `number` e `boolean` em minúsculas para valores primitivos JavaScript. Arrays podem ser escritos como `T[]` ou `Array<T>`. BigInt, symbol, null e undefined também possuem tipos correspondentes, com comportamento de nullabilidade fortemente afetado por `strictNullChecks`.

```ts
let name: string = "Mina";
let count: number = 3;
let active: boolean = true;

const ids: string[] = ["a", "b"];
const scores: Array<number> = [10, 20];
```

Evite tipos boxed como `String`, `Number` e `Boolean` para valores comuns; eles descrevem objetos wrapper, não primitivos. Anotações descrevem valores permitidos, não conversão de runtime. Declarar valor como `number` não transforma string em number—você ainda precisa da lógica JavaScript de conversão.
