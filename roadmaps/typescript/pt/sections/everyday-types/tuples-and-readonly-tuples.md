# Tuples e Readonly Tuples

Tuple types descrevem arrays com sequência conhecida de tipos e, frequentemente, tamanho conhecido. Elementos rotulados melhoram documentação no editor sem mudar assignability. Elementos opcionais e rest podem modelar APIs posicionais mais flexíveis.

```ts
type Coordinate = readonly [x: number, y: number];

const point: Coordinate = [10, 20];

function range(): [start: number, end: number] {
  return [0, 100];
}
```

Use tuples quando a posição em si carrega significado estável e a sequência é pequena. Se callers precisam memorizar muitas posições, objeto com propriedades nomeadas normalmente é mais claro. Tuples `readonly` impedem mutação pela referência tipada e combinam naturalmente com inferência `as const` para dados literais.
