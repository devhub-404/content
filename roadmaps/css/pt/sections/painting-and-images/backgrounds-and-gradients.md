# Camadas de Background e Gradientes

Um background pode conter uma cor e várias camadas de imagem. Cada camada pode ter posição, tamanho, repetição, origem e clipping independentes. A primeira imagem listada é pintada mais perto do observador; a cor de fundo fica atrás de todas as camadas.

```css
.hero {
  background:
    linear-gradient(rgb(0 0 0 / .55), rgb(0 0 0 / .15)),
    url("/images/hero.jpg") center / cover no-repeat;
  color: white;
}
```

Gradientes lineares, radiais e cônicos são imagens geradas, então podem ser usados onde um valor de imagem é aceito e combinados com imagens normais. `cover` preenche a área e pode cortar a fonte; `contain` mantém a imagem inteira visível e pode deixar espaço. Background images são decorativas: imagens de conteúdo que precisam de alt pertencem ao HTML.
