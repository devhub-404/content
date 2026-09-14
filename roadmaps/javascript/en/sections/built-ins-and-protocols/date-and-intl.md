# Dates and Internationalization

`Date` represents an instant as a millisecond timestamp, while its methods expose local-time or UTC calendar fields. Standardized ISO-style strings with explicit timezone information are safer for instants than ambiguous locale-formatted input. A calendar date such as a birthday is conceptually different from a timestamp.

```js
const deadline = new Date("2026-12-01T15:00:00Z");

const formatter = new Intl.DateTimeFormat("pt-BR", {
  dateStyle: "long",
  timeStyle: "short",
  timeZone: "America/Sao_Paulo",
});

console.log(formatter.format(deadline));
```

The `Intl` namespace handles locale-aware dates, numbers, currencies, lists, relative time, collation, plural rules, display names, and segmentation. Avoid manual English-centric formatting and sorting when users have locales. Keep stored data separate from its formatted display representation and reuse formatter instances on hot paths.
