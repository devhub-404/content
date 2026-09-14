# Type Aliases e Interfaces

Type aliases e interfaces podem descrever formas de objetos. Interfaces são projetadas para contratos nomeados de objeto e podem participar de declaration merging e `extends`. Type aliases podem nomear qualquer expressão de tipo, incluindo unions, tuples, primitivos, mapped types e conditional types.

```ts
type Point = {
  x: number;
  y: number;
};

interface User {
  id: string;
  name: string;
}
```

Para modelagem comum de objetos, ambos podem estar corretos; consistência e recursos necessários importam mais que slogans como “sempre use interface”. Use interface quando contratos abertos/mergeable são intencionais e aliases ao compor expressões arbitrárias. Nenhum cria constructor ou validador de runtime.
