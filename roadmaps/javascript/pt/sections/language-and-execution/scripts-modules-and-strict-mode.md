# Scripts, Módulos e Strict Mode

JavaScript no navegador pode rodar como script clássico ou módulo ECMAScript. Módulos possuem escopo de topo próprio, suportam `import` e `export`, permitem `await` no topo e são strict por padrão. Scripts clássicos possuem comportamento global e de carregamento mais antigo e podem ativar strict mode com `"use strict"`.

```html
<script src="/legacy.js" defer></script>
<script type="module" src="/app.js"></script>
```

Código moderno de aplicação normalmente se beneficia de módulos porque dependências ficam explícitas e nomes permanecem locais até serem exportados. Strict mode remove vários comportamentos legados propensos a erro e transforma alguns erros silenciosos em exceções. A resolução de módulos é definida pelo host: navegadores resolvem principalmente URLs, enquanto runtimes de servidor e ferramentas podem adicionar regras de pacotes.
