# Lifting y Compartir State

Cuando varios components deben coincidir sobre la misma información, mueve el state al owner común más cercano y pasa values/callbacks hacia abajo. Esto crea un valor autoritativo en vez de varias copias que pueden divergir.

```jsx
function Accordion() {
  const [openId, setOpenId] = useState(null);

  return items.map(item => (
    <Panel
      key={item.id}
      open={openId === item.id}
      onOpen={() => setOpenId(item.id)}
    />
  ));
}
```

No subas todo state local a la raíz. El state debe vivir tan abajo como sea posible mientras todos los consumers coordinados puedan accederlo. Esto mantiene components reutilizables y reduce dependencias afectadas por cada update.
