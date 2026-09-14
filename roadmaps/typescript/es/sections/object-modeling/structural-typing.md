# Tipado estructural

TypeScript es principalmente estructural: la compatibilidad depende de que un valor tenga la forma requerida, no de haber declarado una relación nominal. Un objeto con todos los miembros necesarios puede satisfacer una interface sin mencionarla explícitamente.

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

Esto encaja con JavaScript y facilita composición, pero dos conceptos distintos con la misma estructura también pueden ser compatibles. Cuando la identidad de dominio importa, usa discriminants, miembros privados o branded types para impedir intercambios accidentales.
