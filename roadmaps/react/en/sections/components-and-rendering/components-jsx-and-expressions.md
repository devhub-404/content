# Components, JSX, and Expressions

JSX is syntax for writing element descriptions close to the JavaScript that prepares their data. Braces enter JavaScript expressions, attributes use React's DOM naming rules such as `className`, and a component must return one root expression, often using a fragment when no wrapper element is needed.

```jsx
function Greeting({ name }) {
  const message = `Hello, ${name}`;
  return <h1 className="greeting">{message}</h1>;
}
```

JSX is not a template string and it does not execute arbitrary statements inside braces. Compute values before the returned JSX or use expressions such as conditional operators and array mapping. Keep markup semantic because React does not change HTML accessibility rules for you.
