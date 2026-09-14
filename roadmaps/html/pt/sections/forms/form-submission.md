# Formulários, Names e Envio

`form` agrupa controles que podem enviar dados no formato nome/valor. `action` identifica o destino e `method` escolhe o método HTTP usado pelo envio normal. `get` normalmente coloca os dados na query string da URL; `post` os envia no corpo da requisição.

```html
<form action="/search" method="get">
  <label for="q">Search</label>
  <input id="q" name="q" type="search">
  <button type="submit">Search</button>
</form>
```

Um controle bem-sucedido precisa de `name` para contribuir dados. O `id` do input o conecta ao label visível, enquanto `name="q"` vira o nome do campo enviado. Formulários não exigem JavaScript para envio básico. Adicione scripts para melhorar validação, feedback ou comportamento da aplicação, mas mantenha validação no servidor porque a marcação do cliente pode ser contornada ou alterada.
