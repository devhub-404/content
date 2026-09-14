# Null, Undefined e Strict Null Checking

Com `strictNullChecks`, `null` e `undefined` são tipos distintos e precisam ser tratados antes de um valor ser usado como tipo não-null. Isso corresponde melhor ao comportamento real de JavaScript e evita grande classe de erros de acesso a propriedade ou chamada.

```ts
function findUser(id: string): User | undefined {
  return users.find(user => user.id === id);
}

const user = findUser("u1");
if (user) {
  console.log(user.name);
}
```

Modele ausência honestamente: busca pode retornar `T | undefined`, campo pode ser optional e API pode usar null deliberadamente. Não espalhe non-null assertions apenas para silenciar checker; `value!` é uma promessa sua ao TypeScript e não adiciona check em runtime. Prefira fluxo de controle ou inicialização melhor quando possível.
