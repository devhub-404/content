# Releases, LTS e Preview Features

Java tem cadence semestral e releases LTS adotadas amplamente. Alguns recursos passam por preview antes de virar permanentes, mudar ou ser retirados.

```java
// Compile a preview experiment only when intended:
// javac --enable-preview --release 25 Example.java
// java --enable-preview Example
```

Não torne preview dependency silenciosa em libraries. Declare JDK/runtime mínimo, teste versões suportadas e diferencie source, binary e runtime compatibility.
