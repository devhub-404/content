# `ref struct`, `stackalloc` e By-ref Safety

Recursos by-ref permitem trabalhar com stack memory e referências sem copiar valores. `ref struct` como `Span<T>` possui restrições para impedir que referências a stack escapem, e `stackalloc` cria storage limitado ao stack frame atual.

```csharp
Span<int> values = stackalloc int[4];
values[0] = 10;

ref int first = ref values[0];
first = 20;
```

Use apenas quando layout e allocation cost importam. As regras são intencionalmente rígidas; lutar contra elas costuma indicar tentativa de fazer memória short-lived escapar longe demais.
