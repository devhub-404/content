# Projetando APIs C Manuteníveis

APIs C manuteníveis deixam ownership, lifetime, mutabilidade, tamanhos de buffer e erros explícitos. Opaque structs escondem implementação enquanto expõem handle estável. Funções devem dizer se ponteiros podem ser null e se memória é borrowed ou transferida.

```c
struct parser;

struct parser *parser_create(void);
int parser_feed(struct parser *, const void *, size_t);
void parser_destroy(struct parser *);
```

Prefira operações pequenas e ortogonais a funções enormes com muitas flags e associe creators a destroyers. Versione structs públicos com cuidado porque size/layout podem virar ABI. Uma boa API reduz regras implícitas que o caller precisa memorizar.
