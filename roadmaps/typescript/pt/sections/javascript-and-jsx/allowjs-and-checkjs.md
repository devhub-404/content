# `allowJs` e `checkJs`

TypeScript pode incluir arquivos JavaScript no projeto com `allowJs` e verificá-los com `checkJs`. Isso permite adoção gradual sem converter todo arquivo para `.ts` de uma vez. Informação de tipos pode vir de sintaxe JavaScript, JSDoc, declaration files e bibliotecas importadas.

```ts
{
  "compilerOptions": {
    "allowJs": true,
    "checkJs": true,
    "noEmit": true
  }
}
```

Checking de JavaScript é intencionalmente mais flexível em algumas áreas porque padrões comuns de JS precisam continuar usáveis. Trate migração por fronteiras: habilite checks, anote APIs importantes, corrija erros reais e converta arquivos onde sintaxe TypeScript agrega valor. Evite renomear tudo em massa antes de o projeto realmente type-checkar.
