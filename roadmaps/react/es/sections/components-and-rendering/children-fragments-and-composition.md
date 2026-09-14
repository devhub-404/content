# Children, Fragments y Composition

Composition permite que un component reciba JSX del parent mediante `children` u otras props de elementos. Suele ser más flexible que añadir muchos boolean props para cada layout interno. Los fragments agrupan siblings sin crear un elemento DOM extra.

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

Prefiere composition cuando el wrapper no debe conocer los detalles internos del contenido. Props de elementos con nombre pueden representar varios slots, como `header` y `footer`. Mantén la API concreta para que callers entiendan la estructura esperada sin leer toda la implementación.
