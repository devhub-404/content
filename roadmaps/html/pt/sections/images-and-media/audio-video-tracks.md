# Áudio, Vídeo, Sources e Tracks

`video` e `audio` incorporam mídia temporal. `controls` nativos fornecem controles de reprodução do navegador e são o padrão mais seguro, a menos que você construa uma alternativa acessível completa. Vários elementos `source` permitem ao navegador escolher um formato reproduzível, e `poster` fornece uma imagem antes da reprodução do vídeo.

```html
<video controls poster="preview.jpg">
  <source src="lesson.webm" type="video/webm">
  <source src="lesson.mp4" type="video/mp4">
  <track
    kind="captions"
    src="lesson-en.vtt"
    srclang="en"
    label="English"
    default>
</video>

<audio controls src="interview.mp3"></audio>
```

`track` anexa texto sincronizado, como legendas descritivas ou traduções, normalmente usando WebVTT. Captions incluem fala e sons relevantes para pessoas que não ouvem a trilha; subtitles principalmente traduzem diálogo. Uma transcrição também é valiosa para busca e contextos sem áudio. Autoplay com som costuma ser bloqueado e geralmente oferece uma experiência ruim mesmo quando tecnicamente possível.
