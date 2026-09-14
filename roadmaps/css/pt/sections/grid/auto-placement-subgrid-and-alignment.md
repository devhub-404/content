# Auto-placement, Alinhamento e Subgrid

Grid items sem posição explícita usam o algoritmo de auto-placement. `grid-auto-flow` controla placement orientado por linhas ou colunas, enquanto `grid-auto-rows` e `grid-auto-columns` dimensionam tracks implícitas. Dense packing pode preencher buracos, mas pode fazer a ordem visual divergir do código, então use com cuidado.

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: 10rem;
}

.card {
  display: grid;
  grid-template-rows: subgrid;
  grid-row: span 3;
}
```

Grid usa propriedades de Box Alignment para alinhar itens e distribuir tracks. `subgrid` permite a um grid aninhado reutilizar o sizing de tracks do pai em um ou ambos os eixos, útil quando cards repetidos devem alinhar títulos, corpos ou rodapés entre irmãos. Use grid aninhado independente quando o filho deve possuir sua geometria; use subgrid quando alinhamento com tracks ancestrais é a relação real.
