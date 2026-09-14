# Whitespace, Quebra e Hifenização

`white-space` controla como espaços e quebras de linha são colapsados e se as linhas podem quebrar. `overflow-wrap` permite quebrar conteúdo que seria inquebrável quando necessário; `word-break` muda o comportamento de quebra de palavras de forma mais agressiva; `hyphens` pode ativar hifenização sensível ao idioma quando metadados e dicionários estão disponíveis.

```css
.prose {
  max-inline-size: 68ch;
  hyphens: auto;
}

.long-token {
  overflow-wrap: anywhere;
}

pre {
  white-space: pre-wrap;
}
```

Use a ferramenta menos agressiva que mantenha o conteúdo dentro do inline size. URLs longas podem precisar de `overflow-wrap: anywhere`; prosa comum não deve quebrar em letras arbitrárias. `pre-wrap` é útil quando whitespace do código-fonte importa mas as linhas ainda precisam quebrar. Metadados corretos de idioma no HTML são importantes para quebra e hifenização sensíveis ao idioma.
