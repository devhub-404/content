# File Uploads

Uploaded files are untrusted data with metadata supplied partly by the client. PHP stores successful uploads in temporary locations and reports status through the upload array. Applications must enforce size, content, extension, ownership, and storage policies.

```php
if (!isset($_FILES['avatar']) || $_FILES['avatar']['error'] !== UPLOAD_ERR_OK) {
    throw new RuntimeException('upload failed');
}

$tmp = $_FILES['avatar']['tmp_name'];
move_uploaded_file($tmp, $destination);
```

Never trust the original filename or MIME string as proof of file type. Store uploads outside executable/public directories when possible, generate server-side names, and inspect content with appropriate libraries for the domain.
