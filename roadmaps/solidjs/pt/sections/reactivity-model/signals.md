# Signals

Signal é a primitive principal de reactive state do Solid. `createSignal` retorna getter e setter. Ler o getter dentro de tracking scope cria dependency; chamar setter notifica apenas computations que realmente dependem do signal.

```tsx
import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);

setCount(1);
setCount(value => value + 1);

console.log(count());
```

O getter como function importa: passar `count` preserva reatividade, enquanto `count()` passa apenas valor atual. Use updater quando next value depende do anterior e evite mutar object interno sem notificar Solid adequadamente.
