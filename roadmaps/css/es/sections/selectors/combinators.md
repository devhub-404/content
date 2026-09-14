# Combinadores

Los combinadores expresan relaciones estructurales. Un espacio significa descendiente, `>` hijo directo, `+` hermano inmediatamente siguiente y `~` hermanos posteriores con el mismo padre. Permiten aprovechar la estructura que ya existe en el documento.

```css
article p { color: #333; }
article > p { max-inline-size: 68ch; }
h2 + p { margin-block-start: 0; }
h2 ~ p { color: #444; }
```

Usa la relación más débil que exprese realmente la dependencia. `article > p` selecciona solo párrafos directos, mientras `article p` también alcanza los anidados. Evita selectores que codifiquen una ruta accidental muy larga: un pequeño cambio de markup puede romperlos sin que cambie el significado del componente.
