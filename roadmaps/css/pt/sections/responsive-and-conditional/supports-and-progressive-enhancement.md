# Feature Queries e Progressive Enhancement

`@supports` testa se o navegador aceita uma propriedade/valor ou sintaxe de seletor e aplica condicionalmente um bloco de CSS. É útil quando uma melhoria precisa de várias regras coordenadas. Para uma única propriedade, fallback normal costuma ser mais simples: escreva a declaração válida antiga primeiro e a nova depois.

```css
.component {
  position: absolute;
  inset-block-start: 100%;
}

@supports (position-area: block-end) {
  .component {
    position-area: block-end;
  }
}
```

Progressive enhancement significa que o baseline continua utilizável enquanto navegadores capazes recebem layout, visual ou interação melhores. Aceitar uma sintaxe não garante que todo comportamento relacionado esteja livre de bugs, então recursos críticos ainda precisam de testes. Prefira fallbacks baseados em padrões a browser sniffing e isole features novas para ajustá-las conforme o baseline de suporte evolui.
