# Checkboxes, Radio Buttons e Select

Checkboxes representam escolhas independentes de ligado/desligado. Radio buttons representam uma escolha dentro de um grupo e pertencem ao mesmo grupo quando compartilham `name`; cada radio precisa de um `value` diferente. `select` apresenta uma lista controlada de opções `option`, e `optgroup` pode rotular grupos em menus maiores.

```html
<label><input type="checkbox" name="newsletter"> Newsletter</label>

<label><input type="radio" name="plan" value="basic"> Basic</label>
<label><input type="radio" name="plan" value="pro"> Pro</label>

<select name="country">
  <option value="">Choose a country</option>
  <option value="br">Brazil</option>
  <option value="jp">Japan</option>
</select>
```

Use o controle cuja interação corresponde à escolha. Um conjunto curto de opções mutuamente exclusivas costuma ser mais claro como radios porque todas ficam visíveis. Um select é útil quando a lista é maior ou o espaço importa. Controles nativos de escolha já possuem comportamento de teclado, foco e acessibilidade que é caro reproduzir corretamente.
