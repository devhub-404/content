# Ponteiros e Indireção

Um ponteiro armazena um endereço ou valor de ponteiro referente a objeto, função ou posição one-past conforme as regras de C. `&` obtém endereço e `*` faz dereference para acessar o objeto referido.

```c
int value = 42;
int *ptr = &value;

*ptr = 50;
printf("%d
", value);
```

O ponteiro precisa ser válido para a operação e relacionado a um objeto dentro de lifetime adequado. Dereference de ponteiro null, dangling, não inicializado ou inválido é undefined behavior. Trate validade e ownership como invariantes explícitas.
