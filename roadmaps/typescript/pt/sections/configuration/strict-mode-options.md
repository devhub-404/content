# A Família `strict`

`strict` habilita família de checks como tratamento estrito de null, regras de variância de funções, initialization checks e detecção de implicit any. É baseline adequado para a maioria dos projetos novos porque o checker consegue fazer garantias mais fortes sobre código comum.

```ts
{
  "compilerOptions": {
    "strict": true,
    "noImplicitOverride": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true
  }
}
```

Opções adicionais como `noUncheckedIndexedAccess`, `exactOptionalPropertyTypes` e `noImplicitOverride` apertam áreas específicas além do strict principal. Habilite intencionalmente e entenda o modelo imposto. Projeto estrito pode exigir mais cuidado em fronteiras, mas isso normalmente revela incerteza real que já existia em runtime.
