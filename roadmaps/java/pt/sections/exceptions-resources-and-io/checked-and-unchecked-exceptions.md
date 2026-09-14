# Exceptions Checked e Unchecked

Java distingue checked exceptions, que caller precisa tratar/declarar, de unchecked sob `RuntimeException`. A distinção faz parte do contrato da API.

```java
try {
    Files.readString(path);
} catch (IOException ex) {
    System.err.println(ex.getMessage());
}
```

Use checked quando condições recuperáveis merecem reconhecimento explícito. Não capture exceptions amplas apenas para continuar; failures inesperadas são mais úteis com stack/cause preservados.
