# Parâmetros, Defaults e Rest

JavaScript não impõe aridade em runtime. Parâmetros ausentes recebem `undefined`, argumentos extras são permitidos, parâmetros default substituem `undefined` por uma expressão e rest parameter coleta argumentos restantes em array real. O rest precisa ser o último parâmetro.

```js
function format(name, prefix = "User", ...tags) {
  return `${prefix}: ${name} [${tags.join(", ")}]`;
}

format("Mina", undefined, "admin", "active");
```

Funções comuns também expõem o objeto array-like `arguments`, mas rest parameters são mais claros em código moderno e funcionam naturalmente com métodos de array. Defaults são avaliados na chamada. Se uma função acumula muitos parâmetros posicionais, objeto de opções normalmente comunica nomes, defaults e extensão futura melhor que lista longa de argumentos.
