# Color schemes y forced colors

`color-scheme` informa al navegador de los esquemas claro/oscuro que la página puede representar, permitiendo adaptar controles nativos y system colors. En forced-colors el navegador puede sustituir colores del autor para satisfacer necesidades de contraste.

```css
:root {
  color-scheme: light dark;
}

.alert {
  border: 2px solid currentColor;
}

@media (forced-colors: active) {
  .alert {
    forced-color-adjust: auto;
  }
}
```

No expreses estado solo mediante el matiz. Texto, bordes, iconos o formas deben conservar el significado si los colores son remapeados. `forced-color-adjust` puede excluir casos muy concretos, pero usarlo ampliamente derrota una preferencia de accesibilidad. Prueba dark mode, forced colors y contraste aumentado.
