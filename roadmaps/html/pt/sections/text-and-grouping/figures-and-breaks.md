# Figuras, Legendas e Quebras Temáticas

`figure` agrupa conteúdo autocontido como imagem, gráfico, trecho de código, citação ou tabela quando esse item pode ser tratado como uma unidade. `figcaption` fornece sua legenda e pode aparecer no início ou no fim da figura. Nem toda imagem precisa de `figure`; use quando imagem e legenda formam uma unidade significativa.

```html
<figure>
  <img src="sales-chart.png" alt="Sales rise from January through June.">
  <figcaption>Monthly sales, January–June.</figcaption>
</figure>

<hr>
```

`hr` representa uma quebra temática no conteúdo, como mudança de cena ou transição de assunto. Sua aparência comum como linha horizontal é apenas a estilização padrão. Se você precisa apenas de uma borda decorativa entre caixas, CSS é uma ferramenta melhor do que adicionar um `hr` sem significado temático.
