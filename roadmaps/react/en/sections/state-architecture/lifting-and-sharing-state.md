# Lifting and Sharing State

When several components must agree on the same information, move that state to their closest common owner and pass values and callbacks down. This creates one authoritative state value instead of several copies that can drift apart.

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

Do not lift every local interaction state to the application root. State should live as low as possible while still being shared by all consumers that need coordination. This keeps components reusable and reduces the number of renders and dependencies affected by an update.
