# Re-exports e Ciclos

Re-exports permitem que feature ou pacote exponha superfície pública deliberada mantendo arquivos internos como detalhes de implementação. `export *` pode ser conciso, mas torna os nomes públicos menos óbvios e pode criar conflitos quando vários módulos exportam o mesmo nome.

```js
// public-api.js
export { createUser } from "./create-user.js";
export { validateUser } from "./validate-user.js";
export { UserError } from "./errors.js";
```

ES modules definem dependências circulares, mas ciclos fortemente acoplados podem ser difíceis porque bindings importados podem existir antes de o módulo definidor terminar inicialização. Prefira extrair responsabilidade compartilhada de nível inferior em vez de módulos exigirem o estado inicializado um do outro. Uma fronteira pública estável deve permitir mudar arquivos internos sem quebrar consumidores.
