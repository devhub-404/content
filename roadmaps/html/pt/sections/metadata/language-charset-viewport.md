# Idioma, Charset e Viewport

Três declarações pertencem ao início da maioria dos documentos. `lang` identifica o idioma principal do documento, ajudando pronúncia, tradução, correção ortográfica e processamento sensível ao idioma. `meta charset="utf-8"` informa ao navegador como os bytes correspondem a caracteres Unicode.

```html
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
</html>
```

A declaração de viewport faz o viewport de layout CSS acompanhar a largura do dispositivo em navegadores móveis e estabelece uma escala inicial normal. Evite configurações que impeçam zoom, pois usuários podem depender dele para leitura. Se uma parte da página mudar de idioma, adicione um `lang` mais específico naquele elemento em vez de alterar o documento inteiro.
