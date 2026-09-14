# Optional, Readonly e Index Signatures

Uma propriedade marcada com `?` pode estar ausente. Uma propriedade `readonly` não pode ser atribuída por aquela referência tipada após inicialização, embora readonly seja restrição de compile time e não faça deep freeze do objeto em runtime. Index signatures descrevem famílias de nomes cujas chaves exatas não são conhecidas antecipadamente.

```ts
interface Settings {
  readonly id: string;
  theme?: "light" | "dark";
  [key: `plugin:${string}`]: unknown;
}
```

Optional nem sempre significa o mesmo que “presente com valor `undefined`”, especialmente com opções mais estritas. Index signatures devem representar domínio real de chaves dinâmicas; evite `[key: string]: any` apenas para silenciar erros em objeto cujos campos são conhecidos. Prefira propriedades explícitas mais pattern de índice estreito.
