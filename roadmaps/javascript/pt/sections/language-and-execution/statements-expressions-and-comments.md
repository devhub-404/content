# Statements, Expressões e Comentários

Uma expressão produz um valor: literal, operação aritmética, chamada de função, acesso a propriedade ou expressão condicional. Um statement executa uma ação da linguagem, como declarar binding, ramificar, repetir, retornar ou lançar erro. Expressões aparecem frequentemente dentro de statements, então distingui-las ajuda a entender onde cada sintaxe pode ser usada.

```js
const price = 12;
const total = price * 3;

if (total > 30) {
  console.log("Large order");
}
```

Comentários usam `//` para uma linha e `/* ... */` para bloco. Bons comentários explicam intenção, restrições ou escolhas surpreendentes em vez de parafrasear código óbvio. JavaScript pode inserir ponto e vírgula em situações definidas, mas automatic semicolon insertion segue regras gramaticais; formatter consistente e quebras não ambíguas tornam o tema quase invisível.
