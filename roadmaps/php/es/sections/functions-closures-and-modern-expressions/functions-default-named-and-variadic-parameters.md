# Functions y Parámetros

Las functions soportan defaults, named arguments, variadic, return types, references y first-class callables. Los named arguments se ligan al nombre del parameter, haciendo que renombrarlos públicamente pueda ser breaking.

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

Usa named arguments para legibilidad y config objects cuando las options formen una estructura significativa.
