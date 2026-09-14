# Labels, fieldsets y legends

Todo control de formulario necesita un nombre accesible. El patrón estándar es un `label` conectado mediante `for` e `id`, aunque también puede envolver al control. El label visible sigue disponible mientras el usuario escribe; el placeholder no lo sustituye.

```html
<label for="email">Email address</label>
<input id="email" name="email" type="email">

<fieldset>
  <legend>Delivery speed</legend>
  <label><input type="radio" name="speed" value="standard"> Standard</label>
  <label><input type="radio" name="speed" value="express"> Express</label>
</fieldset>
```

`fieldset` agrupa controles relacionados y `legend` da nombre al grupo. Es especialmente útil con radios y checkboxes relacionados, porque cada opción necesita el contexto de la pregunta general. Prefiere estas relaciones nativas antes que ARIA: el navegador ya sabe exponerlas de forma consistente.
