# Structs

Una `struct` agrupa miembros con nombre en un tipo de objeto. Los miembros se disponen en orden de declaración con posible padding por alignment. Los designated initializers hacen la inicialización más clara y menos dependiente de recordar posiciones.

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

Copiar una struct copia sus miembros como valor, pero los punteros internos siguen apuntando a los mismos objetos. No serialices una struct volcando sus bytes salvo que un protocolo defina exactamente esa representación; padding, endianness y representación pueden variar.
