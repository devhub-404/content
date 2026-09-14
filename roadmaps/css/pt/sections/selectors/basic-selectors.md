# Seletores de Tipo, Classe, ID e Universal

Seletores de tipo correspondem a nomes de elementos, seletores de classe a tokens em `class`, seletores de ID a um `id`, e o seletor universal `*` corresponde a elementos sem adicionar especificidade. Classes costumam ser o melhor gancho reutilizável porque podem ser compartilhadas sem a alta especificidade de IDs.

```css
p { color: #333; }
.note { background: #fff8c5; }
#main-title { letter-spacing: -.02em; }
* { box-sizing: border-box; }
```

Listas de seletores separadas por vírgulas permitem compartilhar um bloco de declarações. Mantenha seletores ligados a significado estável ou estrutura de componente em vez de longos caminhos no DOM. Um ID é CSS válido, mas usá-lo rotineiramente como gancho de estilo torna overrides futuros desnecessariamente difíceis.
