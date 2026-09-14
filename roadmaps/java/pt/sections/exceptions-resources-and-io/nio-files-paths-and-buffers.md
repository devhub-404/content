# NIO Files, Paths e Buffers

APIs NIO giram em torno de `Path`, `Files`, channels e buffers. Métodos convenientes servem a dados bounded e streaming/channels a conteúdo grande ou incremental.

```java
Path path = Path.of("data", "report.txt");
String text = Files.readString(path);
Files.writeString(path, text + "
updated");
```

Filesystem pode mudar entre check e operação, então trate cada ação como fallible. Use operações de path portáveis em vez de concatenar separators manualmente.
