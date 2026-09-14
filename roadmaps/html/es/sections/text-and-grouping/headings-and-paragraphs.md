# Encabezados y párrafos

HTML ofrece seis niveles de encabezado: `h1`, `h2`, `h3`, `h4`, `h5` y `h6`. `h1` es el nivel más alto y `h6` el más bajo. Los niveles expresan jerarquía, no un tamaño de fuente preferido. Una página suele tener un `h1` principal claro y niveles inferiores a medida que el contenido se anida.

```html
<h1>Gardening guide</h1>
<p>This guide covers vegetables and herbs.</p>

<h2>Vegetables</h2>
<h3>Tomatoes</h3>
<h4>Feeding tomatoes</h4>

<h2>Herbs</h2>
<h3>Basil</h3>
```

`p` representa un párrafo de prosa. Usa encabezados para nombrar secciones y párrafos para bloques normales de texto. Mantén una jerarquía lógica: un `h3` suele depender de un `h2` y un `h4` de un `h3`. CSS puede hacer cualquier encabezado grande o pequeño, así que no elijas `h4` solo porque su estilo por defecto parece adecuado.
