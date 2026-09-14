# File Uploads

Uploads são untrusted data e metadata é parcialmente client-supplied. PHP usa temp files e reporta status em `$_FILES`; app deve impor size, content e storage policies.

```php
if (!isset($_FILES['avatar']) || $_FILES['avatar']['error'] !== UPLOAD_ERR_OK) {
    throw new RuntimeException('upload failed');
}

$tmp = $_FILES['avatar']['tmp_name'];
move_uploaded_file($tmp, $destination);
```

Não confie em original filename/MIME como prova. Gere nomes no server, evite directories executáveis e inspecione content quando necessário.
