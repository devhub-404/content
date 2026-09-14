# Ambient Declarations e Module Augmentation

Ambient declarations descrevem valores ou módulos que existem em runtime mas não são definidos no source TypeScript atual. Module e global augmentation podem adicionar declarations a tipos existentes quando uma extensão real de runtime também existe.

```ts
declare global {
  interface Window {
    appVersion: string;
  }
}

declare module "some-library" {
  interface Options {
    traceId?: string;
  }
}

export {};
```

Augmentation muda apenas o sistema de tipos. Se você declarar que `window.appVersion` existe mas nenhum script o cria, runtime ainda falha. Mantenha augmentations perto do código que realiza o patch de runtime e use com parcimônia; extensões globais escondidas tornam ownership e ordem de dependências difíceis.
