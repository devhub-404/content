# Como a Cascata Escolhe um Valor

Quando várias declarações podem definir a mesma propriedade no mesmo elemento, o CSS usa a cascata. Primeiro, a declaração precisa ser relevante: o seletor deve corresponder e condições externas devem ser verdadeiras. Depois, CSS compara origem e importância, ordem de layers, especificidade, proximidade de escopo e finalmente ordem no código.

```css
.message { color: navy; }
.message { color: rebeccapurple; }
```

Essas duas declarações empatam até a ordem no código, então a segunda vence. “A última regra vence” é apenas um desempate final, não a cascata inteira. Ao depurar, pergunte primeiro se a regra correspondeu, depois em qual origem/layer está, depois especificidade e escopo e só então se a ordem posterior decide o resultado.
