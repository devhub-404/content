# Citações e Texto Pré-formatado

`blockquote` representa uma citação que forma seu próprio bloco; `q` serve para citações curtas dentro de uma linha. Se o leitor precisa conhecer a fonte, forneça essa informação de forma visível em vez de depender apenas de metadados. Uma citação pode ser vinculada ou nomeada no conteúdo próximo.

```html
<blockquote>
  <p>The simplest solution was the most reliable.</p>
</blockquote>

<pre><code>function add(a, b) {
  return a + b;
}</code></pre>
```

`pre` preserva espaços e quebras de linha do código-fonte, sendo útil para código, diagramas ASCII e outros materiais pré-formatados. Blocos de código normalmente combinam `pre` com `code`: `pre` preserva o layout enquanto `code` fornece a semântica de código. Como a indentação dentro de `pre` fica visível, formate sua origem de propósito.
