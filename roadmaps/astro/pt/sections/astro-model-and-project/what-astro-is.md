# O que é Astro

Astro é um framework web baseado em rendering server-first e em enviar pouco ou nenhum JavaScript ao client por default. Astro components renderizam HTML no build ou on demand, enquanto components interativos de frameworks podem ser hidratados seletivamente como islands em vez de transformar a página inteira em client app.

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

Astro 7.3 é a linha atual em setembro de 2026. Aprenda o modelo HTML-first antes de adicionar React, Vue ou outro UI framework. A pergunta central não é “como hidrato tudo?”, mas “quais partes realmente precisam de JavaScript no browser?”.
