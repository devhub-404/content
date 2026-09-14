# Discriminated unions

Una discriminated union da a cada miembro una propiedad común con un literal distinto, como `status: "ok"` o `status: "error"`. Al comprobar ese discriminant, TypeScript reduce todo el objeto y habilita los campos propios de ese estado.

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

Es uno de los mejores patrones para estados de UI, mensajes de protocolo y workflows de dominio. En vez de un objeto con muchos flags y propiedades opcionales, modela cada estado válido como una forma separada para que combinaciones imposibles sean difíciles de representar.
