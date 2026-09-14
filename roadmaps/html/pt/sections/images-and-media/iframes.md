# Iframes e Documentos Incorporados

`iframe` incorpora outro contexto de navegação dentro da página atual. Forneça um `title` útil para que usuários identifiquem o frame antes de entrar nele. Largura e altura fornecem geometria inicial, e frames fora da tela podem ser candidatos a lazy loading.

```html
<iframe
  src="/embedded/map"
  title="Store location map"
  width="640"
  height="400"
  loading="lazy"
  sandbox>
</iframe>
```

O atributo `sandbox` aplica um conjunto de restrições ao conteúdo incorporado; tokens podem restaurar seletivamente capacidades necessárias. Sandboxing é um recurso de segurança com regras sutis, então conceda apenas as permissões necessárias. Iframes são mais pesados e isolados que elementos normais: use quando o conteúdo realmente pertence a outro contexto de documento, não como mecanismo genérico de componentes.
