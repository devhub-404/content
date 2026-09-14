# Tamanho de Fonte, Line Height e Fontes Variáveis

Tipografia legível precisa de tamanho de fonte, line height e medida apropriados. `line-height` sem unidade escala com o tamanho da fonte de cada elemento e costuma ser robusto para tipografia de corpo herdada. Títulos frequentemente usam line height mais apertado por serem maiores e curtos. Mantenha texto de corpo escalável e teste zoom em vez de travar tipografia em pixels fixos.

```css
body {
  font-size: 1rem;
  line-height: 1.6;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
  line-height: 1.1;
  font-weight: 650;
  font-optical-sizing: auto;
}
```

Fontes variáveis podem expor ranges como peso, largura, inclinação e optical size. Prefira propriedades de alto nível como `font-weight`, `font-stretch` e `font-optical-sizing` quando correspondem ao eixo necessário. `font-variation-settings` de baixo nível é útil para eixos customizados, mas o arquivo da fonte precisa realmente fornecer o eixo e o range solicitados.
