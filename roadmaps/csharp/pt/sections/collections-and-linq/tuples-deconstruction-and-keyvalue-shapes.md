# Tuples e Deconstruction

Value tuples agrupam poucos valores com nomes opcionais e deconstruction atribui componentes a variáveis separadas. Classes, records e custom types também podem participar com `Deconstruct`.

```csharp
static (int Min, int Max) Bounds(IEnumerable<int> values)
{
    return (values.Min(), values.Max());
}

var (min, max) = Bounds([3, 8, 2]);
```

Tuples funcionam bem para resultados locais pequenos. Quando o shape cruza boundary público, cresce muitos campos ou precisa comportamento/validação, record ou struct nomeado comunica melhor.
