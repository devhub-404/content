# Imagens e Texto Alternativo

`img` incorpora uma imagem que faz parte do conteúdo do documento. `src` identifica o recurso e `alt` fornece uma alternativa textual. O texto alternativo correto depende da função da imagem no contexto: descreva a informação que o leitor precisa, não apenas que “existe uma imagem”.

```html
<img
  src="mountain.jpg"
  alt="Snow-covered mountain above a pine forest"
  width="1200"
  height="800">
```

Imagens decorativas que não acrescentam informação normalmente devem usar `alt=""` para que tecnologias assistivas possam ignorá-las. Não omita `alt` de imagens comuns de conteúdo. Informar `width` e `height` intrínsecos permite ao navegador calcular a proporção antes do carregamento, ajudando a reservar espaço e reduzir layout shift. CSS ainda pode renderizar a imagem responsivamente em outro tamanho.
