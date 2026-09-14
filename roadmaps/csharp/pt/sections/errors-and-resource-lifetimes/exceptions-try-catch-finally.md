# Exceptions, `try`, `catch` e `finally`

Exceptions representam falhas que unwind a call stack até handler compatível. Capture falhas específicas que consegue recuperar ou traduzir e use `finally` para cleanup obrigatório.

```csharp
try
{
    Process(path);
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine(ex.Message);
}
finally
{
    Console.WriteLine("finished");
}
```

Não capture `Exception` só para ignorar. Boundaries da aplicação podem capturar amplamente para logging/resposta, mas layers inferiores normalmente devem deixar falhas inesperadas subir com stack/context originais.
