# NIO Files, Paths y Buffers

Las APIs NIO giran alrededor de `Path`, `Files`, channels y buffers. Los métodos de conveniencia sirven para datos bounded y streaming/channels para contenido grande o incremental.

```java
Path path = Path.of("data", "report.txt");
String text = Files.readString(path);
Files.writeString(path, text + "
updated");
```

El filesystem puede cambiar entre un check y la operación, así que trata cada acción como fallible. Usa operaciones de path portables en vez de concatenar separadores manualmente.
