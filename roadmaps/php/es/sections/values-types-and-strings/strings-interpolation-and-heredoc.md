# Strings, Interpolation, Heredoc y Nowdoc

Las single quotes hacen escaping mínimo, las double quotes soportan interpolation y heredoc/nowdoc ofrecen multilínea. Las strings son byte sequences y operaciones Unicode dependen de APIs/extensions adecuadas.

```php
$name = 'Mina';
$message = "Hello, {$name}!";

$sql = <<<SQL
SELECT id, name
FROM users
WHERE active = 1
SQL;
```

Interpolation no es escaping. Usa SQL parametrizado, HTML escaping, URL encoding, JSON encoder y shell APIs según contexto.
