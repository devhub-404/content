# Tamaño de fuente, line height y variable fonts

La tipografía legible depende de tamaño, line height y longitud de línea. `line-height` sin unidad escala con el tamaño de fuente del propio elemento y suele ser robusto para texto heredado. Los headings pueden usar líneas más compactas porque son mayores y más cortos.

```css
body {
  font-size: 1rem;
  line-height: 1.6;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
  line-height: 1.1;
  font-weight: 650;
  font-optical-sizing: auto;
}
```

Las variable fonts pueden exponer ejes como peso, anchura, inclinación u optical size. Prefiere propiedades de alto nivel como `font-weight` cuando mapean al eje que necesitas y usa `font-variation-settings` para ejes especiales. El archivo debe soportar realmente el eje solicitado.
