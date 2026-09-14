# Selectores de atributos y estados

Los selectores de atributo pueden comprobar presencia, valor exacto, tokens, prefijos, sufijos o subcadenas. Las pseudo-clases como `:hover`, `:focus-visible`, `:checked`, `:disabled`, `:required` y `:valid` representan estados que el navegador ya conoce.

```css
input[required] { border-inline-start-width: 3px; }
input[type="email"] { inline-size: 24rem; }
a[href^="https:"] { text-decoration-style: dotted; }

button:hover { filter: brightness(1.05); }
button:focus-visible { outline: 3px solid currentColor; }
input:checked + label { font-weight: 700; }
```

No dependas de `:hover` para funciones esenciales porque no todos los dispositivos tienen hover. Conserva un indicador claro de foco de teclado y aprovecha los estados nativos de los controles antes de duplicarlos con clases de aplicación.
