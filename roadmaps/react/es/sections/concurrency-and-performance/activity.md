# Preservando UI Oculta con `<Activity>`

`<Activity>` puede ocultar un subtree preservando su state para volver visible sin recrear todo. El trabajo hidden recibe menor prioridad y los Effects siguen la semántica de Activity, por lo que es distinto de ocultar solo con CSS.

```jsx
function Tabs({ active }) {
  return (
    <>
      <Activity mode={active === 'feed' ? 'visible' : 'hidden'}>
        <Feed />
      </Activity>
      <Activity mode={active === 'messages' ? 'visible' : 'hidden'}>
        <Messages />
      </Activity>
    </>
  );
}
```

Úsalo cuando conservar local state y UI preparada tenga valor real, como tabs o superficies de navegación. Mantiene memoria/state vivos, así que no retengas trees grandes indefinidamente sin evaluar el coste y si un remount sería más simple.
