# Function Type Expressions e Call Signatures

Function type expressions descrevem valores chamáveis de forma concisa. Call signatures em object types são úteis quando valor chamável também possui propriedades. TypeScript verifica compatibilidade de parâmetros e retorno quando funções são atribuídas ou passadas como callbacks.

```ts
type Formatter = (value: number) => string;

type Describable = {
  description: string;
  (value: number): string;
};
```

Diferencie sintaxe de declaração de função em runtime do tipo que descreve comportamento chamável. Type aliases para callbacks importantes tornam APIs de eventos, pipelines e dependências mais legíveis. Evite anotar toda arrow local quando contextual typing já fornece expectativas corretas de parâmetros e retorno.
