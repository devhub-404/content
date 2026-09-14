# Cómo elige un valor la cascada

Cuando varias declaraciones pueden establecer la misma propiedad, CSS usa la cascada. Primero una regla debe ser relevante: el selector tiene que coincidir y las condiciones externas deben cumplirse. Después se comparan origen e importancia, capas, especificidad, proximidad de `@scope` y finalmente el orden de aparición.

```css
.message { color: navy; }
.message { color: rebeccapurple; }
```

Por eso «la última regla gana» solo describe el último desempate. Al depurar, comprueba primero si la regla coincide, luego su origen y layer, después la especificidad y el scope, y solo al final el orden. Seguir ese proceso evita subir especificidad al azar para forzar un resultado.
