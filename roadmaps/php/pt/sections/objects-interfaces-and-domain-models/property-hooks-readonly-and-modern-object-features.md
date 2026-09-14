# Properties Modernas e Design Readonly

PHP moderno oferece readonly, property hooks, asymmetric visibility, promoted properties e clone-with do PHP 8.5. Isso ajuda a impor invariants sem boilerplate excessivo.

```php
final class User
{
    public string $name {
        set => trim($value);
    }

    public function __construct(string $name)
    {
        $this->name = $name;
    }
}
```

Use para contratos claros, não para esconder lógica em toda property. I/O caro e side effects grandes continuam melhores em methods.
