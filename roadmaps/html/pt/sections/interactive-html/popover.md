# Popovers

O atributo global `popover` cria conteúdo oculto até ser mostrado na top layer. `popovertarget` em um botão pode controlá-lo declarativamente. O modo padrão `auto` suporta fechamento leve e coordena com outros popovers automáticos; `manual` deixa abertura e fechamento sob controle explícito, enquanto comportamentos mais novos de hint atendem superfícies de dica transitórias.

```html
<button popovertarget="help">Help</button>

<div id="help" popover>
  <p>Your order number appears on the receipt.</p>
</div>
```

Popover é comportamento de exibição, não um papel semântico. Um popover pode conter ajuda, navegação, controles ou outra estrutura significativa, então escolha separadamente o elemento e a semântica do conteúdo. Como partes do conjunto de recursos de popover são mais novas que o núcleo do HTML, verifique o baseline de navegadores para o comportamento exato usado.
