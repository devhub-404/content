# Inputs Numéricos, Data, Range, Cor e Arquivo

HTML inclui tipos especializados de input para domínios comuns de valor. `number` pode expressar `min`, `max` e `step`; `range` fornece um controle semelhante a slider para valor aproximado; tipos de data e hora podem oferecer seletores da plataforma; `color` pode oferecer um seletor de cor; e `file` permite escolher arquivos locais.

```html
<input type="number" name="qty" min="1" max="10" step="1">
<input type="range" name="volume" min="0" max="100">
<input type="date" name="start">
<input type="color" name="accent">
<input type="file" name="receipt" accept="image/*,.pdf">
```

As interfaces nativas variam por navegador e sistema operacional, então escolha o tipo por sua semântica de dados, não esperando aparência idêntica em todo lugar. `accept` em file input é apenas uma dica de seleção, não validação de segurança. Tipo, tamanho e conteúdo do arquivo ainda precisam ser verificados no servidor, e formulários de upload normalmente usam `multipart/form-data`.
