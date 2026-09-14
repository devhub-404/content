# Seletores de Atributo e Estado

Seletores de atributo podem testar existência, valor exato, participação em tokens, prefixos, sufixos e substrings. São úteis quando o estado já está representado no HTML. Pseudo-classes como `:hover`, `:focus`, `:focus-visible`, `:checked`, `:disabled`, `:required` e `:valid` correspondem a estados conhecidos pelo navegador sem classes extras.

```css
input[required] { border-inline-start-width: 3px; }
input[type="email"] { inline-size: 24rem; }
a[href^="https:"] { text-decoration-style: dotted; }

button:hover { filter: brightness(1.05); }
button:focus-visible { outline: 3px solid currentColor; }
input:checked + label { font-weight: 700; }
```

Não dependa de hover para funcionalidade essencial porque nem todo dispositivo possui hover. Mantenha indicador visível de foco pelo teclado, normalmente com `:focus-visible`. Pseudo-classes nativas de formulário permanecem sincronizadas com o controle, então prefira-as a duplicar o mesmo estado em classes da aplicação, a menos que seu produto tenha outro conceito de estado.
