# Suspense e Lazy Loading

`lazy` adia carregamento de um module de component até o primeiro render. Suspense boundary fornece fallback enquanto child está suspended, seja por lazy code ou data source/framework integrado ao modelo de Suspense.

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

Suspense é mecanismo de coordenação de rendering, não API universal de fetch por si só. Coloque boundaries em regiões significativas para uma área lenta não apagar a página inteira. Boundaries aninhadas permitem reveal progressivo.
