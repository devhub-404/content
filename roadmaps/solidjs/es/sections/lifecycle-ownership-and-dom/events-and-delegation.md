# Events y Event Delegation

Solid soporta event handlers JSX con delegation o native listeners según event/syntax. Delegation permite que muchos elements compartan listener en el document, mientras algunos events necesitan listener directo por comportamiento del browser.

```tsx
function Button() {
  function handleClick(event) {
    console.log(event.currentTarget.name);
  }

  return <button name="save" onClick={handleClick}>Save</button>;
}
```

Los handlers son functions normales y no crean reactive dependency solo por leer un signal al hacer click. Esto es útil: el handler ve el valor actual al ejecutarse sin rerun por state changes. Conserva semantic elements y keyboard behavior nativo.
