# Event Loop, Tasks, and Microtasks

JavaScript execution in a browser runs on a call stack while the host schedules later work. Promise reactions and `queueMicrotask()` use the microtask/job mechanism; timers, user input, network events, and rendering participate in the browser's event-loop task model.

```js
console.log("A");

queueMicrotask(() => console.log("microtask"));
setTimeout(() => console.log("timer"), 0);

console.log("B");
```

Synchronous code runs to completion before queued callbacks execute. Microtasks are processed at defined checkpoints before later tasks such as timers. `setTimeout(fn, 0)` therefore means the callback runs no earlier than that delay and after current work; it does not mean immediate execution. Long synchronous work blocks input and rendering on the main thread.
