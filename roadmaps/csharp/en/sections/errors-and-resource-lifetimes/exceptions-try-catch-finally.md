# Exceptions, `try`, `catch`, and `finally`

Exceptions represent failures that unwind the call stack until a matching handler is found. Catch the most specific failures you can actually recover from or translate, and use `finally` for cleanup that must happen regardless of success.

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

Do not catch `Exception` merely to ignore it. Application boundaries may catch broadly for logging or conversion to an error response, but lower layers should usually let unexpected failures propagate with their original stack and context.
