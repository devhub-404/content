# Diálogos

`dialog` representa uma caixa de diálogo. JavaScript pode mostrá-la de forma não modal com `show()` ou modal com `showModal()`, e comandos declarativos modernos podem controlar diálogos sem um handler de clique personalizado. Um diálogo modal participa da top layer e o navegador cuida de comportamentos importantes de foco e inércia do fundo.

```html
<dialog id="confirm-delete">
  <p>Delete this file?</p>
  <form method="dialog">
    <button value="cancel">Cancel</button>
    <button value="delete">Delete</button>
  </form>
</dialog>
```

Um formulário dentro do diálogo pode usar `method="dialog"` para que o envio feche o diálogo em vez de fazer uma requisição; o botão de submit acionado pode fornecer um valor de retorno. Use o elemento nativo em vez de um `div` genérico quando a interface for realmente um diálogo, porque reproduzir foco, fechamento por Escape, modalidade e acessibilidade corretamente é sutil.
