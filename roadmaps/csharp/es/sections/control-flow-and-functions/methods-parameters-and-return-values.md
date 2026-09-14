# Métodos, Parámetros y Retornos

Las firmas especifican tipos de parámetros y retorno, los overloads pueden compartir nombre y los argumentos optional/named ayudan en APIs concretas. Modifiers como `ref`, `out`, `in` y `params` cambian cómo se pasan o agrupan argumentos.

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

Prefiere parámetros y retornos normales hasta que un modifier exprese una necesidad real. `out` es útil en try-patterns, mientras `ref` expone aliasing y no debe usarse solo para evitar copiar valores pequeños.
