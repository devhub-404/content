# Pseudo-clases estructurales

Pseudo-clases como `:first-child`, `:last-child`, `:only-child` y la familia `:nth-*()` seleccionan elementos según su posición entre hermanos. `:nth-child()` admite fórmulas como `odd`, `2n` o `3n + 1`, y puede contar solo hermanos que coincidan con un selector mediante `of`.

```css
li:first-child { margin-block-start: 0; }
tr:nth-child(even) { background: rgb(0 0 0 / .04); }
.card:nth-child(-n + 3 of .featured) { border-width: 2px; }
```

Úsalas cuando la posición sea parte real de la presentación, como filas alternas o espaciado entre elementos. No conviertas la posición en estado de negocio: si algo es «featured» independientemente de dónde aparece, expresa ese estado en el markup o en una clase.
