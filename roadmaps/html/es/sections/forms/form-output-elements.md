# `datalist`, `output`, `meter` y `progress`

`datalist` proporciona sugerencias a un input compatible sin restringir al usuario a esas opciones. Es diferente de `select`, donde las opciones están controladas. La interfaz nativa de datalist varía entre navegadores, por lo que funciona mejor para sugerencias ligeras que para decisiones críticas.

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

`output` representa el resultado de un cálculo o acción. `meter` representa una medida escalar dentro de un rango conocido, como una puntuación o uso de almacenamiento. `progress` representa el avance de una tarea. Aunque meter y progress pueden parecerse, describen conceptos distintos y no deben intercambiarse solo por apariencia.
