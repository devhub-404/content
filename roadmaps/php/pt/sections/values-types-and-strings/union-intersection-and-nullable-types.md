# Union, Intersection e Nullable Types

Union types descrevem alternativas, intersection types exigem vários class/interface types e nullable inclui `null`. Contracts ficam mais explícitos embora checks ocorram em runtime.

```php
function normalize(string|Stringable $value): string {
    return (string) $value;
}

function save(?User $user): void {
    // ...
}
```

Mantenha unions focadas no domínio. Muitas alternativas sem relação normalmente indicam que parsing/normalization deve ocorrer antes.
