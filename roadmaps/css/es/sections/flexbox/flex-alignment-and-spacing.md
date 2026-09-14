# Alineación flex, gaps y márgenes auto

`justify-content` distribuye items o espacio en el eje principal. `align-items` alinea en el eje transversal y `align-self` puede cambiar un item. `gap` crea separación consistente entre items sin añadir margen exterior.

```css
.nav {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.nav__account {
  margin-inline-start: auto;
}
```

Los márgenes auto absorben espacio libre y son muy útiles para empujar un item o grupo hacia el final. Como los ejes cambian con `flex-direction`, comprueba la dirección antes de concluir que una propiedad de alineación está actuando al revés.
