# Namespaces y Autoloading PSR-4

Los namespaces evitan colisiones y Composer suele mapear prefixes a directories mediante PSR-4. El autoloader generado carga classes on demand sin `require` disperso.

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

Alinea namespaces con boundaries estables. Tras cambiar autoload config, regenera metadata y carga `vendor/autoload.php` una vez en el entry point.
