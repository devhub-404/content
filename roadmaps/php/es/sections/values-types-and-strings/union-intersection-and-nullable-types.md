# Union, Intersection y Nullable Types

Los union types describen alternativas, los intersection types exigen varios class/interface types y nullable incluye `null`. Los contratos quedan más explícitos aunque los checks ocurran en runtime.

```php
function normalize(string|Stringable $value): string {
    return (string) $value;
}

function save(?User $user): void {
    // ...
}
```

Mantén unions enfocadas al dominio. Muchas alternativas no relacionadas suelen indicar que parsing/normalization debería ocurrir antes.
