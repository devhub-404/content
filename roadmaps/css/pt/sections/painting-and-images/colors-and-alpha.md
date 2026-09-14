# Cores, Alpha e `currentColor`

CSS suporta cores nomeadas, hex, `rgb()`, `hsl()`, `hwb()`, Lab/LCH, OKLab/OKLCH e espaços `color()`. Alpha é transparência de um valor de cor específico; a propriedade `opacity` compõe a subárvore renderizada inteira com opacidade reduzida.

```css
.button {
  color: oklch(52% .2 255);
  border: 1px solid currentColor;
  background: rgb(255 255 255 / .9);
}
```

`currentColor` resolve para o `color` computado do elemento, sendo útil para bordas, ícones, fills SVG e decorações que devem acompanhar a cor do texto. Espaços perceptuais como OKLCH ajudam em ajustes sistemáticos de lightness e chroma. Valores wide-gamut podem mostrar cores fora de sRGB em telas capazes, então forneça fallback aceitável quando essa diferença importa.
