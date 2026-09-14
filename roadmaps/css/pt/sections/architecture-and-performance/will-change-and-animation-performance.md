# `will-change` e Performance de Rendering

Mudanças de CSS podem disparar recálculo de estilo, layout, paint e compositing dependendo da propriedade e do contexto. Animações de transform e opacity frequentemente evitam layout repetido, mas o custo real depende do tamanho da superfície, efeitos, dispositivo e navegador. Use ferramentas de performance para identificar o gargalo antes de mudar arquitetura.

```css
.dragging {
  will-change: transform;
}

/* Remove the hint when the interaction ends. */
```

`will-change` é uma dica de que um elemento provavelmente mudará em breve. Navegadores podem alocar recursos ou layers extras em preparação, o que significa que abuso consome memória e pode piorar performance. Aplique pouco antes de uma interação exigente quando medições justificarem e remova depois. Não coloque `will-change` em todo elemento animado por padrão.
