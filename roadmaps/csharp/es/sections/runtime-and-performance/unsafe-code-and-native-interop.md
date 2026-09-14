# Código Unsafe e Interop Nativo

C# puede entrar en contexto `unsafe` para pointer arithmetic, memoria fixed y escenarios de interop. .NET también ofrece P/Invoke y recursos para llamar libraries unmanaged. Unsafe omite parte de las garantías managed y requiere permiso explícito del proyecto.

```csharp
unsafe
{
    int value = 42;
    int* pointer = &value;
    Console.WriteLine(*pointer);
}
```

Mantén boundaries unsafe estrechos y envuélvelos en APIs safe bien probadas. La mayoría de aplicaciones no necesita raw pointers. El interop debe considerar ownership, calling convention, encoding, layout, pinning y errores.
