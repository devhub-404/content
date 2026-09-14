# Fechas e internacionalización

`Date` representa un instante como timestamp en milisegundos y expone campos de calendario en tiempo local o UTC. Las strings ISO con timezone explícito son más seguras para representar instantes que formatos locales ambiguos. Una fecha de calendario y un instante no son siempre el mismo concepto.

```js
const deadline = new Date("2026-12-01T15:00:00Z");

const formatter = new Intl.DateTimeFormat("pt-BR", {
  dateStyle: "long",
  timeStyle: "short",
  timeZone: "America/Sao_Paulo",
});

console.log(formatter.format(deadline));
```

`Intl` ofrece formato y comparación sensibles a locale para fechas, números, monedas, listas, plural, collation, nombres y segmentación. No construyas reglas manuales centradas en inglés. Mantén los datos separados de su representación localizada y reutiliza formatters cuando se usan con frecuencia.
