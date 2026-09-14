# Archivos PHP, Tags y Output

El código PHP empieza con `<?php`. Los archivos PHP puros suelen omitir el closing tag para evitar output accidental. `echo`/`print` escriben salida y CLI también usa streams/exit status.

```php
<?php

declare(strict_types=1);

$message = 'hello';
echo $message, PHP_EOL;
```

Separa la lógica de aplicación del output directo cuando sea posible. Los templates pueden mezclar PHP/HTML, pero domain/service code es más testeable retornando values.
