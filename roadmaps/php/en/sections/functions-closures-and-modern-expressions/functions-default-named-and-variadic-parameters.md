# Functions and Parameters

Functions support default values, named arguments, variadic parameters, return types, references, and first-class callable syntax. Named arguments bind to parameter names, which means changing public parameter names can become a compatibility concern.

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

Use named arguments for readability when an API has several optional or same-typed parameters. Avoid long parameter lists by introducing a configuration/value object when options form a meaningful structure.
