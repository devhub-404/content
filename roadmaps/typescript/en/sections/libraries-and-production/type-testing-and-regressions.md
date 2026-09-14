# Testing Types and Preventing Regressions

Type-level APIs can regress even when runtime tests pass. Libraries often add compile-time fixtures or type tests that assert accepted and rejected call patterns, inferred results, and public declaration behavior. A simple consumer project compiled in CI can catch packaging and resolution mistakes too.

```ts
type Equal<A, B> =
  (<T>() => T extends A ? 1 : 2) extends
  (<T>() => T extends B ? 1 : 2)
    ? true
    : false;

type Expect<T extends true> = T;

type Test = Expect<Equal<ReturnType<typeof createUser>, User>>;
```

Do not make every internal type implementation a brittle exact-equality test; focus on public behavior consumers depend on. Runtime tests still matter because the typechecker cannot validate actual network data, side effects, algorithms, or emitted integration. Production quality needs both static and runtime evidence.
