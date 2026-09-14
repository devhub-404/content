# Declaration merging y namespaces

Algunas declaraciones con el mismo nombre se combinan, sobre todo interfaces y determinadas combinaciones con namespace. Esto permite contratos extensibles y patrones usados por bibliotecas JavaScript existentes.

```ts
interface Box {
  width: number;
}

interface Box {
  height: number;
}

const box: Box = {
  width: 10,
  height: 20,
};
```

Namespaces son un mecanismo de organización anterior al uso generalizado de ES modules. Aún aparecen en declarations y código legacy, pero para código nuevo de aplicaciones y librerías lo normal es usar módulos ECMAScript estándar.
