# Folhas de Estilo, Ícones e Links de Recursos

O elemento `link` descreve uma relação entre o documento atual e outro recurso. `rel="stylesheet"` carrega CSS, enquanto `rel="icon"` fornece um ícone para a interface do navegador ou do site instalado. `link` normalmente fica em `head` porque descreve o documento, não conteúdo visível do corpo.

```html
<link rel="stylesheet" href="/styles/site.css">
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="preload" href="/fonts/ui.woff2" as="font" type="font/woff2" crossorigin>
```

Dicas de recurso como `preload` podem informar ao navegador que um recurso importante será necessário em breve. Elas são ferramentas de desempenho, não boilerplate. Preloads incorretos ou excessivos podem competir com recursos que o navegador priorizaria bem sozinho. Adicione essas dicas apenas quando o carregamento antecipado tiver benefício medido.
