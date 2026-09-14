# Namespaces e Autoloading PSR-4

Namespaces evitam colisões e Composer normalmente mapeia prefixes para directories com PSR-4. O autoloader gerado carrega classes on demand sem `require` espalhado.

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

Alinhe namespaces a boundaries estáveis. Após mudar autoload config, regenere metadata e carregue `vendor/autoload.php` uma vez no entry point.
