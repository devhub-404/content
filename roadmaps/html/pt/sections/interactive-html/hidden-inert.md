# `hidden` e `inert`

`hidden` indica que um elemento não é relevante para apresentação no momento. Um elemento hidden não é renderizado da forma normal. `inert` é diferente: torna uma subárvore não interativa e a remove da navegação de foco e interação de acessibilidade comuns, mesmo que ela continue visível.

```html
<section hidden>
  <h2>Draft report</h2>
</section>

<main inert>
  ...
</main>
```

Use cada um para o estado que realmente representa. Conteúdo que não faz parte da interface apresentada pode ser oculto; conteúdo temporariamente indisponível porque outra interação possui a atenção pode ficar inert. Diálogos modais nativos já gerenciam a inércia do fundo, então não sobreponha mecanismos sem uma razão separada.
