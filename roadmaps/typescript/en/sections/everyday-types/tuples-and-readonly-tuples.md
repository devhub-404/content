# Tuples and Readonly Tuples

Tuple types describe arrays with a known sequence of element types and, often, a known length. Labeled tuple elements improve editor documentation without changing assignability. Optional and rest tuple elements can model more flexible positional APIs.

```ts
type Coordinate = readonly [x: number, y: number];

const point: Coordinate = [10, 20];

function range(): [start: number, end: number] {
  return [0, 100];
}
```

Use tuples when position itself carries stable meaning and the sequence is small. If callers must remember many positions, an object with named properties is usually clearer. `readonly` tuples prevent mutation through the typed reference and pair naturally with `as const` inference for literal data.
