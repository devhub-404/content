# Escopo, Linkage e Storage Duration

Scope responde onde um nome é visível, linkage se declarações em locais diferentes referem-se à mesma entidade e storage duration descreve por quanto tempo um objeto existe. São conceitos distintos mesmo que keywords como `static` participem de mais de um.

```c
static int file_counter;

void tick(void) {
    static int calls;
    ++calls;
    ++file_counter;
}
```

Um local de bloco normalmente tem automatic storage. Um nome `static` em file scope possui internal linkage, enquanto um objeto `static` em block scope persiste durante todo o programa. Entenda cada efeito em vez de traduzir `static` como uma ideia vaga de “global”.
