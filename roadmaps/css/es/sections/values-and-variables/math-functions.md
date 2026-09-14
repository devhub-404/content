# Funciones matemáticas de CSS

`calc()` combina expresiones numéricas compatibles, incluso con unidades diferentes. `min()` elige el menor valor, `max()` el mayor y `clamp(min, preferido, max)` mantiene un valor fluido dentro de límites. Estas funciones permiten expresar restricciones sin llenar la hoja de breakpoints.

```css
main {
  inline-size: min(70rem, calc(100% - 2rem));
  margin-inline: auto;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

El sizing fluido funciona cuando la relación es continua, como tipografía o espaciado. No sustituye una decisión discreta de layout. Si una sidebar debe pasar debajo del contenido, usa una media o container query en lugar de intentar resolver todo con una fórmula enorme.
