# Validação e Autocomplete

HTML pode expressar restrições comuns de validação com atributos como `required`, `minlength`, `maxlength`, `min`, `max`, `step` e `pattern`. O navegador pode impedir um envio normal quando um controle viola essas regras e expor estados de validade para CSS e JavaScript.

```html
<input
  name="username"
  required
  minlength="3"
  maxlength="20"
  pattern="[A-Za-z0-9_]+"
  autocomplete="username">
```

`autocomplete` informa ao navegador que tipo de dado real um campo representa, usando tokens como `name`, `email`, `username`, `current-password`, `street-address` e `postal-code`. Um autocomplete correto reduz digitação e ajuda gerenciadores de senha. Restrições no cliente melhoram a interação, mas não são uma barreira de segurança; sempre valide os valores no servidor.
