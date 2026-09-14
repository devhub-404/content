# Signals

Un signal es la primitive principal de reactive state de Solid. `createSignal` retorna getter y setter. Leer el getter dentro de un tracking scope crea una dependency; llamar al setter notifica solo las computations que realmente dependen del signal.

```tsx
import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);

setCount(1);
setCount(value => value + 1);

console.log(count());
```

El getter como function importa: pasar `count` conserva reactividad, mientras `count()` pasa solo el valor actual. Usa updater cuando el next value depende del anterior y evita mutar un object interno sin notificar adecuadamente a Solid.
