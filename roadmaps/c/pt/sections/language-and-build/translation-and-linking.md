# Tradução, Compilação e Linkedição

Um programa C normalmente é dividido em translation units. O preprocessador trata diretivas como `#include`, cada source é traduzido para object code e o linker resolve símbolos externos para formar executável ou biblioteca. Erros de compilação, linking e runtime são etapas diferentes e indicam problemas diferentes.

```c
// math.c
int add(int a, int b) {
    return a + b;
}

// main.c
int add(int, int);

int main(void) {
    return add(2, 3) == 5 ? 0 : 1;
}
```

Declarações permitem que uma translation unit descreva símbolo definido em outra. Definições alocam storage ou fornecem corpos de função. Coloque declarações públicas em headers e inclua o mesmo header na implementação e nos consumidores para que o compilador verifique consistência.
