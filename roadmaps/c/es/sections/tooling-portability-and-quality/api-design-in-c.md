# Diseñando APIs C Mantenibles

Las APIs C mantenibles hacen explícitos ownership, lifetime, mutabilidad, tamaños de buffer y errores. Las opaque structs esconden implementación mientras exponen un handle estable. Las funciones deben indicar si los punteros pueden ser null y si la memoria se presta o se transfiere.

```c
struct parser;

struct parser *parser_create(void);
int parser_feed(struct parser *, const void *, size_t);
void parser_destroy(struct parser *);
```

Prefiere operaciones pequeñas y ortogonales a funciones enormes con muchas flags y empareja creadores con destructores. Versiona structs públicos con cuidado porque size/layout pueden formar parte de la ABI. Una buena API reduce reglas implícitas que el caller debe recordar.
