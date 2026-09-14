# `implements` and Abstract Classes

`implements` checks that a class instance is compatible with an interface or object type, but it does not change how the class body itself is inferred. An abstract class can provide shared implementation while requiring subclasses to implement abstract members.

```ts
interface Repository<T> {
  get(id: string): Promise<T | undefined>;
}

abstract class BaseRepository<T> implements Repository<T> {
  abstract get(id: string): Promise<T | undefined>;

  protected log(message: string) {
    console.log(message);
  }
}
```

Use an interface when consumers need a contract independent of inheritance. Use an abstract class when subclasses intentionally share runtime base behavior or protected state. `implements` is erased, so it does not register a runtime relationship or make `instanceof` work with an interface.
