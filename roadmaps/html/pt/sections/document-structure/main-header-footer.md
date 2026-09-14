# `main`, `header` e `footer`

`main` identifica o conteúdo dominante do corpo do documento. Uma página normalmente possui uma região principal ativa; navegação repetida do site, branding e conteúdo de rodapé não pertencem a ela, a menos que sejam realmente o objetivo principal da página. Isso cria um landmark útil para navegação.

```html
<body>
  <header>Site header...</header>
  <main>
    <h1>Account settings</h1>
    ...
  </main>
  <footer>Site footer...</footer>
</body>
```

`header` e `footer` são relativos à seção a que pertencem. Uma página pode ter cabeçalho e rodapé do site, enquanto um `article` também pode ter seus próprios header e footer para título/autoria e informações de autor/atualização. O significado é contextual, não simplesmente “a caixa no topo” e “a caixa no fim”.
