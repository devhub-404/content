# Sealed Classes e Hierarquias Fechadas

Sealed class/interface restringe quais tipos podem extend/implement. Subclasses permitidas precisam continuar explicitamente como `final`, `sealed` ou `non-sealed`, criando hierarquia controlada.

```java
public sealed interface Result
    permits Success, Failure { }

record Success(String value) implements Result { }
record Failure(String message) implements Result { }
```

Hierarquias sealed são ótimas para alternativas de domínio fechadas e switch exaustivo. Use interfaces abertas quando implementações de terceiros fazem parte do extension model.
