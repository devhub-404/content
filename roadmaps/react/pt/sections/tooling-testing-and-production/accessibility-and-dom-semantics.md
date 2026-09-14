# Acessibilidade e Semântica do DOM

React renderiza elementos da web platform, então HTML semântico e accessibility continuam sendo base. Use buttons reais para actions, links para navigation, labels em fields, heading hierarchy, landmarks e keyboard behavior nativo antes de ARIA.

```jsx
function Menu() {
  return (
    <nav aria-label="Account">
      <ul>
        <li><a href="/profile">Profile</a></li>
        <li><button type="button">Sign out</button></li>
      </ul>
    </nav>
  );
}
```

UI stateful também precisa cuidar de focus, announcements, disabled states e reduced motion. React não torna custom component acessível automaticamente. Projete APIs que preservem semântica nativa em vez de exigir reconstrução a cada uso.
