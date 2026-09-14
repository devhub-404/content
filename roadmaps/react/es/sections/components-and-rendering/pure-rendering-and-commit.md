# Rendering Puro y Commit Phase

Un render debe ser puro: los mismos props, state y context deben producir el mismo JSX sin mutar datos externos. Así React puede llamar la lógica de rendering cuando sea necesario y solo hacer commit del resultado elegido al DOM después de que el render tenga éxito.

```jsx
function Price({ amount }) {
  const formatted = new Intl.NumberFormat('en', {
    style: 'currency',
    currency: 'USD'
  }).format(amount);

  return <span>{formatted}</span>;
}
```

No inicies requests, mutes el DOM, escribas storage o cambies state de module durante render. Los cálculos deterministas están bien. El trabajo que sincroniza React con un sistema externo pertenece a events, effects, APIs de datos del servidor u otra boundary explícita.
