# Data Fetching Paralelo e Sequencial

Await de data independente um por vez cria waterfall. Inicie operations independentes juntas e use `Promise.all`, mantendo trabalho realmente dependente sequencial. Component composition também pode iniciar data concorrente em branches diferentes.

```tsx
const userPromise = getUser(id);
const postsPromise = getPosts(id);

const [user, posts] = await Promise.all([
  userPromise,
  postsPromise
]);
```

Paralelo não é automaticamente mais barato: page pode sobrecarregar DB/API com operations demais. Faça batch quando backend suporta e use Suspense boundaries quando partes podem streamar independentemente.
