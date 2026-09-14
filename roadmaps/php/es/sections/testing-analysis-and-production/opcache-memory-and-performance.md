# OPcache, Memoria y Performance

OPcache guarda bytecode compilado entre requests, eliminando parse/compile repetido. La performance también depende de database, network, autoload, serialization, memory y framework.

```php
<?php
// Production typically enables OPcache in php.ini.
// Measure application hot paths before manual micro-optimization.
```

Perfila workloads reales antes de micro-optimizar sintaxis. Reduce I/O/algoritmos primero; en persistent workers, leaks y lifecycle importan más.
