# Children, Fragments e Composition

Composition permite que um component receba JSX do parent via `children` ou outras props de elementos. Isso costuma ser mais flexível que adicionar muitos boolean props para cada layout interno. Fragments agrupam siblings sem criar elemento DOM extra.

```jsx
function Card({ title, children }) {
  return (
    <section className="card">
      <h2>{title}</h2>
      {children}
    </section>
  );
}
```

Prefira composition quando o wrapper não deve conhecer detalhes internos do conteúdo. Props de elementos nomeadas podem representar vários slots, como `header` e `footer`. Mantenha a API concreta para callers entenderem a estrutura esperada sem ler toda implementação.
