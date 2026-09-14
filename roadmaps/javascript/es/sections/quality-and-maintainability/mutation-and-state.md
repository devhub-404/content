# Mutación y actualizaciones de estado

Objetos y arrays son referencias mutables. Mutar no es malo por sí mismo, pero el estado mutable compartido crea acoplamiento porque varias partes pueden observar y cambiar el mismo objeto. Updates copy-on-write son útiles cuando necesitas comparar claramente antes y después.

```js
const nextUser = {
  ...user,
  settings: {
    ...user.settings,
    theme: "dark",
  },
};
```

Spread y métodos de copia son superficiales; referencias anidadas deben copiarse también si cambian. No deep-clones todo mecánicamente, porque cambia identidades y puede ser incorrecto para class instances, Maps, funciones u objetos del host. Decide mutación o copia según ownership y observación.
