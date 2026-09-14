# `if`, `switch` y Operador Condicional

`if` selecciona una rama a partir de una condición scalar, mientras `switch` despacha valores enteros o enums mediante `case`. Un case continúa al siguiente si no sale con `break`, `return` u otro salto, así que el fallthrough intencional debe quedar explícito.

```c
if (score >= 90) {
    grade = 'A';
} else if (score >= 80) {
    grade = 'B';
} else {
    grade = 'C';
}

const char *label = ready ? "ready" : "waiting";
```

El operador condicional `?:` es una expresión y resulta útil cuando un valor depende de una condición. Mantén las condiciones y cases centrados en decisiones del dominio. Los warnings ayudan a detectar fallthrough sospechoso, condiciones duplicadas y casos inalcanzables.
