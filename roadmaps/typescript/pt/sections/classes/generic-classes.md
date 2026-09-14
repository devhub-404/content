# Classes Genéricas

Classes genéricas carregam type parameters no lado de instância, permitindo que uma implementação preserve o tipo de valores armazenados ou processados. O parâmetro pode aparecer em fields, constructor parameters, métodos e interfaces implementadas.

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

Membros static normalmente não podem referir-se ao type parameter da instância porque uma propriedade static é compartilhada entre todas as instanciações como `Store<User>` e `Store<Product>`. Se comportamento static precisa de type parameter, torne o próprio método genérico ou mova operação para factory function genérica.
