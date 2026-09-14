# Tipos de input textuales

El elemento `input` cambia de comportamiento según su `type`. Entre los tipos textuales comunes están `text`, `email`, `password`, `search`, `url` y `tel`. Los tipos especializados pueden ofrecer validación básica y teclados o interfaces más adecuadas al dato en dispositivos móviles.

```html
<input type="text" name="name">
<input type="email" name="email">
<input type="password" name="password">
<input type="search" name="q">
<input type="url" name="website">
<input type="tel" name="phone">
```

Elige el tipo que corresponde al dato, pero no confundas validación del navegador con validación de negocio. `email` puede comprobar una sintaxis básica, no si la cuenta existe. `tel` no impone un formato universal porque los números cambian según el país. La validación del servidor sigue siendo la autoridad.
