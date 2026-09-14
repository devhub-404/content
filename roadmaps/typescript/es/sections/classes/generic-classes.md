# Clases genéricas

Una clase genérica conserva un type parameter en el lado de instancia, por lo que fields y métodos pueden mantener el tipo de los valores almacenados o procesados. El parameter puede aparecer en constructor, métodos e interfaces implementadas.

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

Los miembros static no pueden depender normalmente del type parameter de instancia porque un único static se comparte entre todas las especializaciones. Si un método static necesita genericidad, haz que el propio método sea genérico o usa una factory genérica externa.
