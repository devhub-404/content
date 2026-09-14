# PHP Files, Tags, and Output

PHP code is introduced with `<?php` in `.php` files. Pure PHP files normally omit the closing tag to avoid accidental output after it. `echo` and `print` write output, while command-line code can also use standard streams and exit statuses.

```php
<?php

declare(strict_types=1);

$message = 'hello';
echo $message, PHP_EOL;
```

Keep application logic separate from direct output where possible so it can be tested and reused. Templates may mix PHP with HTML deliberately, but core domain and service code is easier to maintain when it returns values rather than printing as a side effect.
