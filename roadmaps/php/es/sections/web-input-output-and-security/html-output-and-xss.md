# Output HTML y XSS

XSS ocurre cuando datos no confiables se convierten en markup/script ejecutable. HTML text, attributes, JavaScript, CSS y URLs son contextos distintos con encoding propio.

```php
<?= htmlspecialchars(
    $user->displayName,
    ENT_QUOTES | ENT_SUBSTITUTE,
    'UTF-8'
) ?>
```

Prefiere template engines con auto-escaping contextual. No “sanitices una vez” para todo contexto; codifica en el boundary de output.
