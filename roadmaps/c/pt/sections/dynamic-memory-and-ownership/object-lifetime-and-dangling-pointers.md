# Lifetime de Objetos e Dangling Pointers

Um ponteiro pode continuar numericamente não-null após o objeto referido terminar seu lifetime. Ele então é dangling e não pode ser dereferenced. Objetos automáticos normalmente morrem ao sair do bloco; alocações dinâmicas terminam com deallocation correspondente.

```c
int *bad_pointer(void) {
    int value = 42;
    return &value; /* wrong: value dies on return */
}
```

Não retorne ponteiro para variável local comum, não armazene borrowed pointer além do owner e não acesse após `free`. Colocar um alias em null pode evitar reuso por aquele nome, mas não corrige outros aliases para o objeto morto.
