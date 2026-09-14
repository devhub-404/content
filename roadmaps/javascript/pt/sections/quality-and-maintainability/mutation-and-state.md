# Mutação e Atualizações de Estado

Objetos e arrays são referências mutáveis. Mutação não é inerentemente errada, mas estado mutável compartilhado cria acoplamento oculto porque várias partes podem observar e alterar o mesmo objeto. Updates copy-on-write são úteis quando o sistema se beneficia de valores claros antes/depois, como em várias arquiteturas de UI.

```js
const nextUser = {
  ...user,
  settings: {
    ...user.settings,
    theme: "dark",
  },
};
```

Spread e métodos de cópia de array são rasos, então referências aninhadas precisam da própria cópia quando também mudam. Não faça deep clone de tudo mecanicamente; cloning muda identidade e pode ser caro ou incorreto para class instances, Maps, funções, objetos do host e recursos externos. Escolha mutação ou cópia conforme regras de ownership e observação.
