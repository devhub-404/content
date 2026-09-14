# React Model and the Component Tree

React builds user interfaces from components: JavaScript functions that describe what the UI should look like for their current inputs. Components compose into a tree, and React reconciles later renders of that tree with the host environment, usually the browser DOM.

```jsx
function App() {
  return (
    <main>
      <Header />
      <Profile />
    </main>
  );
}
```

Think in terms of data flowing down the component tree rather than manually editing DOM nodes. A component render should describe UI, not perform unrelated work. React may render components more than once, interrupt work, or discard a render before committing it.
