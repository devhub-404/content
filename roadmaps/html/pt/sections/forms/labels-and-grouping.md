# Labels, Fieldsets e Legends

Todo controle de formulário precisa de um nome acessível. Um `label` conectado por `for` e `id` correspondentes é o padrão comum, e envolver o controle dentro de um label também é válido. Labels visíveis continuam disponíveis enquanto o usuário digita; placeholder não os substitui.

```html
<label for="email">Email address</label>
<input id="email" name="email" type="email">

<fieldset>
  <legend>Delivery speed</legend>
  <label><input type="radio" name="speed" value="standard"> Standard</label>
  <label><input type="radio" name="speed" value="express"> Express</label>
</fieldset>
```

`fieldset` agrupa controles relacionados e `legend` nomeia o grupo. Isso é especialmente valioso para radio buttons e checkboxes relacionados, porque cada opção precisa do contexto da pergunta do grupo. Use relações nativas do formulário antes de recorrer a ARIA; os navegadores já expõem essas relações de forma consistente.
