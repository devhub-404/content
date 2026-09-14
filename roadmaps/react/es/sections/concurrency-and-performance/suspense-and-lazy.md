# Suspense y Lazy Loading

`lazy` difiere la carga de un module de component hasta su primer render. Una Suspense boundary ofrece fallback mientras un child está suspended, ya sea por lazy code o una data source/framework integrada con Suspense.

```jsx
const Settings = lazy(() => import('./Settings.jsx'));

function App() {
  return (
    <Suspense fallback={<p>Loading settings…</p>}>
      <Settings />
    </Suspense>
  );
}
```

Suspense es un mecanismo de coordinación de rendering, no una API universal de fetch por sí sola. Coloca boundaries alrededor de regiones significativas para que una zona lenta no vacíe toda la página. Boundaries anidadas permiten reveal progresivo.
