# Compiler y Updates Granulares del DOM

El compiler de Solid transforma JSX en creación DOM eficiente y update code reactivo. Las partes estáticas se crean una vez, mientras las expresiones dinámicas se suscriben a los valores reactivos que leen. La función del component normalmente no se vuelve a llamar solo porque cambie un signal.

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

Por eso, consejos de performance de frameworks con virtual DOM no se transfieren mecánicamente. Normalmente no necesitas memoizar components para evitar rerenders. Entiende qué expresiones leen qué signals y mantén el reactive work en la computation más pequeña útil.
