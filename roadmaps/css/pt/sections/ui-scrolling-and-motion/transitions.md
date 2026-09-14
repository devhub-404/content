# Transitions e Starting Styles

Uma transition interpola uma propriedade animável quando seu valor computado muda. Especifique as propriedades que pretende animar em vez de `transition: all`, porque mudanças futuras sem relação podem começar a animar inesperadamente. Duração, timing function e delay controlam a progressão.

```css
.button {
  background: #2457d6;
  translate: 0 0;
  transition:
    background 150ms ease,
    translate 150ms ease;
}

.button:hover {
  background: #1749bd;
  translate: 0 -2px;
}
```

`@starting-style` pode fornecer valor inicial para transitions de entrada quando um estado recém-renderizado não tinha valor anterior, como popover abrindo. Mantenha estados estáticos inicial/final corretos sem animação. Opacidade e transforms frequentemente são alvos eficientes, mas meça rendering real quando performance importar em vez de presumir que todo transform é barato.
