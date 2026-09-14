# Checked and Unchecked Exceptions

Java distinguishes checked exceptions, which callers must handle or declare, from unchecked exceptions under `RuntimeException` and errors. The distinction is part of a method signature and API design, even though both are runtime throwable objects.

```java
try {
    Files.readString(path);
} catch (IOException ex) {
    System.err.println(ex.getMessage());
}
```

Use checked exceptions for recoverable conditions when forcing callers to acknowledge them improves the API. Do not catch broad exceptions just to continue; unexpected programming failures are usually more useful with their stack and cause preserved.
