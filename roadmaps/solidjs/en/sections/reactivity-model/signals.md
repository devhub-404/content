# Signals

A signal is Solid's primary reactive state primitive. `createSignal` returns a getter and setter. Reading the getter inside a tracking scope creates a dependency; calling the setter notifies the computations that actually depend on that signal.

```tsx
import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);

setCount(1);
setCount(value => value + 1);

console.log(count());
```

The function-call getter is important: passing `count` preserves reactivity, while passing `count()` passes only the current value. Use updater functions when the next value depends on the previous value, and avoid mutating an object inside a signal without also notifying Solid appropriately.
