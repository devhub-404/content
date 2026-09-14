# Custom Properties Registradas com `@property`

`@property` registra uma custom property com sintaxe, comportamento de herança e valor inicial. O registro fornece ao navegador informação de tipo que variáveis `--*` comuns não possuem. Isso pode fazer valores validarem mais cedo, receberem valor inicial controlado e interpolarem em animações quando o tipo declarado é animável.

```css
@property --progress {
  syntax: "<number>";
  inherits: false;
  initial-value: 0;
}

.bar {
  --progress: .65;
  scale: var(--progress) 1;
}
```

Use registro quando a variável se comporta como parte da API de um componente e informação de tipo traz valor real. Custom properties comuns continuam mais simples para a maioria dos tokens. A Properties and Values API também possui forma de registro em JavaScript; os dois mecanismos descrevem o mesmo tipo de custom property tipada.
