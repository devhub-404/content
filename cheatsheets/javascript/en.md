---
locale: en
status: published
title: "JavaScript"
slug: javascript
description: "A task-oriented quick reference for everyday JavaScript syntax, APIs, and workflows."
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

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## Language & Execution

**JavaScript and Runtimes**

```js
const total = 2 + 3;
console.log(total);
```

**Scripts, Modules, and Strict Mode**

```html
<script src="/legacy.js" defer></script>
<script type="module" src="/app.js"></script>
```

**Statements, Expressions, and Comments**

```js
const price = 12;
const total = price * 3;

if (total > 30) {
  console.log("Large order");
}
```

**`let`, `const`, and `var`**

```js
const taxRate = 0.2;
let total = 100;
total += total * taxRate;

if (total > 100) {
  const message = "Large total";
  console.log(message);
}
```

## Values, Types & Operators

**Primitive Types**

```js
const name = "Mina";       // string
const count = 42;          // number
const exact = 42n;         // bigint
const active = true;       // boolean
const missing = undefined;
const empty = null;
const key = Symbol("key");
```

**Numbers, BigInt, and Math**

```js
const average = (10 + 15 + 20) / 3;
const rounded = Math.round(average);
const safe = Number.isFinite(rounded);

const huge = 9_007_199_254_740_993n;
```

**Strings and Template Literals**

```js
const first = "Ada";
const last = "Lovelace";
const label = `${first} ${last}`;

const message = `Hello,
${label}!`;
```

**Truthiness, Nullish Values, and Coercion**

```js
const input = "";
if (!input) {
  console.log("No input");
}

const page = settings.page ?? 1;
const count = Number("42");
```

**Equality and Comparison**

```js
0 === false;          // false
0 == false;           // true
Object.is(NaN, NaN);  // true

const sameUser = a.id === b.id;
```

**Operators, Short-circuiting, and Optional Chaining**

```js
const canEdit = signedIn && permissions.includes("edit");
const label = compact ? "Save" : "Save changes";
const city = user.address?.city ?? "Unknown";

settings.theme ??= "system";
```

## Control Flow & Errors

**Conditionals**

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

**Loops and Iteration Statements**

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

**Exceptions**

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

**Program Invariants and Validation**

```js
function transfer(amount) {
  if (!Number.isFinite(amount) || amount <= 0) {
    throw new RangeError("amount must be a positive finite number");
  }

  // Later code can rely on the invariant.
}
```

## Functions, Scope & Closures

**Functions and Return Values**

```js
function add(a, b) {
  return a + b;
}

const multiply = function (a, b) {
  return a * b;
};
```

**Parameters, Defaults, and Rest**

```js
function format(name, prefix = "User", ...tags) {
  return `${prefix}: ${name} [${tags.join(", ")}]`;
}

format("Mina", undefined, "admin", "active");
```

**Arrow Functions and Lexical `this`**

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

**Lexical Scope and Closures**

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

**Callbacks and Higher-order Functions**

```js
function repeat(times, action) {
  for (let i = 0; i < times; i++) {
    action(i);
  }
}

repeat(3, index => console.log(index));
```

**Recursion**

```js
function factorial(n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}
```

## Objects, Prototypes & Classes

**Objects and Properties**

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

**Object Spread and Destructuring**

```js
const user = { name: "Mina", role: "admin" };
const updated = { ...user, role: "editor" };

const {
  name: displayName,
  role = "guest",
} = updated;
```

**Methods, `this`, `bind`, `call`, and `apply`**

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

**The Prototype Chain**

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

**Classes and Private Fields**

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

**Inheritance and Static Members**

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

**Property Descriptors and Accessors**

```js
const user = {};

Object.defineProperty(user, "id", {
  value: 42,
  writable: false,
  enumerable: true,
  configurable: false,
});
```

## Arrays & Collections

**Array Basics**

```js
const items = ["a", "b", "c"];
items.push("d");

console.log(items[0]);
console.log(items.at(-1));
console.log(items.length);
```

**Transforming, Searching, and Reducing Arrays**

```js
const activeNames = users
  .filter(user => user.active)
  .map(user => user.name);

const admin = users.find(user => user.role === "admin");
const allValid = users.every(user => user.name.length > 0);
const total = prices.reduce((sum, price) => sum + price, 0);
```

**Copying and Sorting Arrays**

```js
const sorted = users.toSorted((a, b) =>
  a.name.localeCompare(b.name)
);

const reversed = items.toReversed();
const updated = items.with(1, "new value");
const removed = items.toSpliced(2, 1);
```

**Array Destructuring and Spread**

```js
const [first, second, ...rest] = items;
const copy = [...items];
const combined = [...left, ...right];

function point([x, y]) {
  return { x, y };
}
```

**`Map` and `Set`**

```js
const visits = new Map();
visits.set(user, 3);

const tags = new Set(["js", "web", "js"]);
tags.add("css");

console.log(tags.size);
```

**Weak Collections**

```js
const metadata = new WeakMap();

function attachMetadata(element, data) {
  metadata.set(element, data);
}

function getMetadata(element) {
  return metadata.get(element);
}
```

**Typed Arrays and Binary Data**

```js
const buffer = new ArrayBuffer(8);
const bytes = new Uint8Array(buffer);
const numbers = new Uint32Array(buffer);

bytes[0] = 255;
console.log(numbers[0]);
```

## Built-ins & Language Protocols

**JSON**

```js
const text = JSON.stringify({
  id: 42,
  active: true,
});

const value = JSON.parse(text);
```

**Dates and Internationalization**

```js
const deadline = new Date("2026-12-01T15:00:00Z");

const formatter = new Intl.DateTimeFormat("pt-BR", {
  dateStyle: "long",
  timeStyle: "short",
  timeZone: "America/Sao_Paulo",
});

console.log(formatter.format(deadline));
```

**Regular Expressions**

```js
const pattern = /^(?<user>[a-z0-9._-]+)@(?<host>[a-z0-9.-]+)$/i;
const match = pattern.exec("mina@example.com");

if (match) {
  console.log(match.groups.user);
}
```

**Iterables and Iterators**

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

**Generators and Async Generators**

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

**Symbols and Protocol Hooks**

```js
const internalId = Symbol("internalId");

const record = {
  [internalId]: 42,
  [Symbol.toStringTag]: "Record",
};
```

## Asynchronous JavaScript

**Event Loop, Tasks, and Microtasks**

```js
console.log("A");

queueMicrotask(() => console.log("microtask"));
setTimeout(() => console.log("timer"), 0);

console.log("B");
```

**Promises and Chaining**

```js
loadUser()
  .then(user => loadOrders(user.id))
  .then(orders => renderOrders(orders))
  .catch(error => showError(error))
  .finally(() => stopSpinner());
```

**Promise Composition**

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

**`async` and `await`**

```js
async function loadDashboard() {
  const response = await fetch("/api/dashboard");

  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }

  return response.json();
}
```

**Async Iteration**

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

## Modules

**Imports and Exports**

```js
// math.js
export const PI = Math.PI;
export function area(radius) {
  return PI * radius ** 2;
}

// app.js
import { PI, area as circleArea } from "./math.js";
```

**Re-exports and Cycles**

```js
// public-api.js
export { createUser } from "./create-user.js";
export { validateUser } from "./validate-user.js";
export { UserError } from "./errors.js";
```

**Dynamic Import and Top-level `await`**

```js
async function openEditor() {
  const { createEditor } = await import("./editor.js");
  return createEditor();
}

// module top level
const config = await loadConfig();
```

**Module Resolution by the Host**

```js
import { format } from "./format.js";
import { readFile } from "node:fs/promises";
```

## Browser APIs

**DOM Querying and Traversal**

```js
const form = document.querySelector("#signup");
const fields = form.querySelectorAll("input");

for (const field of fields) {
  console.log(field.name);
}

console.log(form.parentElement);
```

**Creating and Updating DOM Content**

```js
const item = document.createElement("li");
item.className = "todo";
item.textContent = userInput;

list.append(item);
```

**Attributes, Classes, and Data Attributes**

```js
button.disabled = true;
button.classList.toggle("is-active", active);
button.dataset.userId = String(user.id);

const label = button.getAttribute("aria-label");
```

**Events and Delegation**

```js
const controller = new AbortController();

list.addEventListener("click", event => {
  const button = event.target.closest("button[data-id]");
  if (!button) return;

  removeItem(button.dataset.id);
}, { signal: controller.signal });
```

**Forms and `FormData`**

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

**Fetch and Cancellation**

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

**URLs and History**

```js
const url = new URL(location.href);
url.searchParams.set("page", "2");

history.pushState({ page: 2 }, "", url);

addEventListener("popstate", event => {
  console.log(event.state);
});
```

**Storage and Web Workers**

```js
localStorage.setItem("theme", "dark");
const theme = localStorage.getItem("theme");

const worker = new Worker("./worker.js", { type: "module" });
worker.postMessage({ values: largeArray });
```

## Metaprogramming & Resources

**`Proxy` and `Reflect`**

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

**Memory and Garbage Collection**

```js
let cache = new Map();

function remember(key, value) {
  cache.set(key, value);
}

function clearCache() {
  cache = new Map();
}
```

**`using` and Explicit Disposal**

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

**`await using` and Disposable Stacks**

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

## Quality & Maintainability

**Debugging JavaScript**

```js
function calculateTotal(items) {
  debugger;
  return items.reduce((sum, item) => sum + item.price, 0);
}
```

**Mutation and State Updates**

```js
const nextUser = {
  ...user,
  settings: {
    ...user.settings,
    theme: "dark",
  },
};
```

**Trust Boundaries and Web Security**

```js
const item = document.createElement("li");
item.textContent = untrustedName;

const response = await fetch("/api/profile", {
  credentials: "same-origin",
});
```
