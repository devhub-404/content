# Local Functions e Expression-bodied Members

Local functions definem helpers limitados ao método e podem capturar estado externo salvo quando declaradas `static`. Expression-bodied members usam `=>` quando a implementação cabe naturalmente em uma expressão.

```csharp
static int SumPositive(IEnumerable<int> values)
{
    return values.Sum(IsPositive);

    static int IsPositive(int value) =>
        value > 0 ? value : 0;
}
```

Use essas formas para melhorar locality, não para esconder funções grandes dentro de outras funções grandes. Uma local function static garante que não há capture acidental de variáveis externas.
