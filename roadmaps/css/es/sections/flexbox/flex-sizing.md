# Flex basis, grow, shrink y tamaño mínimo

El sizing flex parte del flex base size, normalmente controlado por `flex-basis`. `flex-grow` distribuye espacio positivo y `flex-shrink` participa cuando falta espacio. La shorthand `flex` expresa las tres decisiones como una sola política.

```css
.sidebar {
  flex: 0 0 16rem;
}

.main {
  flex: 1 1 0;
  min-inline-size: 0;
}
```

Los flex items también tienen un minimum automático que puede impedir que el contenido se encoja. Por eso `min-inline-size: 0` resuelve muchos overflows legítimos. `flex: 1` es una shorthand con comportamiento definido, no simplemente «una fracción del ancho».
