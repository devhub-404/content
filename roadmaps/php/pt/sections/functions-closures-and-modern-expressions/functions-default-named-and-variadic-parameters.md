# Functions e Parâmetros

Functions suportam defaults, named arguments, variadic, return types, references e first-class callables. Named arguments ligam ao nome do parameter, tornando renames públicos potencialmente breaking.

```php
function connect(
    string $host,
    int $port = 443,
    bool $secure = true,
): void {
    // ...
}

connect(host: 'example.com', secure: false);
```

Use named arguments para legibilidade e config objects quando options formam estrutura significativa. Em APIs públicas, uma assinatura simples e explícita costuma ser mais fácil de manter que convenções implícitas entre callers.
