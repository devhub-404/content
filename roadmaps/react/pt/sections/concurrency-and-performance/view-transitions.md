# React View Transitions

React 19.3 estabiliza `<ViewTransition>`, integrando updates do React à View Transition API do navegador para animar UI que entra, sai, move ou muda de tamanho entre renders. React coordena nomes e lifecycle com seu trabalho de rendering.

```jsx
function Profile({ user }) {
  return (
    <ViewTransition name={`avatar-${user.id}`}>
      <img src={user.avatar} alt="" />
    </ViewTransition>
  );
}
```

Animation deve reforçar navigation/state change, não esconder lentidão. Respeite reduced-motion e preserve focus/navigation semânticos. View transitions dependem do browser, então projete primeiro resultado utilizável sem animation e trate motion como enhancement.
