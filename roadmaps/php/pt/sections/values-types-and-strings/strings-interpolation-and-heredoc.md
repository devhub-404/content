# Strings, Interpolation, Heredoc e Nowdoc

Single quotes fazem escaping mínimo, double quotes suportam interpolation e heredoc/nowdoc oferecem multilinhas. Strings são byte sequences e operações Unicode dependem de APIs/extensions adequadas.

```php
$name = 'Mina';
$message = "Hello, {$name}!";

$sql = <<<SQL
SELECT id, name
FROM users
WHERE active = 1
SQL;
```

Interpolation não é escaping. Use SQL parametrizado, HTML escaping, URL encoding, JSON encoder e shell APIs conforme contexto.
