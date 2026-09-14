# Exceptions Customizadas e Contratos de Erro

Exceptions customizadas ajudam quando callers precisam distinguir falha de domínio sem parsear mensagem. Derive de `Exception`, preserve inner exceptions ao envolver e dê significado estável ao tipo.

```csharp
public sealed class InvalidOrderException : Exception
{
    public InvalidOrderException(string message)
        : base(message) { }
}
```

Nem toda validação merece custom exception. Try-patterns, result types ou collections de validação podem ser melhores quando falha é fluxo esperado. Exceptions funcionam melhor quando a chamada não consegue cumprir seu resultado normalmente.
