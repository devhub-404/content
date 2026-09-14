# Components, JSX y Expressions

JSX es sintaxis para escribir descripciones de elementos cerca del JavaScript que prepara sus datos. Las llaves introducen expressions JavaScript, los atributos usan nombres de React como `className`, y un component retorna una expresión raíz, a menudo un fragment cuando no necesita wrapper.

```jsx
function Greeting({ name }) {
  const message = `Hello, ${name}`;
  return <h1 className="greeting">{message}</h1>;
}
```

JSX no es un template string y no ejecuta statements arbitrarios dentro de las llaves. Calcula valores antes del JSX retornado o usa expressions como el operador condicional y `map`. Mantén markup semántico porque React no cambia las reglas de accesibilidad de HTML.
