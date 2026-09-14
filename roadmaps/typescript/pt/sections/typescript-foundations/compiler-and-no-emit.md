# Type Checking, Emissão e `noEmit`

O compilador TypeScript pode verificar tipos e emitir JavaScript, mas esses trabalhos podem ser separados. Muitos projetos modernos deixam outra ferramenta transpilar ou bundle o código e usam `tsc --noEmit` apenas como typechecker. Outros usam `tsc` para produzir JavaScript e declaration files diretamente.

```ts
{
  "compilerOptions": {
    "strict": true,
    "noEmit": true
  }
}
```

A pergunta importante é qual ferramenta possui cada etapa: type checking, transformação de sintaxe, bundling de módulos, minificação e emissão de declarations. Não presuma que transpile bem-sucedido significa type check bem-sucedido. Um projeto pode emitir JavaScript mesmo com erros de tipo conforme configuração e tooling, então CI deve executar o checker deliberadamente.
