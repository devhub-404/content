# Accesibilidad y Semántica del DOM

React renderiza elementos de la web platform, por lo que HTML semántico y accessibility siguen siendo la base. Usa buttons reales para actions, links para navigation, labels en fields, heading hierarchy, landmarks y keyboard behavior nativo antes de ARIA.

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

La UI stateful también debe cuidar focus, announcements, disabled states y reduced motion. React no vuelve accesible un custom component automáticamente. Diseña APIs que conserven semántica nativa en vez de exigir reconstruirla en cada uso.
