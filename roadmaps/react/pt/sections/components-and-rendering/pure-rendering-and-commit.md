# Rendering Puro e Commit Phase

Um render deve ser puro: os mesmos props, state e context devem produzir o mesmo JSX sem mutar dados externos. Assim React pode chamar a lógica de rendering quando necessário e só fazer commit do resultado escolhido no DOM após o render funcionar.

```jsx
function Price({ amount }) {
  const formatted = new Intl.NumberFormat('en', {
    style: 'currency',
    currency: 'USD'
  }).format(amount);

  return <span>{formatted}</span>;
}
```

Não inicie requests, mute DOM, escreva storage ou altere state de module durante render. Cálculos determinísticos são adequados. Trabalho que sincroniza React com sistema externo pertence a events, effects, APIs de dados do servidor ou outra boundary explícita.
