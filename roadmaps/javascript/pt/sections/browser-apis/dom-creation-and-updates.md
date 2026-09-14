# Criando e Atualizando Conteúdo DOM

Métodos DOM podem criar, inserir, mover, substituir e remover nodes. `createElement()` cria elemento HTML em documento HTML; `textContent` define texto sem parse como markup; `append`, `prepend`, `before`, `after`, `replaceWith` e `remove` cobrem updates comuns da árvore.

```js
const item = document.createElement("li");
item.className = "todo";
item.textContent = userInput;

list.append(item);
```

Use APIs de texto para texto não confiável. `innerHTML` intencionalmente faz parse de markup e só é apropriado quando a aplicação controla ou sanitiza com segurança a string HTML. Inserir strings não confiáveis como HTML pode criar XSS. Prefira construir nodes estruturados ou usar estratégia confiável de sanitização em vez de escapar markup manualmente.
