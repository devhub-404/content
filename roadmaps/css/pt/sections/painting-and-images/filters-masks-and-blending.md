# Filters, Clipping, Masking e Blending

`filter` processa a saída renderizada do elemento; `backdrop-filter` processa pixels atrás de um elemento translúcido. Blend modes mudam como camadas sobrepostas se combinam. `clip-path` cria uma região visível rígida, enquanto masks podem criar transparência parcial e bordas suaves usando alpha ou luminância.

```css
.photo { filter: saturate(.9) contrast(1.05); }
.avatar { clip-path: circle(45%); }

.fade-edge {
  mask-image:
    linear-gradient(to right, transparent, black 15%, black 85%, transparent);
}
```

Esses efeitos mudam pintura e composição, não a geometria do fluxo normal. Um clip circular não faz o conteúdo ao redor organizar-se em círculo. Blurs, filters e masks animadas complexas podem ser caros, especialmente em superfícies grandes. Não dependa de blending ou translucidez para contraste essencial de texto porque o background pode mudar o resultado.
