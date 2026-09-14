# Color Schemes e Forced Colors

`color-scheme` informa ao navegador quais esquemas light/dark a página consegue renderizar, permitindo que controles do user agent e system colors se adaptem. Ambientes forced-colors podem substituir cores do autor para atender necessidades de contraste; palavras-chave de cores do sistema e pistas estruturais são valiosas ali.

```css
:root {
  color-scheme: light dark;
}

.alert {
  border: 2px solid currentColor;
}

@media (forced-colors: active) {
  .alert {
    forced-color-adjust: auto;
  }
}
```

Não codifique estado apenas por matiz. Texto, bordas, ícones, formas ou outra estrutura devem preservar significado quando cores são remapeadas. `forced-color-adjust` pode retirar um elemento estreito de parte do comportamento forced-colors, mas fazer isso amplamente derrota o modo de acessibilidade escolhido pelo usuário. Teste dark mode, forced colors e contraste aumentado como ambientes reais.
