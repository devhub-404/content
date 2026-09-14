# Tracks, Linhas e `fr` no Grid

Grid é um sistema de layout bidimensional. Colunas e linhas são tracks separadas por grid lines; a interseção de uma linha e coluna é uma célula, e um item pode ocupar várias células. Filhos diretos do grid container viram grid items. Tracks explícitas vêm do template; placement também pode criar tracks implícitas.

```css
.layout {
  display: grid;
  grid-template-columns: 16rem 1fr;
  grid-template-rows: auto 1fr;
  gap: 1rem;
}
```

`fr` distribui espaço flexível restante depois de tamanhos fixos, gaps e contribuições intrínsecas. Não é simplesmente porcentagem. Minimums baseados em conteúdo podem tornar uma track `1fr` maior que o esperado; `minmax(0, 1fr)` é útil quando você quer explicitamente permitir encolher abaixo do minimum do conteúdo.
