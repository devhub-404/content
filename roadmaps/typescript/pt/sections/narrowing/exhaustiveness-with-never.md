# Exaustividade com `never`

Depois que todo membro de uma union é eliminado pelo fluxo, o tipo restante é `never`. Atribuir valor supostamente inalcançável a `never` é forma comum de tornar switch exaustivo em compile time.

```ts
type Action =
  | { type: "save" }
  | { type: "delete"; id: string };

function handle(action: Action) {
  switch (action.type) {
    case "save":
      return save();
    case "delete":
      return remove(action.id);
    default: {
      const exhaustive: never = action;
      return exhaustive;
    }
  }
}
```

Quando novo membro é adicionado depois, o branch default deixa de ser impossível e a atribuição gera erro, direcionando a atualização do handler. Isso é especialmente útil para reducers, mensagens de protocolo, state machines e comandos onde esquecer um caso novo viraria lacuna de runtime.
