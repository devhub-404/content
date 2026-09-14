# Listas

HTML tiene tres estructuras principales de lista. `ul` es una lista no ordenada cuando la secuencia no importa; `ol` es una lista ordenada cuando el orden o la numeración sí importa. Ambas contienen elementos `li`. Las listas pueden anidarse cuando el contenido es realmente jerárquico.

```html
<ul>
  <li>Tea</li>
  <li>Coffee</li>
</ul>

<ol>
  <li>Open the package.</li>
  <li>Add water.</li>
</ol>

<dl>
  <dt>HTML</dt>
  <dd>Structures web content.</dd>
</dl>
```

Una lista de descripción usa `dl`, `dt` y `dd` para grupos de nombre y descripción. Sirve para glosarios, metadatos, términos con definiciones y relaciones similares. No uses una lista solo para obtener viñetas o números del navegador. Usa marcado de lista cuando el contenido sea una lista y deja que CSS controle los marcadores y el layout.
