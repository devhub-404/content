# Mapped Types

Mapped type itera sobre union de property keys para construir novo object type. A fonte comum é `keyof T`. Mapping modifiers podem adicionar ou remover `readonly` e optional, e vários utility types padrão usam esse mecanismo.

```ts
type Flags<T> = {
  [K in keyof T]: boolean;
};

type Mutable<T> = {
  -readonly [K in keyof T]-?: T[K];
};
```

Mapped types são ideais para transformações sistemáticas como “mesmas chaves, outro value type” ou “todas propriedades opcionais”. Key remapping com `as` pode renomear ou filtrar chaves. Mantenha nomes das transformações significativos; pilha densa de mapped e conditional helpers pode deixar mensagens de erro muito difíceis.
