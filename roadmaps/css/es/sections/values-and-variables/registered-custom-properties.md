# Custom properties registradas con `@property`

`@property` registra una custom property con una sintaxis, comportamiento de herencia y valor inicial. El navegador obtiene información de tipo que una variable `--*` normal no tiene, por lo que puede validar antes e interpolar correctamente en animaciones cuando el tipo es animable.

```css
@property --progress {
  syntax: "<number>";
  inherits: false;
  initial-value: 0;
}

.bar {
  --progress: .65;
  scale: var(--progress) 1;
}
```

Registra variables cuando realmente forman parte de la API de un componente o necesitan interpolación tipada. Para la mayoría de tokens, una custom property normal es más simple. El registro no cambia que el valor participe en la cascada.
