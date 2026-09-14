# Carregando Scripts

Um script clássico sem atributos de carregamento pode interromper o parsing do HTML enquanto baixa e executa. `defer` permite que o parsing continue e executa scripts adiados depois que o documento foi analisado, preservando a ordem do documento. Em geral, é um bom padrão para scripts de aplicação colocados no `head`.

```html
<script src="/scripts/app.js" defer></script>
<script type="module" src="/scripts/main.js"></script>
```

Scripts de módulo usam `type="module"` e já são adiados por padrão. Eles suportam imports e exports do JavaScript. `async` serve para scripts independentes que podem executar assim que estiverem prontos; a ordem entre scripts async não é preservada. Escolha o modo de carregamento conforme as dependências do script, em vez de adicionar `async` ou `defer` mecanicamente.
