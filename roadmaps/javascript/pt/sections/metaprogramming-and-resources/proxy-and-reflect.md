# `Proxy` e `Reflect`

`Proxy` envolve objeto ou alvo chamável e intercepta operações fundamentais por traps como acesso, assignment, delete, construction e enumeração. `Reflect` expõe operações correspondentes como funções e frequentemente é a forma mais segura de um trap delegar ao comportamento normal da linguagem.

```js
const target = { count: 1 };

const observed = new Proxy(target, {
  set(object, key, value, receiver) {
    console.log("set", key, value);
    return Reflect.set(object, key, value, receiver);
  },
});

observed.count = 2;
```

Invariantes de Proxy impedem traps de relatar resultados impossíveis sobre propriedades não configuráveis e outros fatos fixos. Proxies são úteis em sistemas reativos, validação, membranes e tooling, mas tornam operações comuns indiretas e podem complicar otimização e debugging. Prefira objetos ou funções explícitas quando interceptação não fizer parte real da abstração.
