# Semântica Útil para Texto Inline

HTML inclui elementos inline para tipos comuns de texto. `abbr` identifica uma abreviação; `code` marca código de computador; `kbd` marca entrada do usuário; `samp` marca saída de programa; `sub` e `sup` representam subscrito e sobrescrito quando essa posição faz parte do significado; e `time` pode combinar texto legível com uma data ou hora em formato legível por máquinas.

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> structures web content.</p>
<p>Run <code>npm test</code> and press <kbd>Enter</kbd>.</p>
<p>Water is H<sub>2</sub>O and 2<sup>10</sup> is 1024.</p>
<p>Published <time datetime="2026-09-12">September 12, 2026</time>.</p>
```

Outros elementos úteis incluem `mark` para destaque relevante ao contexto, `small` para comentários secundários como texto legal, `cite` para o título de uma obra e `q` para uma citação curta inline. Esses elementos devem ser escolhidos pelo significado, não apenas porque a estilização padrão parece conveniente.
