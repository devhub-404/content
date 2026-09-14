# Composer Dependencies and Lock Files

`composer.json` declares package metadata and version constraints, while `composer.lock` records the resolved dependency graph for reproducible application installs. Libraries normally publish constraints rather than forcing consumers to use their lockfile.

```json
{
  "require": {
    "php": "^8.5",
    "psr/log": "^3.0"
  }
}
```

Review updates for transitive changes, PHP/extension requirements, security advisories, and abandoned packages. Use `composer install` in deployment from a committed application lockfile rather than resolving arbitrary latest versions on the production server.
