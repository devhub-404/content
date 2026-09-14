# Exceptions, `try`, `catch` y `finally`

Las exceptions representan fallos que hacen unwind de la call stack hasta encontrar un handler compatible. Captura fallos específicos de los que puedas recuperarte o que puedas traducir y usa `finally` para cleanup obligatorio.

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

No captures `Exception` solo para ignorarla. Los boundaries de la aplicación pueden capturar ampliamente para logging/respuesta, pero las capas inferiores deberían dejar que fallos inesperados se propaguen con stack/context originales.
