# Local Functions y Expression-bodied Members

Las local functions definen helpers limitados al método y pueden capturar estado externo salvo si son `static`. Los expression-bodied members usan `=>` cuando la implementación cabe naturalmente en una expresión.

```csharp
static int SumPositive(IEnumerable<int> values)
{
    return values.Sum(IsPositive);

    static int IsPositive(int value) =>
        value > 0 ? value : 0;
}
```

Usa estas formas para mejorar locality, no para esconder funciones grandes dentro de otras funciones grandes. Una local function static garantiza que no haya capture accidental de variables externas.
