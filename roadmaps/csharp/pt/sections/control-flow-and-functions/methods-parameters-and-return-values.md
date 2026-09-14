# Métodos, Parâmetros e Retornos

Assinaturas especificam tipos de parâmetros e retorno, overloads podem compartilhar nome e argumentos optional/named ajudam em APIs específicas. Modifiers como `ref`, `out`, `in` e `params` mudam passagem ou agrupamento de argumentos.

```csharp
static bool TryDivide(
    double a,
    double b,
    out double result)
{
    if (b == 0)
    {
        result = default;
        return false;
    }

    result = a / b;
    return true;
}
```

Prefira parâmetros e retornos comuns até que um modifier expresse necessidade real. `out` é útil em try-patterns, enquanto `ref` expõe aliasing e não deve ser usado só para evitar cópia de valores pequenos.
