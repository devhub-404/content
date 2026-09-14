# Literal types y unions

Un literal type representa un valor exacto, como `"dark"` o `200`. Un union type combina alternativas con `|`, por lo que una API puede describir varios estados legítimos sin perder precisión. Cuando el vocabulario permitido es conocido, un union de literals suele ser mejor que un `string` abierto.

```ts
type Theme = "light" | "dark" | "system";
type Id = string | number;

function setTheme(theme: Theme) {
  // ...
}
```

Hasta que el flujo haga narrowing, una operación sobre un union debe ser válida para todos sus miembros. Diseñar estados como miembros separados de una union suele ser más seguro que un único objeto con muchas propiedades opcionales.
