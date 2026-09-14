# Error Boundaries

An Error Boundary catches errors thrown while rendering descendants and can replace the failed subtree with fallback UI. In core React, defining a traditional Error Boundary still uses a class component or a framework/library wrapper built around that mechanism.

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

Boundaries do not catch every error source, such as arbitrary event-handler exceptions. Place them around meaningful failure regions so one broken widget does not necessarily remove the entire application. Report the original error to monitoring while showing users a safe, useful fallback.
