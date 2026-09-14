# `implements` e Classes Abstratas

`implements` verifica que instância de classe é compatível com interface ou object type, mas não muda como o corpo da classe é inferido. Classe abstrata pode fornecer implementação compartilhada enquanto exige que subclasses implementem membros abstract.

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

Use interface quando consumidores precisam de contrato independente de herança. Use classe abstrata quando subclasses intencionalmente compartilham comportamento de runtime ou estado protected. `implements` é apagado, então não registra relação de runtime nem faz `instanceof` funcionar com interface.
