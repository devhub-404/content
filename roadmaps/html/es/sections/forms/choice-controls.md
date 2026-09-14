# Checkboxes, radio buttons y `select`

Los checkboxes representan decisiones independientes de sí/no. Los radio buttons representan una única elección dentro de un grupo y forman el mismo grupo cuando comparten `name`; cada radio necesita un `value` distinto. `select` presenta una lista controlada de `option`, y `optgroup` puede agrupar opciones.

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

Elige el control según la interacción. Un conjunto corto de opciones excluyentes suele ser más claro como radios porque todas son visibles; un select funciona mejor cuando la lista es larga o el espacio importa. Los controles nativos ya incluyen teclado, foco y comportamiento accesible que resulta costoso recrear correctamente.
