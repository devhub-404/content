# Formulários e `FormData`

Formulários HTML já fornecem submission, labels, controles e constraint validation. JavaScript pode ouvir `submit`, inspecionar controles, chamar `checkValidity()` ou `reportValidity()` e criar `FormData` a partir de controles nomeados bem-sucedidos. Ouvir o form preserva teclado e outros caminhos nativos de submission.

```js
form.addEventListener("submit", event => {
  if (!form.checkValidity()) {
    event.preventDefault();
    form.reportValidity();
    return;
  }

  const data = new FormData(form);
  console.log(data.get("email"));
});
```

Validação no cliente é feedback para o usuário, não barreira de segurança; o servidor precisa validar os dados novamente. `FormData` também pode ser enviado diretamente por Fetch para dados multipart. Preserve semântica nativa de formulário e faça progressive enhancement em vez de substituir controles funcionais por widgets feitos com div.
