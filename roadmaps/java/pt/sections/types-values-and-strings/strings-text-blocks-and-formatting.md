# Strings, Text Blocks e Formatação

`String` é imutável e armazena texto Unicode em representação interna da JVM. Text blocks simplificam multilinhas, enquanto `formatted`, `StringBuilder` e APIs de formatação cobrem diferentes necessidades.

```java
String name = "Mina";
String message = "Hello, " + name;

String json = """
    {"name": "Mina"}
    """;

String formatted = "id=%d".formatted(42);
```

Indexação trabalha com code units UTF-16, não necessariamente caracteres visíveis. Para Unicode sensível, entenda code points e boundaries de texto em vez de tratar todo `char` como um caractere percebido.
