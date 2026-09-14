# Números, Dimensões e Porcentagens

Valores CSS possuem tipos conforme o contexto. Números sem unidade, comprimentos, ângulos, tempos, resoluções, porcentagens, cores, imagens, identificadores e outros tipos aparecem em gramáticas diferentes. Um comprimento como `16px` não é intercambiável com ângulo ou tempo, e um número sem unidade pode ter significado completamente diferente dos mesmos dígitos com unidade.

```css
.box {
  inline-size: 20rem;
  rotate: 5deg;
  transition-duration: 200ms;
  opacity: .8;
  max-inline-size: 80%;
}
```

Porcentagens são valores relativos, mas a referência depende da propriedade. `width: 50%` normalmente resolve contra o tamanho inline de um containing block, enquanto outras propriedades percentuais podem usar referências diferentes. Não aprenda `%` apenas como “relativo ao pai”; veja o que a propriedade define. Zero frequentemente dispensa unidade de comprimento, mas contextos tipados ainda podem exigir ângulo, tempo ou outra dimensão.
