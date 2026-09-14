# Try-with-resources

Try-with-resources closes objects implementing `AutoCloseable` when the block exits, including when an exception occurs. Multiple resources close in reverse declaration order, and suppressed exceptions preserve failures that happen during cleanup.

```java
try (var reader = Files.newBufferedReader(path)) {
    System.out.println(reader.readLine());
}
```

Use this construct for streams, JDBC resources, locks wrapped as closeable helpers, and other deterministic lifetimes. Garbage collection does not replace closing external resources promptly.
