# Convenções de Ownership em APIs C

C não possui ownership checker na linguagem, então APIs precisam estabelecer convenções. Um ponteiro pode ser borrowed durante a chamada, retido pelo callee, transferido a ele ou retornado com ownership ao caller. Documente esses casos e reflita-os em nomes e tipos quando possível.

```c
struct buffer {
    unsigned char *data;
    size_t length;
};

void buffer_destroy(struct buffer *buffer) {
    free(buffer->data);
    buffer->data = nullptr;
    buffer->length = 0;
}
```

Associe funções que criam recursos a destroy/free claros, inicialize owners em estado vazio seguro e encapsule ponteiro mais length/capacity em structs para reduzir invariantes separadas.
