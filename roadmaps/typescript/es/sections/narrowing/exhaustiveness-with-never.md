# Exhaustividad con `never`

Cuando el flujo elimina todos los miembros posibles de una union, el tipo restante es `never`. Asignar la rama supuestamente imposible a `never` permite convertir un `switch` en una comprobación exhaustiva en compile time.

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

Si más tarde aparece un nuevo miembro de la union, esa rama deja de ser imposible y TypeScript produce un error. Es especialmente útil para reducers, state machines, comandos y protocolos donde olvidar un nuevo caso causaría una laguna de comportamiento.
