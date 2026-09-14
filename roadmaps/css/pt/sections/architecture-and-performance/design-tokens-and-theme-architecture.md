# Design Tokens e Arquitetura de Tema

Um sistema de tokens sustentável separa primitives brutos de papéis semânticos. Um token de paleta pode descrever cor literal, enquanto `--color-action` ou `--color-surface` descreve como o valor é usado. Componentes devem consumir tokens semânticos para temas sobrescreverem significado sem reescrever seletores do componente.

```css
@layer tokens {
  :root {
    --color-blue-600: oklch(52% .2 255);
    --color-surface: white;
    --color-action: var(--color-blue-600);
    --space-card: 1rem;
  }

  [data-theme="dark"] {
    --color-surface: #151515;
  }
}
```

Cascade layers podem dar precedência explícita a tokens, regras-base, componentes e utilities. Mantenha a superfície pública de tokens intencionalmente pequena: cada custom property da qual código externo depende vira parte de uma API de estilo. Não crie centenas de variáveis globais apenas porque custom properties são fáceis de declarar.
