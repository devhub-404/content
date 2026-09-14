# Condicionales

`if`, `else if` y `else` ramifican según truthiness. El operador ternario `condición ? a : b` funciona bien para elegir entre dos valores, pero ternarios anidados suelen ser menos legibles que branching normal.

```js
if (score >= 90) {
  grade = "A";
} else if (score >= 80) {
  grade = "B";
} else {
  grade = "C";
}

const status = active ? "online" : "offline";
```

`switch` compara una expresión con casos discretos usando igualdad estricta. Los cases continúan hasta `break`, `return` u otra salida, así que cualquier fallthrough intencional debe quedar claro. Elige la estructura que haga las reglas del dominio más fáciles de leer.
