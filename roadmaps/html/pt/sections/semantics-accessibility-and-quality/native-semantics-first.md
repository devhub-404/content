# HTML Nativo Primeiro

Elementos nativos já fornecem semântica e frequentemente comportamento. Um button recebe foco, pode ser ativado pelo teclado, pode ser desabilitado e é exposto como botão a tecnologias assistivas. Um link com `href` participa da navegação e do comportamento de links do navegador. Começar com `div` genérico significa reconstruir contratos que a plataforma já oferece.

```html
<button type="button">Save changes</button>

<a href="/account">Open account</a>
```

ARIA pode complementar HTML quando a semântica nativa não expressa um estado ou relação necessária, mas não adiciona automaticamente comportamento de teclado. Prefira o elemento nativo cujo contrato embutido corresponde à tarefa. Use button para ação, link para navegação, heading para título e controle de formulário real para entrada do usuário.
