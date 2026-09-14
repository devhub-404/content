# Flex Basis, Grow, Shrink e Tamanho Mínimo

Flex sizing começa no flex base size de cada item, normalmente controlado por `flex-basis`. Espaço livre positivo pode ser distribuído por `flex-grow`; espaço negativo participa de `flex-shrink`. A shorthand `flex` costuma ser mais clara porque grow, shrink e basis formam uma única política de sizing.

```css
.sidebar {
  flex: 0 0 16rem;
}

.main {
  flex: 1 1 0;
  min-inline-size: 0;
}
```

Flex items também possuem minimum size automático que pode preservar conteúdo longo. Por isso, um item principal pode causar overflow mesmo podendo encolher; `min-inline-size: 0` frequentemente expressa que ele pode ficar menor que o minimum intrínseco do conteúdo. `flex: 1` é comportamento shorthand, não simplesmente “uma fração da largura”.
