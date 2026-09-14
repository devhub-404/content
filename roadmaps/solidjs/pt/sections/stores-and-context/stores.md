# State Aninhado com `createStore`

Store fornece acesso reativo fine-grained a objects/arrays aninhados via proxies. `createStore` retorna state proxy read-only e setter capaz de atualizar paths selecionados sem substituir tree inteira.

```tsx
import { createStore } from "solid-js/store";

const [state, setState] = createStore({
  user: { name: "Mina", active: false },
  todos: []
});

setState("user", "active", true);
```

Use stores quando structured state aninhado se beneficia de tracking por propriedade. Signals continuam mais simples para valores independentes ou whole-value replacement. Não destructure store properties cedo se precisa manter reatividade.
