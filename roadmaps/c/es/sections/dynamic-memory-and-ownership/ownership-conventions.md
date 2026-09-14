# Convenciones de Ownership en APIs C

C no tiene un ownership checker en el lenguaje, así que las APIs deben establecer convenciones. Un puntero puede ser borrowed durante la llamada, retenido por el callee, transferido o devuelto con ownership al caller. Documenta esos casos y refléjalos en nombres y tipos cuando sea posible.

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

Empareja funciones que crean recursos con destroy/free claros, inicializa owners en un estado vacío seguro y encapsula puntero más length/capacity en structs para reducir invariantes separadas.
