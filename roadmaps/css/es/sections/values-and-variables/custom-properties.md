# Custom properties y `var()`

Las custom properties almacenan secuencias de tokens que participan en la cascada y se leen con `var()`. Normalmente heredan, por lo que pueden redefinirse en la raíz, un tema, un componente, un estado o una media/container query y propagarse a los descendientes.

```css
:root {
  --surface: white;
  --text: #161616;
  --space-card: 1rem;
}

.card {
  color: var(--text);
  background: var(--surface);
  padding: var(--space-card, 1rem);
}

[data-theme="dark"] {
  --surface: #161616;
  --text: white;
}
```

El segundo argumento de `var()` es un fallback cuando la variable falta o no puede proporcionar un valor usable; no es un fallback de compatibilidad del navegador. Usa nombres semánticos como `--surface` o `--space-card` cuando la variable representa un papel de diseño, no solo un valor literal.
