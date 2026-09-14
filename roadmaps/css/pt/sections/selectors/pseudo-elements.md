# Pseudo-elementos e Conteúdo Gerado

Pseudo-elementos estilizam partes geradas ou abstratas de um elemento. `::before` e `::after` podem gerar apresentação com `content`; `::marker` alcança marcadores de lista; `::selection` texto selecionado; `::first-line` e `::first-letter` fragmentos tipográficos onde se aplicam.

```css
.tag::before {
  content: "#";
  opacity: .6;
}

li::marker { font-weight: 700; }

::selection {
  background: Highlight;
  color: HighlightText;
}
```

Conteúdo gerado é apresentação, então não coloque instruções ou rótulos essenciais apenas em `content`. Pseudo-elementos podem formar caixas visuais reais e participar de posicionamento, empilhamento e overflow. Trate-os com a mesma disciplina de layout das caixas comuns, mesmo que não apareçam como nós de elemento normais no HTML.
