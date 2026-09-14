# `textarea` e Botões

`textarea` coleta texto em várias linhas. Seu valor inicial fica entre as tags de abertura e fechamento, não em um atributo `value`. `rows` e `cols` fornecem uma dica inicial de tamanho, enquanto CSS normalmente controla o layout final. Lembre que espaços literais entre as tags podem virar parte do valor inicial.

```html
<label for="message">Message</label>
<textarea id="message" name="message" rows="6"></textarea>

<button type="submit">Send</button>
<button type="button">Preview</button>
```

Um `button` dentro de formulário assume comportamento de submit por padrão, então especifique `type` quando houver ambiguidade. Use `submit` para enviar, `button` para ações controladas por script e `reset` apenas quando restaurar todos os valores iniciais realmente ajudar. Fora de formulários, button continua sendo o elemento nativo correto para ações como abrir menu ou diálogo.
