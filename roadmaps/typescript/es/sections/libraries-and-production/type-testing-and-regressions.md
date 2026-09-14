# Probar tipos y evitar regresiones

Una API de tipos puede romperse aunque los tests de runtime sigan verdes. Las bibliotecas suelen añadir fixtures de compile time o type tests para comprobar llamadas aceptadas y rechazadas, inferencia y declarations públicas.

```ts
type Equal<A, B> =
  (<T>() => T extends A ? 1 : 2) extends
  (<T>() => T extends B ? 1 : 2)
    ? true
    : false;

type Expect<T extends true> = T;

type Test = Expect<Equal<ReturnType<typeof createUser>, User>>;
```

No conviertas cada helper interno en una prueba frágil de igualdad exacta; prueba el comportamiento público del que dependen los consumidores. Los tests de runtime siguen siendo necesarios porque el typechecker no prueba algoritmos, side effects ni datos externos reales.
