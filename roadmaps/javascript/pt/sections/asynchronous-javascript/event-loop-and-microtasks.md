# Event Loop, Tasks e Microtasks

Execução JavaScript no navegador roda em call stack enquanto o host agenda trabalho posterior. Reações de Promise e `queueMicrotask()` usam mecanismo de microtasks/jobs; timers, input do usuário, eventos de rede e rendering participam do modelo de tasks do event loop do navegador.

```js
console.log("A");

queueMicrotask(() => console.log("microtask"));
setTimeout(() => console.log("timer"), 0);

console.log("B");
```

Código síncrono roda até o fim antes dos callbacks enfileirados. Microtasks são processadas em checkpoints definidos antes de tasks posteriores como timers. `setTimeout(fn, 0)` significa que o callback roda não antes daquele delay e depois do trabalho atual; não significa execução imediata. Trabalho síncrono longo bloqueia input e rendering na main thread.
