# Overflow e Scroll Containers

Overflow ocorre quando o conteúdo não cabe em sua caixa. `overflow: auto` pode criar um scroll container quando necessário; `scroll` sempre solicita comportamento de rolagem; `hidden` corta overflow mantendo parte do scrolling programático; `clip` é um corte mais estrito. Os eixos inline e block podem ser controlados separadamente.

```css
.code-frame {
  max-inline-size: 100%;
  overflow: auto;
}

.long-token {
  overflow-wrap: anywhere;
}
```

Não esconda overflow antes de descobrir a causa. Um filho flex/grid pode precisar de permissão para encolher, texto pode precisar quebrar ou mídia pode precisar de tamanho máximo. Código largo e tabelas de dados frequentemente merecem rolagem local, enquanto prosa normalmente deve quebrar. `overflow-x: hidden` global é uma forma comum de esconder bug de layout em vez de resolvê-lo.
