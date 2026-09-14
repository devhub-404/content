# Narrowing con `instanceof`, `in` e igualdad

`instanceof` hace narrowing según una relación real de constructor, `in` según la presencia de una propiedad y comparaciones de igualdad pueden revelar un tipo compatible común. Son mecanismos de runtime que el checker entiende.

```ts
function read(value: Date | { text: string }) {
  if (value instanceof Date) {
    return value.toISOString();
  }

  if ("text" in value) {
    return value.text;
  }

  return "";
}
```

Las interfaces no existen en runtime, por lo que no puedes usarlas con `instanceof`. Para datos simples, discriminants o validación explícita suelen ser mejores; reserva `instanceof` para objetos que realmente provienen de constructors o classes.
