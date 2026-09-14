# Pacotes de Tipos Ambient e `types`

Pacotes de tipos ambient podem adicionar globals e declarations ao projeto, normalmente por pacotes `@types` ou tipos fornecidos pelo próprio pacote. A opção `types` escolhe explicitamente quais pacotes ambient entram no escopo global.

```ts
{
  "compilerOptions": {
    "types": ["node", "vitest/globals"]
  }
}
```

TypeScript 6.0 muda `types` para default vazio, tornando inclusão ambient mais explícita. Isso reduz dependência acidental em pacotes não relacionados instalados em outro ponto do workspace. Tipos de módulos importáveis continuam resolvendo normalmente; a opção trata de pacotes que contribuem globals sem import explícito.
