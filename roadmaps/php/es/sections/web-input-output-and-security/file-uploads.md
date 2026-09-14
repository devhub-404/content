# File Uploads

Los uploads son untrusted data y la metadata viene en parte del client. PHP usa temp files y reporta status en `$_FILES`; la app debe imponer size, content y storage policies.

```php
if (!isset($_FILES['avatar']) || $_FILES['avatar']['error'] !== UPLOAD_ERR_OK) {
    throw new RuntimeException('upload failed');
}

$tmp = $_FILES['avatar']['tmp_name'];
move_uploaded_file($tmp, $destination);
```

No confíes en original filename/MIME como prueba. Genera nombres en server, evita directories ejecutables e inspecciona content cuando sea necesario.
