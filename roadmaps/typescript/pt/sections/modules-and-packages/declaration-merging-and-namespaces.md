# Declaration Merging e Namespaces

Algumas declarations com mesmo nome fazem merge, especialmente interfaces e certas combinações com namespace. Isso suporta contratos extensíveis de biblioteca e padrões de ecossistemas JavaScript existentes. Também significa que interface pode ser intencionalmente aberta, não declaração fechada única.

```ts
interface Box {
  width: number;
}

interface Box {
  height: number;
}

const box: Box = {
  width: 10,
  height: 20,
};
```

Namespaces são mecanismo legado de organização do TypeScript anterior ao uso amplo de ECMAScript modules. Continuam relevantes em declaration files e código existente, mas TypeScript 6.0 deprecia padrões legados orientados a módulos em novos projetos. Prefira ES modules padrão para source comum de aplicações e bibliotecas.
