# Familias tipográficas y web fonts

`font-family` es una lista ordenada de fallbacks. Termina normalmente con una familia genérica como `sans-serif`, `serif` o `monospace`. Diferentes scripts pueden usar fallbacks distintos incluso en la misma línea, y las métricas tipográficas afectan layout además de apariencia.

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

`@font-face` relaciona una familia, estilo y peso con archivos descargables. Declara los rangos reales de peso/estilo para que el navegador elija la cara adecuada. `font-display` controla la experiencia de carga. Las web fonts son recursos de red: el fallback debe seguir siendo usable.
