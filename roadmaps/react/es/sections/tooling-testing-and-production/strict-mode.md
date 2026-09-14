# Strict Mode

`<StrictMode>` habilita checks extra en development para revelar rendering impuro, cleanup ausente, APIs deprecated y patrones frágiles. Algunas functions se ejecutan veces extra deliberadamente para exponer problemas.

```jsx
createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

No “arregles” Strict Mode con flags que oculten setup duplicado. Haz rendering puro y Effects simétricos. Los checks son development-only y no significan duplicación literal en production, pero el código que los supera suele ser más resiliente.
