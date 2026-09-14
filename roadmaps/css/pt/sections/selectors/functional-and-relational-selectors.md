# `:is()`, `:where()`, `:not()` e `:has()`

Seletores funcionais reduzem repetição e expressam condições mais ricas. `:is()` corresponde a qualquer argumento e recebe especificidade do argumento mais específico. `:where()` corresponde da mesma forma, mas contribui zero especificidade. `:not()` exclui matches. `:has()` permite que o sujeito corresponda porque um seletor relativo teve sucesso, permitindo estilo baseado em filhos ou irmãos.

```css
article :is(h2, h3, h4) { line-height: 1.2; }
:where(article, section) > p { max-inline-size: 68ch; }
button:not(:disabled) { cursor: pointer; }
.card:has(img) { grid-template-columns: 8rem 1fr; }
```

Escolha `:is()` ou `:where()` conforme a intenção de cascata, não apenas conveniência. Use `:has()` para relações significativas já presentes no DOM, como estilizar um card de forma diferente quando contém mídia. Estado da aplicação já conhecido pelo JavaScript ainda pode ser mais claro como classe ou data attribute explícito do que como seletor relacional complicado.
