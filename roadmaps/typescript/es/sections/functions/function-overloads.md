# Function overloads

Los overload signatures describen varias formas de llamada admitidas y después una única implementación debe soportarlas. Los callers ven los overloads, no una firma de implementación adicional. Son útiles cuando parámetros o retorno cambian de forma significativa según la llamada.

```ts
function parse(value: string): string[];
function parse(value: Uint8Array): string[];
function parse(value: string | Uint8Array): string[] {
  const text =
    typeof value === "string"
      ? value
      : new TextDecoder().decode(value);

  return text.split(",");
}
```

Prefiere unions o generics cuando expresen la relación de manera más directa. Muchos overloads apenas distintos son difíciles de mantener y pueden inferir peor cuando el caller posee un union. Documenta todas las formas públicas reales en la lista de overloads.
