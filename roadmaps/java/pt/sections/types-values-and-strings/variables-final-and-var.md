# Variáveis, `final` e `var`

`var` pede ao compilador para inferir um tipo estático local pelo initializer. `final` impede reassignment do binding, mas uma referência final ainda pode apontar para objeto mutável.

```java
var name = "Mina";
final int maxRetries = 5;

name = name.toUpperCase();
```

Use `var` quando o tipo continuar óbvio e explicit types quando a abstração importa. `final` ajuda em invariantes e captures, mas Java não exige declarar final todo local que não muda.
