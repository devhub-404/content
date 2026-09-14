# Ênfase e Importância

`em` marca ênfase de entonação: mudar a palavra enfatizada pode mudar a nuance da frase. `strong` marca forte importância, seriedade ou urgência. Navegadores geralmente exibem `em` em itálico e `strong` em negrito, mas esses padrões visuais não são o significado dos elementos.

```html
<p>You <em>must</em> stir continuously.</p>
<p><strong>Warning:</strong> the surface is hot.</p>
```

Se um texto é apenas visualmente diferente, não invente semântica de ênfase só para obter itálico ou negrito. Use o elemento que corresponde ao significado do conteúdo e depois estilize com CSS. Essa distinção importa porque tecnologias assistivas e outros softwares podem usar a semântica mesmo quando a apresentação visual muda por completo.
