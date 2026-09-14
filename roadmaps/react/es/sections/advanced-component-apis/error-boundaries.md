# Error Boundaries

Un Error Boundary captura errors lanzados al renderizar descendants y puede sustituir el subtree con fallback UI. En React core, definir un boundary tradicional aún usa un class component o un wrapper de framework/library construido sobre ese mecanismo.

```jsx
class ErrorBoundary extends React.Component {
  state = { failed: false };

  static getDerivedStateFromError() {
    return { failed: true };
  }

  render() {
    return this.state.failed ? <p>Something went wrong.</p> : this.props.children;
  }
}
```

Los boundaries no capturan toda fuente de error, como exceptions arbitrarias en event handlers. Colócalos en regiones de fallo significativas. Reporta el error original al monitoring mientras muestras un fallback seguro y útil.
