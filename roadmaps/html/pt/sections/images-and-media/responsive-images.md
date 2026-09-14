# Imagens Responsivas com `srcset`, `sizes` e `picture`

Imagens responsivas resolvem dois problemas diferentes. `srcset` com descritores de largura e `sizes` permite ao navegador escolher uma resolução eficiente para o mesmo conteúdo visual. O navegador combina larguras candidatas, tamanho esperado do espaço renderizado, densidade de pixels e outros fatores para escolher o recurso.

```html
<img
  src="photo-800.jpg"
  srcset="photo-480.jpg 480w,
          photo-800.jpg 800w,
          photo-1200.jpg 1200w"
  sizes="(width <= 600px) 100vw, 800px"
  alt="A cyclist crossing a stone bridge">

<picture>
  <source media="(width < 600px)" srcset="portrait-crop.jpg">
  <img src="wide-photo.jpg" alt="Chef preparing bread at a work table">
</picture>
```

`picture` é útil para direção de arte ou troca de formato. Direção de arte significa que outro corte ou composição comunica melhor em um layout diferente. Troca de formato oferece alternativas como AVIF ou WebP com um `img` de fallback. Em ambos os casos, `img` continua sendo o elemento real da imagem e é responsável pelo texto alternativo.
