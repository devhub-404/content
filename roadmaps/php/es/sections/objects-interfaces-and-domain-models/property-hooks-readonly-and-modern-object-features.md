# Properties Modernas y Diseño Readonly

PHP moderno ofrece readonly, property hooks, asymmetric visibility, promoted properties y clone-with de PHP 8.5. Esto ayuda a imponer invariants sin boilerplate excesivo.

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

Úsalos para contratos claros, no para esconder lógica en cada property. I/O costoso y side effects grandes siguen siendo mejores en methods.
