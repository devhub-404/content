# Configurações de Módulo no TypeScript 6.0

Configuração de módulos é uma das partes mais sensíveis ao ambiente no TypeScript. Projetos Node modernos geralmente usam modos conscientes de Node; projetos dirigidos por bundler frequentemente usam resolução orientada ao bundler. O setting deve descrever como imports são interpretados pelo runtime ou sistema de build real.

```ts
{
  "compilerOptions": {
    "module": "nodenext",
    "moduleResolution": "nodenext",
    "verbatimModuleSyntax": true
  }
}
```

TypeScript 6.0 deprecia várias opções legadas, incluindo resolução antiga `node10`/`classic` e emits AMD/UMD/SystemJS. Também move defaults em direção a interoperabilidade moderna. Código novo não deve começar com config legada só porque tutorial antigo a usou; comece pelo template oficial atual do runtime.
