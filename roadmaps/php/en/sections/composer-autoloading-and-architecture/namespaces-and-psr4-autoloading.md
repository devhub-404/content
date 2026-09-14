# Namespaces and PSR-4 Autoloading

Namespaces prevent name collisions and Composer commonly maps namespace prefixes to source directories through PSR-4 autoloading. The generated autoloader loads classes on demand without manual `require` calls scattered throughout the application.

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

Keep namespace structure aligned with stable code ownership rather than every tiny folder. After changing autoload configuration, regenerate Composer metadata as required. Application entry points should load `vendor/autoload.php` once.
