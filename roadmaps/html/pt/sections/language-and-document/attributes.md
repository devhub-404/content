# Atributos e Atributos Booleanos

Atributos adicionam informações ou configuração a um elemento e são escritos em sua tag de abertura. `href` fornece o destino de um link; `class` atribui nomes de classe reutilizáveis; `id` identifica um elemento; atributos de formulário como `required` afetam o comportamento do controle. Os nomes e valores permitidos dependem do elemento e da definição do atributo.

```html
<a href="/about" class="nav-link">About</a>
<button disabled>Save</button>
<input required>
```

Atributos booleanos funcionam pela presença: se `disabled` estiver presente, o botão está desabilitado; se `required` estiver presente, o campo é obrigatório. Escrever `disabled="false"` ainda significa desabilitado, pois o atributo está presente. Coloque valores comuns entre aspas de forma consistente, especialmente quando podem conter espaços ou pontuação.
