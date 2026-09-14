# Transforms

Transforms movem, rotacionam, escalam, inclinam ou alteram o sistema de coordenadas renderizado após o layout. Eles não fazem caixas vizinhas no fluxo normal reservarem novo espaço. Propriedades individuais `translate`, `rotate` e `scale` são convenientes quando efeitos precisam ser controlados separadamente.

```css
.badge {
  translate: 0 -.15em;
  rotate: -2deg;
}

.button:active {
  scale: .98;
}
```

A ordem de funções em uma lista tradicional `transform` importa porque cada operação muda o sistema de coordenadas da próxima. `transform-origin` muda o pivô de rotação e escala. Transforms 3D adicionam eixo z e perspective; use deliberadamente porque movimento espacial grande pode afetar leitura e conforto. Transforms frequentemente criam stacking contexts.
