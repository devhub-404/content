# Function Overloads

Overload signatures descrevem várias formas de chamada suportadas seguidas por uma única implementação. Callers enxergam os overloads, enquanto a implementação precisa ser compatível com eles. Overloads são úteis quando retorno ou parâmetros válidos mudam conforme a forma da chamada.

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

Prefira parâmetros union ou generics quando descrevem a relação de forma mais direta. Muitos overloads que diferem pouco são difíceis de manter e podem inferir mal para callers com union values. A assinatura de implementação não é overload público adicional, então documente as formas suportadas na lista de overloads.
