# `ref struct`, `stackalloc` y By-ref Safety

Las features by-ref permiten trabajar con stack memory y referencias sin copiar valores. Los `ref struct` como `Span<T>` tienen restricciones para impedir que referencias al stack escapen, y `stackalloc` crea almacenamiento limitado al stack frame actual.

```csharp
Span<int> values = stackalloc int[4];
values[0] = 10;

ref int first = ref values[0];
first = 20;
```

Úsalas solo cuando layout y allocation cost importen. Las reglas son deliberadamente estrictas; luchar contra ellas suele indicar que el diseño intenta hacer escapar memoria short-lived demasiado lejos.
