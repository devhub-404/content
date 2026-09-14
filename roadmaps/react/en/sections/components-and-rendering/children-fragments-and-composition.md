# Children, Fragments, and Composition

Composition lets a component accept JSX from its parent through `children` or other element-valued props. This is often more flexible than adding many boolean props for every possible nested layout. Fragments group siblings without creating an extra DOM element.

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

Prefer composition when a wrapper should not know the implementation details of its content. Named element props can express several slots, such as `header` and `footer`. Keep the API concrete enough that callers can understand the expected structure without reverse-engineering the component body.
