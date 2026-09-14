# `nav` e `search`

`nav` identifica uma região de navegação significativa, como menu principal, índice ou paginação. Nem todo grupo de links precisa ser navegação. Quando a página possui mais de um landmark de navegação, dê rótulos acessíveis distintos para que o usuário consiga diferenciá-los.

```html
<nav aria-label="Primary">
  <a href="/">Home</a>
  <a href="/products">Products</a>
</nav>

<search>
  <form action="/search">
    <label for="q">Search products</label>
    <input id="q" name="q" type="search">
  </form>
</search>
```

`search` identifica uma região cuja finalidade é pesquisar ou filtrar. Ela pode conter um formulário e controles relacionados. O formulário ainda cuida do envio de dados; `search` descreve o propósito maior da região. Use landmarks semânticos porque ajudam pessoas e softwares a ir diretamente às principais áreas da página.
