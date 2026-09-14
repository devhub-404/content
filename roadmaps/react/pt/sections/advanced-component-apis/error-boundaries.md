# Error Boundaries

Error Boundary captura errors lançados ao renderizar descendants e pode substituir subtree com fallback UI. No React core, definir boundary tradicional ainda usa class component ou wrapper de framework/library construído sobre esse mecanismo.

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

Boundaries não capturam toda origem de error, como exceptions arbitrárias em event handlers. Coloque em regiões de falha significativas. Reporte error original ao monitoring enquanto mostra fallback seguro e útil.
