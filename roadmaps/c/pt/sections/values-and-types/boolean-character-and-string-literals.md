# Booleanos, Caracteres e String Literals

C23 possui as keywords `bool`, `true` e `false` diretamente na linguagem. Character constants e string literals têm regras de encoding que dependem do prefixo e do character set da execução. Uma string literal comum é um array de caracteres seguido por byte zero terminador.

```c
bool ready = true;
char newline = '
';
const char *message = "hello";
```

Um ponteiro para string literal deve ser tratado como apontando para dados imutáveis; tentar modificar o literal é undefined behavior. `char` é um tipo inteiro pequeno e seu signedness é implementation-defined, então use `signed char`, `unsigned char` ou tipos fixed-width quando isso importar.
