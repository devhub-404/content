# Narrowing com `instanceof`, `in` e Igualdade

`instanceof` faz narrowing usando relação com constructor em runtime. O operador `in` pode estreitar unions pela existência de propriedade. Igualdade entre variáveis relacionadas ou contra literals também pode fazer o checker inferir tipo compatível comum.

```ts
function read(value: Date | { text: string }) {
  if (value instanceof Date) {
    return value.toISOString();
  }

  if ("text" in value) {
    return value.text;
  }

  return "";
}
```

Esses checks só são significativos conforme o modelo de runtime. Interfaces desaparecem em runtime, então `instanceof SomeInterface` é impossível. Objetos cross-realm também podem tornar identidade de constructor surpreendente. Prefira discriminants ou validação explícita para dados simples e reserve `instanceof` para relações reais de classe/constructor.
