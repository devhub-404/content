# `implements` y clases abstractas

`implements` verifica que una instancia sea compatible con una interface u object type, pero no cambia la inferencia del cuerpo de la clase. Una clase abstracta puede compartir implementación y exigir a las subclases que completen miembros abstract.

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

Usa interface cuando el consumidor necesita un contrato independiente de herencia y clase abstracta cuando las subclases comparten comportamiento runtime o estado protected. `implements` se borra: no crea una relación que puedas comprobar con `instanceof` sobre una interface.
