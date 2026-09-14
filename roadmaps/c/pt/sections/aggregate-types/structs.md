# Structures

Uma `struct` agrupa membros nomeados em um tipo de objeto. Os membros aparecem em ordem de declaração com possível padding de alignment. Designated initializers tornam inicialização mais clara e menos dependente de posição.

```c
struct user {
    int id;
    char name[32];
};

struct user u = {
    .id = 42,
    .name = "Mina",
};
```

Copiar uma struct copia seus membros como valor, mas ponteiros internos continuam apontando aos mesmos objetos. Não serialize uma struct despejando bytes brutos salvo protocolo que defina exatamente essa representação; padding, endianness e representação podem variar.
