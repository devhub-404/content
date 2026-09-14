# Unions e Tagged Unions

Uma union sobrepõe vários membros no mesmo storage. Em cada ponto lógico, o programa precisa saber qual representação está ativa e quais acessos são permitidos. Unions são úteis para variants compactos e trabalho de representação de baixo nível.

```c
enum value_kind { VALUE_INT, VALUE_DOUBLE };

struct value {
    enum value_kind kind;
    union {
        int as_int;
        double as_double;
    } data;
};
```

Uma tagged union combina a union com um discriminador explícito para selecionar o membro correto. Mantenha tag e payload consistentes. É um padrão equivalente a variant algébrico em C, mas o compilador não garante exaustividade nem consistência automaticamente.
