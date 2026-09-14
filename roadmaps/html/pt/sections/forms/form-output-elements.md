# `datalist`, `output`, `meter` e `progress`

`datalist` fornece sugestões para um input compatível sem restringir o usuário àquelas sugestões. É diferente de `select`, onde as escolhas são controladas. As interfaces nativas de datalist variam entre navegadores, então use para sugestões leves, não para fluxos críticos de seleção.

```html
<input name="city" list="cities">
<datalist id="cities">
  <option value="Lisbon">
  <option value="Tokyo">
</datalist>

<output>$48</output>
<meter min="0" max="100" value="72">72%</meter>
<progress max="100" value="40">40%</progress>
```

`output` representa o resultado de um cálculo ou ação. `meter` representa uma medição escalar dentro de um intervalo conhecido, como pontuação ou uso de armazenamento. `progress` representa o progresso de conclusão de uma tarefa. Embora meter e progress possam parecer semelhantes, descrevem conceitos diferentes e não devem ser trocados apenas pela aparência.
