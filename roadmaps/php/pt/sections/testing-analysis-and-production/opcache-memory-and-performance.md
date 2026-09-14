# OPcache, Memória e Performance

OPcache guarda bytecode compilado entre requests, removendo parse/compile repetido. Performance também depende de database, network, autoload, serialization, memory e framework.

```php
<?php
// Production typically enables OPcache in php.ini.
// Measure application hot paths before manual micro-optimization.
```

Profile workloads reais antes de micro-otimizar syntax. Reduza I/O/algoritmos primeiro; em persistent workers, leaks e lifecycle importam mais.
