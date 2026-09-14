# Loops `for`, `while` e `do`

`for` é conveniente quando inicialização, condição e atualização pertencem juntas. `while` repete enquanto a condição for diferente de zero, e `do ... while` testa depois do corpo, portanto executa pelo menos uma vez.

```c
for (size_t i = 0; i < count; ++i) {
    process(items[i]);
}

while (queue_has_items()) {
    consume_next();
}
```

`break` sai do loop ou switch mais interno e `continue` avança para a próxima iteração. Tenha cuidado com limites inteiros, especialmente misturando signed e unsigned. Ao percorrer arrays, faça o limite vir do tamanho real ou de um count explícito passado junto ao ponteiro.
