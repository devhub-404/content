# Filtros, clipping, masking y blending

`filter` procesa la salida renderizada de un elemento; `backdrop-filter` procesa lo que queda detrás. Blend modes cambian cómo se combinan capas. `clip-path` crea una región visible rígida y las masks permiten transparencias parciales y bordes suaves.

```css
.photo { filter: saturate(.9) contrast(1.05); }
.avatar { clip-path: circle(45%); }

.fade-edge {
  mask-image:
    linear-gradient(to right, transparent, black 15%, black 85%, transparent);
}
```

Estos efectos cambian pintura y composición, no la geometría del flujo normal. Un clip circular no hace que otros elementos se distribuyan alrededor de un círculo. Filtros y blurs grandes pueden ser costosos, y el contraste esencial no debería depender de translucidez o blending impredecible.
