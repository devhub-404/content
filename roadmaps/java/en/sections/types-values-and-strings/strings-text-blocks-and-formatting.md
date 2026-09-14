# Strings, Text Blocks, and Formatting

`String` is immutable and stores Unicode text in a JVM-defined internal representation. Text blocks make multiline literals readable, while `formatted`, `StringBuilder`, and formatting APIs serve different construction needs. Repeated `+` inside one expression is compiler-friendly, but repeated mutation in loops may need a builder.

```java
String name = "Mina";
String message = "Hello, " + name;

String json = """
    {"name": "Mina"}
    """;

String formatted = "id=%d".formatted(42);
```

String indexing works with UTF-16 code units, not necessarily user-perceived characters. For Unicode-sensitive processing, understand code points and higher-level text boundaries instead of treating every `char` as one visible character.
