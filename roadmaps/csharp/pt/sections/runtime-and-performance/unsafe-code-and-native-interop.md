# Código Unsafe e Interop Nativo

C# pode entrar em contexto `unsafe` para pointer arithmetic, memória fixed e cenários de interop. .NET também oferece P/Invoke e recursos para chamar libraries unmanaged. Unsafe ignora parte das garantias managed e exige permissão explícita do projeto.

```csharp
unsafe
{
    int value = 42;
    int* pointer = &value;
    Console.WriteLine(*pointer);
}
```

Mantenha boundaries unsafe estreitas e envolva em APIs safe bem testadas. A maioria das aplicações não precisa raw pointers. Interop precisa considerar ownership, calling convention, encoding, layout, pinning e erros.
