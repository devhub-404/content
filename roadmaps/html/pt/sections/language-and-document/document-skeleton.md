# A Estrutura Básica do Documento HTML

Um documento HTML normal começa com o doctype do HTML, possui um único elemento raiz `html`, um `head` para metadados do documento e um `body` para o conteúdo apresentado ao usuário. O doctype mantém o navegador no modo de padrões; ele não é um elemento HTML.

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My page</title>
  </head>
  <body>
    <h1>Hello</h1>
  </body>
</html>
```

`lang` declara o idioma principal do documento. Dentro de `head`, UTF-8 é a codificação de caracteres padrão, a declaração de viewport permite o comportamento responsivo esperado em navegadores móveis e `title` nomeia o documento na interface do navegador, como abas e favoritos. O conteúdo visível da página pertence ao `body`. Essa estrutura é um ponto de partida confiável para páginas comuns.
