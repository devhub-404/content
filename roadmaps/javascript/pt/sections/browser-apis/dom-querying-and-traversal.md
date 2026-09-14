# Consulta e Navegação no DOM

DOM é um object model do documento fornecido pelo navegador. `querySelector()` e `querySelectorAll()` usam seletores CSS para localizar elementos, enquanto a árvore de nodes expõe relações de pai, filho e irmãos. Consulte a partir da raiz estável mais estreita já conhecida em vez de buscar o documento inteiro repetidamente.

```js
const form = document.querySelector("#signup");
const fields = form.querySelectorAll("input");

for (const field of fields) {
  console.log(field.name);
}

console.log(form.parentElement);
```

`querySelectorAll()` retorna NodeList estática; algumas APIs DOM antigas retornam coleções live que mudam junto com o documento. Prefira referências diretas e estrutura semântica a seletores dependentes de muitos wrappers acidentais. DOM é API de host, então esses objetos não existem em ambiente ECMAScript puro salvo se o runtime fornecer equivalente.
