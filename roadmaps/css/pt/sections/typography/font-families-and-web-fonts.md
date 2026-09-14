# Famílias de Fonte e Web Fonts

`font-family` é uma lista ordenada de fallbacks. Termine stacks de autor com família genérica adequada como `sans-serif`, `serif` ou `monospace`; scripts diferentes podem cair em fontes diferentes na mesma linha. Métricas da fonte afetam quebras de linha e layout, não apenas aparência.

```css
body {
  font-family: Inter, system-ui, sans-serif;
}

@font-face {
  font-family: "Brand Sans";
  src: url("/fonts/brand-sans.woff2") format("woff2");
  font-weight: 100 900;
  font-style: normal;
  font-display: swap;
}
```

`@font-face` mapeia uma descrição de família/estilo/peso para dados de fonte baixáveis. Declare ranges reais de peso e estilo para o navegador escolher a face correta em vez de sintetizar. `font-display` controla o carregamento; `swap` favorece texto fallback imediato seguido da web font. Web fonts são dependências de rede, então mantenha a experiência fallback utilizável.
