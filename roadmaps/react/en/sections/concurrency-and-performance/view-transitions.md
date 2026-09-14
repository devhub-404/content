# React View Transitions

React 19.3 stabilizes `<ViewTransition>`, which integrates React updates with the browser View Transition API so entering, leaving, moving, or resizing UI can animate across renders. React coordinates names and transition lifecycle with its rendering work.

```jsx
function Profile({ user }) {
  return (
    <ViewTransition name={`avatar-${user.id}`}>
      <img src={user.avatar} alt="" />
    </ViewTransition>
  );
}
```

Animation should reinforce navigation and state change rather than hide slow work. Respect reduced-motion preferences and keep semantic focus/navigation behavior correct. View transitions depend on browser capabilities, so design a usable non-animated result first and treat motion as enhancement.
