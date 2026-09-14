# Alinhamento e Decoração de Texto

`text-align` controla alinhamento inline; valores lógicos `start` e `end` seguem a direção de escrita e costumam ser mais portáveis que left/right. Justificação muda espaçamento para alinhar as duas bordas e deve ser testada com idioma e largura reais. Espaçamento de letras e palavras também afeta legibilidade e não deve ser usado para forçar encaixe visual arbitrário.

```css
.article {
  text-align: start;
}

.article a {
  text-decoration-thickness: .08em;
  text-underline-offset: .18em;
}
```

Propriedades de text decoration controlam linha, estilo, espessura, offset e comportamento de skip; marcas de ênfase atendem sistemas de escrita onde ênfase aparece ao lado dos glifos. Ao personalizar links, preserve affordance reconhecível. Text shadows e decoração afetam pintura, mas não mudam a geometria subjacente das line boxes.
