# Exceptions Checked y Unchecked

Java distingue checked exceptions, que el caller debe manejar/declarar, de unchecked bajo `RuntimeException`. La distinción forma parte del contrato de la API.

```java
try {
    Files.readString(path);
} catch (IOException ex) {
    System.err.println(ex.getMessage());
}
```

Usa checked cuando condiciones recuperables merezcan reconocimiento explícito. No captures exceptions amplias solo para continuar; los fallos inesperados son más útiles con stack/cause conservados.
