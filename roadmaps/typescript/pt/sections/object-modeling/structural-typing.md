# Tipagem Estrutural

TypeScript é principalmente estrutural: compatibilidade depende da forma exigida pelo tipo, não de uma relação nominal declarada. Um valor com pelo menos os membros compatíveis necessários normalmente pode ser atribuído mesmo que nunca tenha declarado explicitamente aquela interface.

```ts
interface Named {
  name: string;
}

const value = {
  name: "Mina",
  role: "admin",
};

const named: Named = value;
```

Tipagem estrutural combina com o modelo de objetos JavaScript e torna composição flexível, mas também significa que dois valores conceitualmente diferentes com estrutura idêntica podem ser assignable. Quando identidade de domínio importa, use discriminants literais, membros privados de classe ou branded-style types para impedir troca acidental.
