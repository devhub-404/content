# Arquivos PHP, Tags e Output

Código PHP começa com `<?php`. Arquivos PHP puros normalmente omitem closing tag para evitar output acidental. `echo`/`print` escrevem saída e CLI também usa streams/exit status.

```php
<?php

declare(strict_types=1);

$message = 'hello';
echo $message, PHP_EOL;
```

Separe lógica de aplicação de output direto quando possível. Templates podem misturar PHP/HTML, mas domain/service code fica mais testável retornando values.
