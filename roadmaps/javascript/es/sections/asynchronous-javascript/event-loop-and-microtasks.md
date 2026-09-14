# Event loop, tasks y microtasks

En el navegador, JavaScript ejecuta código en una call stack mientras el host agenda trabajo posterior. Reacciones de Promise y `queueMicrotask()` usan microtasks; timers, input y muchos eventos se procesan como tasks dentro del modelo del event loop.

```js
console.log("A");

queueMicrotask(() => console.log("microtask"));
setTimeout(() => console.log("timer"), 0);

console.log("B");
```

El código síncrono termina antes de ejecutar callbacks encolados. Las microtasks se procesan en checkpoints antes de tasks posteriores como timers. `setTimeout(fn, 0)` no significa ejecución inmediata. Trabajo síncrono largo bloquea input y rendering en la main thread.
