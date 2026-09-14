# `script` e `noscript`

`script` incorpora ou carrega JavaScript. Prefira arquivos externos para código reutilizável de aplicação e escolha carregamento clássico, deferido, async ou módulo conforme as dependências. Scripts inline são válidos, mas podem dificultar cache, políticas de segurança e manutenção quando crescem além de configuração específica do documento.

```html
<script type="module" src="/scripts/main.js"></script>

<noscript>
  <p>This dashboard needs JavaScript for live editing.</p>
</noscript>
```

`noscript` fornece marcação para ambientes em que scripts relevantes estão desabilitados ou indisponíveis. Use quando a experiência sem JavaScript precisa de uma explicação ou caminho alternativo real. Melhor ainda, quando o produto permite, renderize conteúdo e formulários úteis em HTML primeiro e os aprimore com JavaScript em vez de deixar o documento inteiro vazio sem execução de scripts.
