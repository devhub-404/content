# Queries de preferencias y capacidades de entrada

Media features pueden detectar preferencias como reduced motion, color scheme, contraste o forced colors, además de capacidades como hover y precisión del pointer. Es mejor consultar la capacidad real que inferirla por tamaño de pantalla.

```css
@media (prefers-reduced-motion: reduce) {
  .panel { transition: none; }
}

@media (prefers-color-scheme: dark) {
  :root { --surface: #161616; --text: #f5f5f5; }
}

@media (hover: hover) and (pointer: fine) {
  .menu-item:hover { text-decoration: underline; }
}
```

Un dispositivo grande puede ser táctil y uno pequeño puede tener puntero preciso. Trata estas queries como parte normal del producto. La experiencia base debe seguir funcionando cuando ninguna mejora coincide, y hover nunca debe ser el único camino para información esencial.
