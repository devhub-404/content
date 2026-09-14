# Extensão de Interfaces e Composição de Objetos

Interfaces podem estender um ou mais object types, produzindo contrato nomeado com membros herdados. Isso é composição no nível de tipos e não cria herança de prototype em runtime. Objeto simples pode satisfazer `Admin` sem ser instância de classe alguma.

```ts
interface Entity {
  id: string;
}

interface User extends Entity {
  name: string;
}

interface Admin extends User {
  permissions: string[];
}
```

Use extension quando a relação comunica contrato estável de subtipo. Para transformações ad-hoc ou unions, aliases e intersections podem ser mais expressivos. Evite hierarquias profundas de tipos apenas porque sintaxe OO existe; o grafo de tipos deve esclarecer o domínio, não imitar estrutura de classes sem necessidade.
