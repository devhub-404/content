# Symbols e Hooks de Protocolo

Symbol é primitivo único usado frequentemente como property key que não colide com chaves string comuns. `Symbol()` sempre cria novo symbol, enquanto `Symbol.for()` usa registry global. Propriedades com chave symbol são omitidas por várias operações comuns de enumeração de chaves string.

```js
const internalId = Symbol("internalId");

const record = {
  [internalId]: 42,
  [Symbol.toStringTag]: "Record",
};
```

Well-known symbols definem protocolos e hooks da linguagem para iteração, async iteration, conversão primitiva, matching, species, disposal, tags de objeto e mais. Implemente esses hooks apenas quando um tipo realmente participa do protocolo correspondente. Symbols fornecem identidade e chaves de protocolo; não são barreira de segurança para dados privados.
