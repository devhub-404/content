# React View Transitions

React 19.3 estabiliza `<ViewTransition>`, integrando updates de React con la View Transition API del navegador para animar UI que entra, sale, se mueve o cambia de tamaño entre renders. React coordina nombres y lifecycle con su trabajo de rendering.

```jsx
function Profile({ user }) {
  return (
    <ViewTransition name={`avatar-${user.id}`}>
      <img src={user.avatar} alt="" />
    </ViewTransition>
  );
}
```

La animation debe reforzar navigation/state change, no ocultar lentitud. Respeta reduced-motion y conserva focus/navigation semánticos. View transitions dependen del browser, así que diseña primero un resultado usable sin animation y trata motion como enhancement.
