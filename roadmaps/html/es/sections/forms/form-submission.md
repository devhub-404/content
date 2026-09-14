# Formularios, nombres y envío

`form` agrupa controles que pueden enviar pares nombre/valor. `action` identifica el destino y `method` el método HTTP usado por el envío nativo. `get` suele colocar datos en la query string; `post` los envía en el cuerpo de la petición.

```html
<form action="/search" method="get">
  <label for="q">Search</label>
  <input id="q" name="q" type="search">
  <button type="submit">Search</button>
</form>
```

Un control necesita `name` para aportar un valor al envío. El `id` conecta el input con su label visible, mientras `name` se convierte en la clave enviada. Los formularios no necesitan JavaScript para el envío básico. Añade scripts para mejorar feedback o interacción, pero valida siempre en el servidor porque el cliente puede modificarse o evitarse.
