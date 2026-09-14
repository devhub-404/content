# Whitespace, wrapping e hyphenation

`white-space` controla cómo se colapsan espacios y saltos y si el texto puede hacer wrap. `overflow-wrap` permite partir contenido que de otro modo desbordaría; `word-break` cambia las reglas de ruptura de forma más agresiva; `hyphens` puede habilitar hifenación dependiente del idioma.

```css
.prose {
  max-inline-size: 68ch;
  hyphens: auto;
}

.long-token {
  overflow-wrap: anywhere;
}

pre {
  white-space: pre-wrap;
}
```

Usa la herramienta menos agresiva que mantenga el contenido dentro de su espacio. Una URL larga puede necesitar `overflow-wrap: anywhere`, mientras la prosa normal no debería romperse en cualquier letra. El `lang` correcto en HTML ayuda a las reglas de hifenación y separación.
