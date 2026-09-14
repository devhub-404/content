# Arquivos e Streams

A biblioteca padrão modela arquivos e outros byte streams com `FILE *`. Abrir escolhe um modo, reads/writes avançam estado e `fclose` libera o stream. Modos text e binary podem diferir entre plataformas, então escolha conforme os dados.

```c
FILE *file = fopen("data.txt", "r");
if (!file) {
    perror("fopen");
    return -1;
}

char line[256];
while (fgets(line, sizeof line, file)) {
    fputs(line, stdout);
}

fclose(file);
```

Cheque operações que podem falhar e diferencie EOF de erro quando necessário. Buffering significa que write bem-sucedido pode ainda não ter chegado ao dispositivo; `fflush` e fechamento importam em fronteiras de transação ou processo.
