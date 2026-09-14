# Generic Classes

Generic classes carry type parameters on their instance side, allowing one implementation to preserve the type of stored or processed values. The parameter can appear in fields, constructor parameters, methods, and implemented interfaces.

```ts
class Store<T> {
  #items = new Map<string, T>();

  set(id: string, value: T) {
    this.#items.set(id, value);
  }

  get(id: string): T | undefined {
    return this.#items.get(id);
  }
}
```

Static members cannot generally refer to a class's instance type parameter because one static property is shared across every instantiation such as `Store<User>` and `Store<Product>`. If static behavior needs a type parameter, make the static method itself generic or move the operation to a generic factory function.
