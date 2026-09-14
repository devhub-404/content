# Listas

HTML possui três estruturas principais de lista. `ul` é uma lista não ordenada quando a sequência não importa. `ol` é uma lista ordenada quando a ordem ou numeração importa. Ambas contêm itens `li`. Listas podem ser aninhadas quando o conteúdo é genuinamente hierárquico.

```html
<ul>
  <li>Tea</li>
  <li>Coffee</li>
</ul>

<ol>
  <li>Open the package.</li>
  <li>Add water.</li>
</ol>

<dl>
  <dt>HTML</dt>
  <dd>Structures web content.</dd>
</dl>
```

Uma lista de descrição usa `dl`, `dt` e `dd` para grupos de nome e descrição. Ela funciona para glossários, metadados, termos com definições e relações semelhantes. Não escolha uma lista apenas para obter marcadores ou números do navegador. Use marcação de lista quando o conteúdo realmente for uma lista e deixe o CSS controlar marcadores e layout.
