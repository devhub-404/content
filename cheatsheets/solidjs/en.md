---
locale: en
status: published
title: "SolidJS"
slug: solidjs
description: "A task-oriented quick reference for everyday SolidJS syntax, APIs, and workflows."
tags:
  - solidjs
  - cheatsheet
  - quick-reference
references:
  - label: "MDN: Accessibility"
    url: https://developer.mozilla.org/en-US/docs/Web/Accessibility
  - label: "SolidJS Documentation"
    url: https://docs.solidjs.com
  - label: "SolidJS: Fine-grained reactivity"
    url: https://docs.solidjs.com/concepts/intro-to-reactivity
---

# SolidJS

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## Reactivity Model

**Signals**

```tsx
import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);

setCount(1);
setCount(value => value + 1);

console.log(count());
```

**Tracking Scopes and Dependency Graphs**

```tsx
const [price, setPrice] = createSignal(10);
const [quantity, setQuantity] = createSignal(2);

const total = createMemo(() => price() * quantity());

createEffect(() => {
  console.log("total", total());
});
```

## Computations & Derived State

**Derived Values with `createMemo`**

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

const fullName = createMemo(() => `${first()} ${last()}`);

<p>{fullName()}</p>
```

**Effects**

```tsx
const [theme, setTheme] = createSignal("dark");

createEffect(() => {
  document.documentElement.dataset.theme = theme();
});
```

**Batching Updates**

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

batch(() => {
  setFirst("Grace");
  setLast("Hopper");
});
```

**`untrack`, `on`, and Explicit Dependency Control**

```tsx
createEffect(on(userId, id => {
  const themeNow = untrack(theme);
  console.log("user changed", id, themeNow);
}));
```

## Components, Props & Control Flow

**Components and JSX**

```tsx
function Badge(props) {
  return <span class="badge">{props.label}</span>;
}

<Badge label="New" />
```

**Props and Reactive Access**

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Avoid eagerly copying a reactive prop into a plain local value.
```

**Children and the `children` Helper**

```tsx
import { children } from "solid-js";

function Card(props) {
  const content = children(() => props.children);
  return <section class="card">{content()}</section>;
}
```

**Conditional UI with `Show`, `Switch`, and `Match`**

```tsx
<Show when={user()} fallback={<Login />}>
  {current => <Profile user={current()} />}
</Show>

<Switch>
  <Match when={status() === "loading"}>Loading…</Match>
  <Match when={status() === "error"}>Failed</Match>
</Switch>
```

**List Rendering with `For` and `Index`**

```tsx
<For each={users()}>
  {(user, index) => (
    <p>{index() + 1}. {user.name}</p>
  )}
</For>
```

**Dynamic Components and Portals**

```tsx
<Dynamic component={currentView()} user={user()} />

<Portal mount={document.body}>
  <div class="modal">Settings</div>
</Portal>
```

## Stores & Context

**Nested State with `createStore`**

```tsx
import { createStore } from "solid-js/store";

const [state, setState] = createStore({
  user: { name: "Mina", active: false },
  todos: []
});

setState("user", "active", true);
```

**Store Updates, `produce`, and `reconcile`**

```tsx
setState(
  produce(draft => {
    draft.todos.push({ id: 1, title: "Learn Solid" });
  })
);

setState("users", reconcile(serverUsers, { key: "id" }));
```

**Context**

```tsx
const ThemeContext = createContext("light");

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Page />
    </ThemeContext.Provider>
  );
}

const theme = useContext(ThemeContext);
```

**`createMutable` and Mutable-style State**

```tsx
const state = createMutable({ count: 0 });

state.count += 1;
```

## Lifecycle, Ownership & DOM

**`onMount` and `onCleanup`**

```tsx
onMount(() => {
  const controller = connect();
  controller.start();

  onCleanup(() => controller.stop());
});
```

**Reactive Owners and `createRoot`**

```tsx
const dispose = createRoot(dispose => {
  const [count, setCount] = createSignal(0);
  createEffect(() => console.log(count()));
  setCount(1);
  return dispose;
});

dispose();
```

**DOM Refs**

```tsx
function Search() {
  let input;

  onMount(() => input.focus());

  return <input ref={input} />;
}
```

**Events and Event Delegation**

```tsx
function Button() {
  function handleClick(event) {
    console.log(event.currentTarget.name);
  }

  return <button name="save" onClick={handleClick}>Save</button>;
}
```

## Async Data & Boundaries

**Async Data with `createResource`**

```tsx
const [userId, setUserId] = createSignal(1);

const [user] = createResource(userId, async id => {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
});

<Show when={user()}>{value => <h1>{value().name}</h1>}</Show>
```

**Suspense**

```tsx
<Suspense fallback={<p>Loading user…</p>}>
  <UserProfile user={user} />
</Suspense>
```

**Error Boundaries**

```tsx
<ErrorBoundary fallback={(error, reset) => (
  <div>
    <p>{error.message}</p>
    <button onClick={reset}>Try again</button>
  </div>
)}>
  <Dashboard />
</ErrorBoundary>
```

**Transitions and Deferred Values**

```tsx
const [pending, start] = useTransition();

function selectTab(id) {
  start(() => setTab(id));
}

const deferredQuery = createDeferred(query);
```

**Lazy Components**

```tsx
const Settings = lazy(() => import("./Settings"));

<Suspense fallback={<p>Loading…</p>}>
  <Settings />
</Suspense>
```

## Reusable Reactive Primitives

**Custom Reactive Primitives**

```tsx
function createToggle(initial = false) {
  const [value, setValue] = createSignal(initial);
  const toggle = () => setValue(current => !current);
  return [value, toggle];
}

const [open, toggleOpen] = createToggle();
```

**`mergeProps` and `splitProps`**

```tsx
function Button(props) {
  const merged = mergeProps({ type: "button" }, props);
  const [local, rest] = splitProps(merged, ["variant", "children"]);

  return <button {...rest} class={`btn ${local.variant ?? "default"}`}>
    {local.children}
  </button>;
}
```

**Observable Interoperability**

```tsx
const temperature = from(sensorObservable);

createEffect(() => {
  console.log("temperature", temperature());
});
```

**Reactive State Outside Components**

```tsx
const [session, setSession] = createSignal(null);

export function currentSession() {
  return session();
}

export function login(user) {
  setSession(user);
}
```

## Routing & SolidStart

**Solid Router Basics**

```tsx
import { Router, Route, A } from "@solidjs/router";

<Router>
  <nav><A href="/about">About</A></nav>
  <Route path="/" component={Home} />
  <Route path="/about" component={About} />
</Router>
```

**SolidStart File-based Routing**

```tsx
// src/routes/users/[id].tsx
export default function UserPage() {
  const params = useParams();
  return <h1>User {params.id}</h1>;
}
```

**SolidStart Queries and Data Loading**

```tsx
const getPosts = query(async () => {
  "use server";
  return db.posts.findMany();
}, "posts");

export default function Posts() {
  const posts = createAsync(() => getPosts());
  return <For each={posts()}>{post => <p>{post.title}</p>}</For>;
}
```

**Server Functions and Actions**

```tsx
const saveTodo = action(async formData => {
  "use server";
  const title = String(formData.get("title"));
  await db.todos.create({ title });
});

<form action={saveTodo}>
  <input name="title" />
  <button>Add</button>
</form>
```

## SSR, Testing & Production

**SSR and Hydration**

```tsx
import { renderToString } from "solid-js/web";

const html = renderToString(() => <App />);
```

**Testing Solid Components**

```tsx
render(() => <Counter />);

const button = screen.getByRole("button", { name: /count/i });
await userEvent.click(button);

expect(button).toHaveTextContent("1");
```

**DevTools and Reactive Debugging**

```tsx
createEffect(() => {
  console.debug({
    query: query(),
    resultCount: filtered().length
  });
});
```

**Accessibility and Native DOM Semantics**

```tsx
function Dialog(props) {
  return (
    <div role="dialog" aria-modal="true" aria-labelledby="dialog-title">
      <h2 id="dialog-title">{props.title}</h2>
      {props.children}
      <button onClick={props.onClose}>Close</button>
    </div>
  );
}
```
