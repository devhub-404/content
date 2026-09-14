# URLs e History

A classe `URL` faz parse e constrói URLs sem concatenação manual, e `URLSearchParams` lê e atualiza query parameters aplicando regras de encoding. URLs relativas podem ser resolvidas contra uma base.

```js
const url = new URL(location.href);
url.searchParams.set("page", "2");

history.pushState({ page: 2 }, "", url);

addEventListener("popstate", event => {
  console.log(event.state);
});
```

History API adiciona ou substitui entries do mesmo documento com `pushState()` e `replaceState()`, enquanto `popstate` relata navegação entre essas entries. Alterar history não renderiza estado da aplicação automaticamente. Mantenha URLs significativas e links normais quando possível para que reload, compartilhamento, navegação do navegador e acessibilidade continuem robustos.
