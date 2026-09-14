# `typeof` em Posições de Tipo

O `typeof` em posição de tipo obtém o tipo estático de valor ou propriedade que já existe no código. É diferente do operador `typeof` de runtime do JavaScript, embora use a mesma grafia.

```ts
const defaults = {
  retries: 3,
  mode: "safe" as const,
};

type Defaults = typeof defaults;

function configure(options: Partial<Defaults>) {
  // ...
}
```

É útil quando um valor é fonte da verdade e você quer que tipos o acompanhem em vez de duplicar uma forma de objeto. `typeof` de tipo é intencionalmente limitado a identificadores e acessos de propriedade, não expressões de runtime arbitrárias, mantendo extração previsível.
