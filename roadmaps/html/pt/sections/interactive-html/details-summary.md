# `details` e `summary`

`details` cria um widget de disclosure e `summary` fornece o controle visível que o abre e fecha. O navegador fornece comportamento de ponteiro e teclado sem JavaScript personalizado. O atributo `open` representa o estado expandido e também pode estar presente inicialmente.

```html
<details>
  <summary>Shipping details</summary>
  <p>Orders leave within two business days.</p>
</details>
```

Use disclosure para conteúdo opcional que pode ser mostrado ou ocultado no lugar. Ele não substitui toda interface expansível: menus, diálogos modais, abas e controles específicos da aplicação possuem modelos de interação diferentes. Começar pelo elemento nativo é valioso porque semântica e comportamento básico já existem.
