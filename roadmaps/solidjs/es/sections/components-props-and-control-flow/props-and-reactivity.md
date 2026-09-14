# Props y Acceso Reactivo

Las props de Solid son property accessors read-only cuyos values pueden seguir reactivos. Leer `props.name` en JSX tracked crea la dependency esperada. Destructuring eager puede perder reactividad de propiedad salvo con helpers adecuados.

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Avoid eagerly copying a reactive prop into a plain local value.
```

Trata props como interfaz del parent, no state a mutar. Usa `mergeProps` para defaults y `splitProps` para separar options propias de attributes reenviados. Mantén reactive reads tardíos, cerca de donde se usan.
