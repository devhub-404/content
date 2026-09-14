# Try-with-resources

Try-with-resources fecha objetos `AutoCloseable` na saída do bloco, inclusive em exceptions. Múltiplos recursos fecham na ordem inversa e suppressed exceptions preservam falhas de cleanup.

```java
try (var reader = Files.newBufferedReader(path)) {
    System.out.println(reader.readLine());
}
```

Use para streams, JDBC e outros lifetimes determinísticos. Garbage collection não substitui fechamento rápido de recursos externos. Esse padrão mantém a liberação do recurso próxima da aquisição e funciona mesmo quando uma exception interrompe o fluxo.
