# Restrições de Tamanho e Tamanhos Intrínsecos

`width`/`height` e as formas lógicas `inline-size`/`block-size` expressam tamanhos preferidos. `min-*` e `max-*` adicionam limites inferior e superior, combinando bem com layout responsivo. Contêineres de texto normalmente precisam de block size automático para crescer com conteúdo, zoom, localização e fontes do usuário.

```css
.article {
  inline-size: 100%;
  max-inline-size: 70rem;
}

.label {
  inline-size: fit-content;
}

.grid {
  grid-template-columns: minmax(0, 1fr) max-content;
}
```

Tamanhos intrínsecos vêm do conteúdo. `min-content` aproxima o menor tamanho permitido pelas regras de quebra, `max-content` o tamanho preferido sem quebra e `fit-content` usa sizing intrínseco respeitando o espaço disponível. Flexbox e Grid usam contribuições intrínsecas intensamente; minimum sizes automáticos são razão comum para um item se recusar a encolher até aparecer `min-inline-size: 0` ou uma track `minmax(0, 1fr)`.
