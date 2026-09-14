# Audio, vídeo, fuentes y pistas

`video` y `audio` incorporan medios temporales. `controls` proporciona controles nativos del navegador y es el punto de partida más seguro salvo que construyas una alternativa completa y accesible. Varios elementos `source` permiten al navegador escoger un formato reproducible, y `poster` ofrece una imagen previa al vídeo.

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

`track` añade texto sincronizado, como captions o subtítulos, normalmente en WebVTT. Los captions incluyen diálogo y sonidos relevantes; los subtítulos suelen traducir el diálogo. Una transcripción también mejora búsqueda y acceso sin audio. El autoplay con sonido suele bloquearse y, incluso cuando funciona, rara vez es una buena experiencia.
