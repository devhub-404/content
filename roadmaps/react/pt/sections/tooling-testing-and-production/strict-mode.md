# Strict Mode

`<StrictMode>` habilita checks extras em development para revelar rendering impuro, cleanup ausente, APIs deprecated e padrões frágeis. Algumas functions rodam vezes extras de propósito para expor problemas.

```jsx
createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

Não “corrija” Strict Mode com flags que escondem setup duplicado. Torne rendering puro e Effects simétricos. Checks são development-only e não significam duplicação literal em production, mas código que passa neles tende a ser mais resiliente.
