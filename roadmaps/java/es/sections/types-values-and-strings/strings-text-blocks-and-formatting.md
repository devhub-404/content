# Strings, Text Blocks y Formato

`String` es inmutable y almacena texto Unicode en una representación interna de la JVM. Los text blocks simplifican multilíneas, mientras `formatted`, `StringBuilder` y APIs de formato cubren necesidades distintas.

```java
String name = "Mina";
String message = "Hello, " + name;

String json = """
    {"name": "Mina"}
    """;

String formatted = "id=%d".formatted(42);
```

La indexación trabaja con code units UTF-16, no necesariamente caracteres visibles. Para Unicode sensible, entiende code points y boundaries de texto en vez de tratar cada `char` como un carácter percibido.
