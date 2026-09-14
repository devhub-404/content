# Try-with-resources

Try-with-resources cierra objetos `AutoCloseable` al salir del bloque, incluso con exceptions. Varios recursos se cierran en orden inverso y suppressed exceptions conservan fallos de cleanup.

```java
try (var reader = Files.newBufferedReader(path)) {
    System.out.println(reader.readLine());
}
```

Úsalo para streams, JDBC y otros lifetimes deterministas. Garbage collection no sustituye el cierre rápido de recursos externos. Este patrón mantiene la liberación del recurso cerca de la adquisición y funciona incluso cuando una exception interrumpe el flujo.
