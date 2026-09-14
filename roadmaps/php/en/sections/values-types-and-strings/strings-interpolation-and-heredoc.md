# Strings, Interpolation, Heredoc, and Nowdoc

Single-quoted strings perform minimal escaping, double-quoted strings support variable interpolation, and heredoc/nowdoc provide multiline syntax with different interpolation rules. Strings are byte sequences with many encoding-aware operations supplied by extensions such as mbstring.

```php
$name = 'Mina';
$message = "Hello, {$name}!";

$sql = <<<SQL
SELECT id, name
FROM users
WHERE active = 1
SQL;
```

Interpolation is not escaping. Use parameterized SQL, HTML escaping, URL encoding, JSON encoders, and shell argument APIs according to the output context instead of inserting untrusted text directly.
