# Inputs numéricos, de fecha, rango, color y archivo

HTML incluye tipos de input especializados. `number` puede expresar `min`, `max` y `step`; `range` ofrece un slider para valores aproximados; los tipos de fecha y hora pueden mostrar pickers de la plataforma; `color` puede mostrar un selector; y `file` permite escoger archivos locales.

```html
<input type="number" name="qty" min="1" max="10" step="1">
<input type="range" name="volume" min="0" max="100">
<input type="date" name="start">
<input type="color" name="accent">
<input type="file" name="receipt" accept="image/*,.pdf">
```

La interfaz concreta varía entre navegador y sistema, por lo que debes elegir el tipo por la semántica del dato y no por una apariencia exacta. `accept` en un file input es solo una pista de selección, no validación de seguridad. Tipo, tamaño y contenido del archivo deben comprobarse en el servidor.
