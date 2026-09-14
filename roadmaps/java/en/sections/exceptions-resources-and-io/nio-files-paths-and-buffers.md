# NIO Files, Paths, and Buffers

The NIO APIs center on `Path`, `Files`, channels, and buffers for filesystem and I/O work. Convenience methods are good for bounded data, while channels and streaming APIs suit large or incremental content.

```java
Path path = Path.of("data", "report.txt");
String text = Files.readString(path);
Files.writeString(path, text + "
updated");
```

Filesystem operations can fail between checks and actions, so handle each operation as fallible instead of assuming an earlier existence test guarantees success. Choose platform-independent path operations rather than concatenating separators manually.
