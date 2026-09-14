# Transitions y estilos iniciales

Una transition interpola una propiedad animable cuando cambia su valor computado. Es mejor listar las propiedades que quieres animar que usar `transition: all`, porque futuros cambios no relacionados podrían empezar a animarse sin intención.

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

`@starting-style` puede aportar el valor inicial de una transición de entrada cuando el elemento acaba de aparecer, por ejemplo un popover. El estado final debe ser correcto incluso sin animación. Opacity y transform suelen ser buenos candidatos, pero el rendimiento real debe medirse.
