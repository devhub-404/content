# Design tokens y arquitectura de temas

Un sistema mantenible separa valores primitivos de roles semánticos. Un token puede representar un color literal, mientras `--color-action` o `--color-surface` expresa para qué se usa. Los componentes deberían consumir roles semánticos para que un tema cambie significado sin reescribir selectores.

```css
@layer tokens {
  :root {
    --color-blue-600: oklch(52% .2 255);
    --color-surface: white;
    --color-action: var(--color-blue-600);
    --space-card: 1rem;
  }

  [data-theme="dark"] {
    --color-surface: #151515;
  }
}
```

Cascade layers pueden dar prioridad explícita a tokens, base, componentes y utilities. Mantén pequeña la superficie pública de custom properties: toda variable de la que dependan consumidores se convierte en parte de una API de estilos.
