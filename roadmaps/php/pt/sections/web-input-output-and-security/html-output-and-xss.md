# Output HTML e XSS

XSS ocorre quando dados não confiáveis viram markup/script executável. HTML text, attributes, JavaScript, CSS e URLs são contextos diferentes com encoding próprio.

```php
<?= htmlspecialchars(
    $user->displayName,
    ENT_QUOTES | ENT_SUBSTITUTE,
    'UTF-8'
) ?>
```

Prefira template engines com auto-escaping contextual. Não “sanitize uma vez” para todo contexto; encode na boundary de output.
