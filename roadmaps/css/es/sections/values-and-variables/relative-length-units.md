# Unidades relativas a fuente, viewport y container

Las unidades relativas expresan una relación en vez de un tamaño fijo. `em` sigue una fuente local, `rem` la fuente raíz, `ch` y `lh` métricas tipográficas, y las unidades de viewport siguen dimensiones de la ventana. Las variantes `sv*`, `lv*` y `dv*` distinguen distintos estados del viewport.

```css
.prose { max-inline-size: 68ch; }
.button { padding: .65em 1em; }
.hero { min-block-size: 100svh; }

.card-shell { container-type: inline-size; }
.card h2 { font-size: clamp(1.2rem, 5cqi, 2rem); }
```

Las unidades de container como `cqi` y `cqb` dependen de un query container y son útiles para componentes reutilizables. Escoge la unidad según la relación que quieres modelar: tipografía, viewport o container, en vez de usar una unidad por costumbre.
