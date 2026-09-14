# Ponteiros Nulos e `nullptr`

Um null pointer representa ausência de objeto ou função. C23 adiciona a keyword `nullptr` e `nullptr_t`, fornecendo uma constante dedicada em vez de depender apenas do inteiro zero ou da macro `NULL`.

```c
int *find_value(int *items, size_t n, int target) {
    for (size_t i = 0; i < n; ++i) {
        if (items[i] == target) return &items[i];
    }
    return nullptr;
}
```

Testar um ponteiro em condição continua idiomático, e dereference de null permanece inválido. APIs públicas devem documentar se null é valor opcional válido ou erro. Diferencie ponteiro null de array vazio ou ponteiro válido acompanhado de length zero.
