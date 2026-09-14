# Nomes Acessíveis

Controles interativos e conteúdo incorporado precisam de nomes que informem ao usuário o que são. Elementos diferentes obtêm nomes por mecanismos nativos diferentes: controles de formulário por labels, imagens por `alt`, botões pelo próprio texto e iframes por `title`. Texto visível costuma ser o melhor ponto de partida porque ajuda todos os usuários.

```html
<label for="search">Search products</label>
<input id="search" name="q" type="search">

<img src="warning.svg" alt="Warning: high voltage">

<iframe src="/chart" title="Quarterly revenue chart"></iframe>
```

Não adicione `aria-label` automaticamente quando conteúdo visível nativo já fornece o nome correto. O cálculo de nome acessível possui regras específicas de precedência, e um rótulo ARIA pode substituir o texto visível na árvore de acessibilidade. Use nomeação ARIA quando os mecanismos nativos forem insuficientes e teste o resultado com ferramentas de acessibilidade.
