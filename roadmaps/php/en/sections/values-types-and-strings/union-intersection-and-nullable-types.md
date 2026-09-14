# Union, Intersection, and Nullable Types

Union types describe alternatives, intersection types require a value to satisfy several class/interface types, and nullable types include `null`. These declarations make dynamic PHP APIs much more explicit without changing that values are checked at runtime.

```php
function normalize(string|Stringable $value): string {
    return (string) $value;
}

function save(?User $user): void {
    // ...
}
```

Keep unions domain-focused. A signature with many unrelated alternatives often indicates that parsing or normalization should happen before the value reaches the core API.
