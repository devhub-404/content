# Discriminated Unions

Discriminated union fornece a cada membro uma propriedade compartilhada cujo valor literal identifica aquele membro. Verificar o discriminant estreita o objeto inteiro, então campos pertencentes apenas a um estado ficam disponíveis sem casts.

```ts
type Result =
  | { status: "ok"; value: string }
  | { status: "error"; error: Error };

function show(result: Result) {
  if (result.status === "ok") {
    return result.value;
  }

  return result.error.message;
}
```

Esse é um dos padrões mais fortes do TypeScript para estados de UI, mensagens de protocolo, resultados de comandos e workflows de domínio. Evita combinações impossíveis como `{ loading: true, data: ..., error: ... }` quando estados deveriam ser exclusivos. Modele estados como formas válidas separadas em vez de um saco de propriedades opcionais.
