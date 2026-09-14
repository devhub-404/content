# Releases, LTS y Preview Features

Java tiene una cadencia semestral y releases LTS ampliamente adoptadas. Algunas features pasan por preview antes de hacerse permanentes, cambiar o retirarse.

```java
// Compile a preview experiment only when intended:
// javac --enable-preview --release 25 Example.java
// java --enable-preview Example
```

No conviertas preview en dependencia silenciosa de libraries. Declara JDK/runtime mínimo, prueba versiones soportadas y distingue source, binary y runtime compatibility.
