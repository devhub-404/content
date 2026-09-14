# Parámetros optional, rest y destructured

Los parámetros pueden ser opcionales con `?`, tener valores default o usar rest para recoger una cantidad variable de argumentos. Un parámetro objeto destructured funciona bien para opciones nombradas y APIs que crecerán con el tiempo.

```ts
type Options = {
  retries?: number;
  signal?: AbortSignal;
};

function request(
  url: string,
  { retries = 2, signal }: Options = {}
) {
  // ...
}

function sum(...values: number[]) {
  return values.reduce((a, b) => a + b, 0);
}
```

Mantén la optionality alineada con runtime. Un default se aplica cuando falta el argumento o es `undefined`. Cuando aparecen muchos booleans y parámetros opcionales posicionales, un objeto de opciones suele producir llamadas mucho más legibles.
