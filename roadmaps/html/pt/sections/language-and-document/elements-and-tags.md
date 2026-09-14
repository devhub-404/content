# Elementos, Tags e Elementos Vazios

A maioria dos elementos HTML possui uma tag de abertura, conteúdo e uma tag de fechamento. Em `<p>This is a paragraph.</p>`, a construção completa é o elemento `p`, enquanto `<p>` e `</p>` são suas tags. Elementos podem conter texto e outros elementos quando seu modelo de conteúdo permite.

```html
<p>This is a paragraph.</p>
<img src="photo.jpg" alt="A mountain at sunrise">
<br>
```

Alguns elementos são vazios e não podem conter conteúdo nem possuir tag de fechamento. Exemplos comuns incluem `img`, `input`, `meta`, `link`, `br`, `hr`, `source` e `track`. Escrever `<img></img>` não transforma uma imagem em contêiner. Aprenda as regras de conteúdo de cada elemento em vez de presumir que toda tag vem em par.
