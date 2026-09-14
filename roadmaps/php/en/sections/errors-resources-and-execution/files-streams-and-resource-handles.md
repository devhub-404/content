# Files, Streams, and Resource Handles

PHP exposes files, sockets, processes, and many extensions through resource or object handles with explicit close/finalization functions. Streams provide a uniform abstraction across files, memory, HTTP wrappers, compression, and custom protocols.

```php
$handle = fopen($path, 'rb');
if ($handle === false) {
    throw new RuntimeException('cannot open file');
}

try {
    $data = stream_get_contents($handle);
} finally {
    fclose($handle);
}
```

Release scarce handles promptly instead of relying only on request termination or garbage collection. In long-lived workers this becomes critical because process lifetime may span thousands of jobs.
