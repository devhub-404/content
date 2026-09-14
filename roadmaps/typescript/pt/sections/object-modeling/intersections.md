# Intersection Types

Uma intersection `A & B` descreve valor que satisfaz ambos os tipos ao mesmo tempo. Para object types isso normalmente combina conjuntos de propriedades obrigatórias. Intersections são úteis para composição, helpers mixin-like e APIs que adicionam capacidades a uma forma existente.

```ts
type Timestamped = {
  createdAt: Date;
};

type Entity = {
  id: string;
};

type StoredEntity = Entity & Timestamped;
```

Intersections não são operações de object spread e podem se tornar impossíveis quando a mesma propriedade é exigida com tipos incompatíveis. Prefira contrato nomeado claro quando intersections repetidas ficam difíceis de ler. Unions modelam alternativas; intersections modelam requisitos simultâneos.
