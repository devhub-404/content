# `public`, `protected` y `private`

Los access modifiers controlan qué accesos permite TypeScript: `public` es el default, `protected` permite clase y subclases y `private` restringe dentro del checker. Estos modifiers son principalmente una frontera de compile time.

```ts
class Account {
  public owner: string;
  protected balance = 0;
  private auditCode = "internal";

  constructor(owner: string) {
    this.owner = owner;
  }
}
```

Los campos JavaScript `#private` tienen privacidad real de runtime y semántica distinta. Usa `#private` cuando el encapsulamiento runtime importe y `private` cuando una frontera estática sea suficiente. No expongas internals mutables como public sin una razón de API.
