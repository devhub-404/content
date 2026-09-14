# Template Literal Types

Template literal types constroem string literal types interpolando outros literal types. Quando posição substituída é union, TypeScript forma as combinações correspondentes. É útil para nomes de eventos, padrões de rota, APIs derivadas de propriedades e outras convenções de string estruturadas.

```ts
type EventName<T extends string> = `${T}Changed`;

type Field = "name" | "email";
type FieldEvent = EventName<Field>;
// "nameChanged" | "emailChanged"
```

Esses tipos descrevem relações de strings em compile time; não fazem parse ou validação de strings arbitrárias em runtime. Grandes produtos cartesianos de unions podem ficar caros e difíceis. Prefira dados gerados ou tipos string mais simples quando o vocabulário é enorme em vez de forçar o checker a enumerar milhares de combinações.
