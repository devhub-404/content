# Datas e Internacionalização

`Date` representa um instante como timestamp em milissegundos, enquanto seus métodos expõem campos de calendário em horário local ou UTC. Strings padronizadas semelhantes a ISO com timezone explícito são mais seguras para instantes que input formatado por locale. Uma data de calendário como aniversário é conceitualmente diferente de timestamp.

```js
const deadline = new Date("2026-12-01T15:00:00Z");

const formatter = new Intl.DateTimeFormat("pt-BR", {
  dateStyle: "long",
  timeStyle: "short",
  timeZone: "America/Sao_Paulo",
});

console.log(formatter.format(deadline));
```

O namespace `Intl` trata datas, números, moedas, listas, tempo relativo, collation, regras de plural, nomes e segmentação sensíveis a locale. Evite formatação e ordenação manual centrada em inglês quando há usuários de vários locales. Mantenha dados armazenados separados da representação formatada e reutilize formatters em caminhos quentes.
