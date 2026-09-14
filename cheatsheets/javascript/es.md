---
locale: es
status: published
title: "JavaScript"
slug: javascript
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de JavaScript."
tags:
  - javascript
  - cheatsheet
  - quick-reference
references:
  - label: "MDN: JavaScript Guide"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide
  - label: "MDN: JavaScript Modules"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules
  - label: "MDN: JavaScript Reference"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference
---

# JavaScript

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Lenguaje y ejecución

**JavaScript y entornos de ejecución**

```js
const total = 2 + 3;
console.log(total);
```

**Scripts, módulos y Strict Mode**

```html
<script src="/legacy.js" defer></script>
<script type="module" src="/app.js"></script>
```

**Statements, expresiones y comentarios**

```js
const price = 12;
const total = price * 3;

if (total > 30) {
  console.log("Large order");
}
```

**`let`, `const` y `var`**

```js
const taxRate = 0.2;
let total = 100;
total += total * taxRate;

if (total > 100) {
  const message = "Large total";
  console.log(message);
}
```

## Valores, tipos y operadores

**Tipos primitivos**

```js
const name = "Mina";       // string
const count = 42;          // number
const exact = 42n;         // bigint
const active = true;       // boolean
const missing = undefined;
const empty = null;
const key = Symbol("key");
```

**Numbers, BigInt y Math**

```js
const average = (10 + 15 + 20) / 3;
const rounded = Math.round(average);
const safe = Number.isFinite(rounded);

const huge = 9_007_199_254_740_993n;
```

**Strings y template literals**

```js
const first = "Ada";
const last = "Lovelace";
const label = `${first} ${last}`;

const message = `Hello,
${label}!`;
```

**Truthiness, valores nullish y coerción**

```js
const input = "";
if (!input) {
  console.log("No input");
}

const page = settings.page ?? 1;
const count = Number("42");
```

**Igualdad y comparación**

```js
0 === false;          // false
0 == false;           // true
Object.is(NaN, NaN);  // true

const sameUser = a.id === b.id;
```

**Operadores, short-circuit y optional chaining**

```js
const canEdit = signedIn && permissions.includes("edit");
const label = compact ? "Save" : "Save changes";
const city = user.address?.city ?? "Unknown";

settings.theme ??= "system";
```

## Flujo de control y errores

**Condicionales**

```js
if (score >= 90) {
  grade = "A";
} else if (score >= 80) {
  grade = "B";
} else {
  grade = "C";
}

const status = active ? "online" : "offline";
```

**Loops y statements de iteración**

```js
for (let i = 0; i < 3; i++) {
  console.log(i);
}

for (const item of items) {
  console.log(item);
}

while (queue.length > 0) {
  process(queue.shift());
}
```

**Excepciones**

```js
function parseConfig(text) {
  try {
    return JSON.parse(text);
  } catch (error) {
    throw new Error("Invalid configuration", { cause: error });
  } finally {
    console.log("Parse attempt finished");
  }
}
```

**Invariantes del programa y validación**

```js
function transfer(amount) {
  if (!Number.isFinite(amount) || amount <= 0) {
    throw new RangeError("amount must be a positive finite number");
  }

  // Later code can rely on the invariant.
}
```

## Funciones, scope y closures

**Funciones y valores de retorno**

```js
function add(a, b) {
  return a + b;
}

const multiply = function (a, b) {
  return a * b;
};
```

**Parámetros, defaults y rest**

```js
function format(name, prefix = "User", ...tags) {
  return `${prefix}: ${name} [${tags.join(", ")}]`;
}

format("Mina", undefined, "admin", "active");
```

**Arrow functions y `this` léxico**

```js
const double = value => value * 2;

const counter = {
  value: 0,
  start() {
    setTimeout(() => {
      this.value += 1;
    }, 100);
  },
};
```

**Scope léxico y closures**

```js
function makeCounter() {
  let count = 0;

  return function next() {
    count += 1;
    return count;
  };
}

const next = makeCounter();
next(); // 1
next(); // 2
```

**Callbacks y funciones de orden superior**

```js
function repeat(times, action) {
  for (let i = 0; i < times; i++) {
    action(i);
  }
}

repeat(3, index => console.log(index));
```

**Recursión**

```js
function factorial(n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}
```

## Objetos, prototypes y classes

**Objetos y propiedades**

```js
const field = "email";

const user = {
  id: 42,
  name: "Mina",
  [field]: "mina@example.com",
};

console.log(user.name);
console.log(user["email"]);
```

**Object spread y destructuring**

```js
const user = { name: "Mina", role: "admin" };
const updated = { ...user, role: "editor" };

const {
  name: displayName,
  role = "guest",
} = updated;
```

**Métodos, `this`, `bind`, `call` y `apply`**

```js
const account = {
  balance: 100,
  deposit(amount) {
    this.balance += amount;
  },
};

const deposit = account.deposit.bind(account);
deposit(25);
```

**La prototype chain**

```js
const animal = {
  speak() {
    return "sound";
  },
};

const dog = Object.create(animal);
dog.name = "Pico";

dog.speak();
```

**Classes y campos privados**

```js
class Counter {
  #value = 0;

  increment() {
    this.#value += 1;
    return this.#value;
  }

  get value() {
    return this.#value;
  }
}
```

**Herencia y miembros static**

```js
class User {
  constructor(name) {
    this.name = name;
  }

  describe() {
    return this.name;
  }
}

class Admin extends User {
  static role = "admin";

  describe() {
    return `${super.describe()} (admin)`;
  }
}
```

**Property descriptors y accessors**

```js
const user = {};

Object.defineProperty(user, "id", {
  value: 42,
  writable: false,
  enumerable: true,
  configurable: false,
});
```

## Arrays y colecciones

**Fundamentos de arrays**

```js
const items = ["a", "b", "c"];
items.push("d");

console.log(items[0]);
console.log(items.at(-1));
console.log(items.length);
```

**Transformar, buscar y reducir arrays**

```js
const activeNames = users
  .filter(user => user.active)
  .map(user => user.name);

const admin = users.find(user => user.role === "admin");
const allValid = users.every(user => user.name.length > 0);
const total = prices.reduce((sum, price) => sum + price, 0);
```

**Copiar y ordenar arrays**

```js
const sorted = users.toSorted((a, b) =>
  a.name.localeCompare(b.name)
);

const reversed = items.toReversed();
const updated = items.with(1, "new value");
const removed = items.toSpliced(2, 1);
```

**Array destructuring y spread**

```js
const [first, second, ...rest] = items;
const copy = [...items];
const combined = [...left, ...right];

function point([x, y]) {
  return { x, y };
}
```

**`Map` y `Set`**

```js
const visits = new Map();
visits.set(user, 3);

const tags = new Set(["js", "web", "js"]);
tags.add("css");

console.log(tags.size);
```

**Weak collections**

```js
const metadata = new WeakMap();

function attachMetadata(element, data) {
  metadata.set(element, data);
}

function getMetadata(element) {
  return metadata.get(element);
}
```

**Typed arrays y datos binarios**

```js
const buffer = new ArrayBuffer(8);
const bytes = new Uint8Array(buffer);
const numbers = new Uint32Array(buffer);

bytes[0] = 255;
console.log(numbers[0]);
```

## Built-ins y protocolos del lenguaje

**JSON**

```js
const text = JSON.stringify({
  id: 42,
  active: true,
});

const value = JSON.parse(text);
```

**Fechas e internacionalización**

```js
const deadline = new Date("2026-12-01T15:00:00Z");

const formatter = new Intl.DateTimeFormat("pt-BR", {
  dateStyle: "long",
  timeStyle: "short",
  timeZone: "America/Sao_Paulo",
});

console.log(formatter.format(deadline));
```

**Expresiones regulares**

```js
const pattern = /^(?<user>[a-z0-9._-]+)@(?<host>[a-z0-9.-]+)$/i;
const match = pattern.exec("mina@example.com");

if (match) {
  console.log(match.groups.user);
}
```

**Iterables e iterators**

```js
const range = {
  from: 1,
  to: 3,
  *[Symbol.iterator]() {
    for (let value = this.from; value <= this.to; value++) {
      yield value;
    }
  },
};

console.log([...range]);
```

**Generators y async generators**

```js
function* ids() {
  let id = 1;
  while (true) {
    yield id++;
  }
}

async function* pages(loadPage) {
  for (let page = 1; ; page++) {
    const items = await loadPage(page);
    if (items.length === 0) return;
    yield items;
  }
}
```

**Symbols y hooks de protocolo**

```js
const internalId = Symbol("internalId");

const record = {
  [internalId]: 42,
  [Symbol.toStringTag]: "Record",
};
```

## JavaScript asíncrono

**Event loop, tasks y microtasks**

```js
console.log("A");

queueMicrotask(() => console.log("microtask"));
setTimeout(() => console.log("timer"), 0);

console.log("B");
```

**Promises y chaining**

```js
loadUser()
  .then(user => loadOrders(user.id))
  .then(orders => renderOrders(orders))
  .catch(error => showError(error))
  .finally(() => stopSpinner());
```

**Composición de Promises**

```js
const [user, settings] = await Promise.all([
  loadUser(),
  loadSettings(),
]);

const first = await Promise.any([
  fetchFromPrimary(),
  fetchFromReplica(),
]);
```

**`async` y `await`**

```js
async function loadDashboard() {
  const response = await fetch("/api/dashboard");

  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }

  return response.json();
}
```

**Iteración asíncrona**

```js
async function* pages(loadPage) {
  let page = 1;

  while (true) {
    const result = await loadPage(page++);
    if (result.length === 0) return;
    yield result;
  }
}

for await (const page of pages(loadPage)) {
  console.log(page);
}
```

## Módulos

**Imports y exports**

```js
// math.js
export const PI = Math.PI;
export function area(radius) {
  return PI * radius ** 2;
}

// app.js
import { PI, area as circleArea } from "./math.js";
```

**Re-exports y ciclos**

```js
// public-api.js
export { createUser } from "./create-user.js";
export { validateUser } from "./validate-user.js";
export { UserError } from "./errors.js";
```

**Dynamic import y `await` en el nivel superior**

```js
async function openEditor() {
  const { createEditor } = await import("./editor.js");
  return createEditor();
}

// module top level
const config = await loadConfig();
```

**Resolución de módulos por el host**

```js
import { format } from "./format.js";
import { readFile } from "node:fs/promises";
```

## APIs del navegador

**Consulta y navegación del DOM**

```js
const form = document.querySelector("#signup");
const fields = form.querySelectorAll("input");

for (const field of fields) {
  console.log(field.name);
}

console.log(form.parentElement);
```

**Creación y actualización de contenido DOM**

```js
const item = document.createElement("li");
item.className = "todo";
item.textContent = userInput;

list.append(item);
```

**Atributos, clases y data attributes**

```js
button.disabled = true;
button.classList.toggle("is-active", active);
button.dataset.userId = String(user.id);

const label = button.getAttribute("aria-label");
```

**Eventos y delegación**

```js
const controller = new AbortController();

list.addEventListener("click", event => {
  const button = event.target.closest("button[data-id]");
  if (!button) return;

  removeItem(button.dataset.id);
}, { signal: controller.signal });
```

**Formularios y `FormData`**

```js
form.addEventListener("submit", event => {
  if (!form.checkValidity()) {
    event.preventDefault();
    form.reportValidity();
    return;
  }

  const data = new FormData(form);
  console.log(data.get("email"));
});
```

**Fetch y cancelación**

```js
const controller = new AbortController();

const response = await fetch("/api/users", {
  signal: controller.signal,
});

if (!response.ok) {
  throw new Error(`HTTP ${response.status}`);
}

const users = await response.json();
```

**URLs e History**

```js
const url = new URL(location.href);
url.searchParams.set("page", "2");

history.pushState({ page: 2 }, "", url);

addEventListener("popstate", event => {
  console.log(event.state);
});
```

**Storage y Web Workers**

```js
localStorage.setItem("theme", "dark");
const theme = localStorage.getItem("theme");

const worker = new Worker("./worker.js", { type: "module" });
worker.postMessage({ values: largeArray });
```

## Metaprogramación y recursos

**`Proxy` y `Reflect`**

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

**Memoria y garbage collection**

```js
let cache = new Map();

function remember(key, value) {
  cache.set(key, value);
}

function clearCache() {
  cache = new Map();
}
```

**`using` y disposal explícito**

```js
class Lock {
  acquire() {
    console.log("locked");
    return this;
  }

  [Symbol.dispose]() {
    console.log("unlocked");
  }
}

{
  using lock = new Lock().acquire();
  // protected work
}
```

**`await using` y Disposable Stacks**

```js
async function read(openFile) {
  await using file = await openFile();
  return file.read();
}

{
  using stack = new DisposableStack();
  stack.defer(() => console.log("cleanup"));
}
```

## Calidad y mantenibilidad

**Depuración de JavaScript**

```js
function calculateTotal(items) {
  debugger;
  return items.reduce((sum, item) => sum + item.price, 0);
}
```

**Mutación y actualizaciones de estado**

```js
const nextUser = {
  ...user,
  settings: {
    ...user.settings,
    theme: "dark",
  },
};
```

**Fronteras de confianza y seguridad web**

```js
const item = document.createElement("li");
item.textContent = untrustedName;

const response = await fetch("/api/profile", {
  credentials: "same-origin",
});
```
