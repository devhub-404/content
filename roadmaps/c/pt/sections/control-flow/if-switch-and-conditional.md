# `if`, `switch` e Operador Condicional

`if` seleciona um branch a partir de condição scalar, enquanto `switch` despacha valores inteiros ou enums por `case`. Um case continua no seguinte se não houver `break`, `return` ou outro jump, então fallthrough intencional deve ser explícito.

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

O operador condicional `?:` é uma expressão e funciona bem quando um valor depende de uma condição. Mantenha condições e cases focados em decisões de domínio. Warnings do compilador ajudam a encontrar fallthrough suspeito, condições duplicadas e casos inalcançáveis.
