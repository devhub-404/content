# Excess Property Checks

Object literals novos recebem checks extras para propriedades desconhecidas no tipo alvo. Isso encontra typos ou campos equivocados em locais de criação. A regra é intencionalmente mais estrita que assignment estrutural geral, onde variável pode conter propriedades adicionais e ainda ser compatível.

```ts
interface User {
  name: string;
}

const user: User = {
  name: "Mina",
  // role: "admin", // excess property in this fresh literal
};
```

Não contorne excess-property error com cast antes de entender se o campo extra é realmente pretendido. Se o objeto legitimamente suporta mais chaves, modele com index signature explícita ou tipo de domínio mais amplo. Se for typo, o check está fazendo trabalho útil.
