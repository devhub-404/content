# Quebra de Linha e Ordem Visual

`flex-wrap: wrap` permite formar linhas flex adicionais quando uma linha não cabe. Cada linha é organizada de forma independente, então itens quebrados não criam colunas compartilhadas entre linhas. Se linhas e colunas alinhadas importam juntas, Grid costuma ser o modelo mais forte.

```css
.chips {
  display: flex;
  flex-wrap: wrap;
  gap: .5rem;
}

.featured {
  order: -1;
}
```

`order`, `row-reverse` e `column-reverse` podem mudar a ordem visual sem normalmente mudar a ordem de leitura do DOM ou foco pelo teclado. Use apenas quando a sequência semântica continuar fazendo sentido. Se conteúdo importante precisa aparecer primeiro, corrija a ordem no código em vez de fazer o CSS contar uma história visual e outra para teclado ou tecnologia assistiva.
