# Qué es Astro

Astro es un framework web basado en rendering server-first y en enviar poco o ningún JavaScript al client por defecto. Los Astro components renderizan HTML en build o on demand, mientras components interactivos de frameworks pueden hidratarse selectivamente como islands en vez de convertir toda la página en una client app.

```astro
---
const title = "Hello Astro";
---
<html>
  <body>
    <h1>{title}</h1>
  </body>
</html>
```

Astro 7.3 es la línea actual en septiembre de 2026. Aprende el modelo HTML-first antes de añadir React, Vue u otro UI framework. La pregunta central no es “¿cómo hidrato todo?”, sino “¿qué partes realmente necesitan JavaScript en el browser?”.
