# `div`, `span` e Agrupamento Genérico

`div` e `span` são contêineres genéricos sem significado especial de conteúdo. `div` é usado para agrupar conteúdo de fluxo; `span` é usado dentro de conteúdo textual. Eles são úteis quando você precisa de um gancho para CSS ou JavaScript e nenhum elemento semântico mais específico descreve a relação.

```html
<div class="price">
  <span class="amount">$29</span>
  <span class="currency">USD</span>
</div>
```

Contêineres genéricos não são HTML ruim; contêineres genéricos desnecessários são. Antes de adicionar um `div`, pergunte se o conteúdo é realmente uma seção, artigo, região de navegação, lista, figura, formulário ou outra estrutura nativa. Use o elemento semântico quando ele se encaixa e use `div` ou `span` honestamente quando o agrupamento for apenas técnico ou visual.
