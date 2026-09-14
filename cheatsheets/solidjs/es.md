---
locale: es
status: published
title: "SolidJS"
slug: solidjs
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de SolidJS."
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

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Modelo de Reactividad

**Signals**

```tsx
import { createSignal } from "solid-js";

const [count, setCount] = createSignal(0);

setCount(1);
setCount(value => value + 1);

console.log(count());
```

**Tracking Scopes y Dependency Graphs**

```tsx
const [price, setPrice] = createSignal(10);
const [quantity, setQuantity] = createSignal(2);

const total = createMemo(() => price() * quantity());

createEffect(() => {
  console.log("total", total());
});
```

## Computations y State Derivado

**Valores Derivados con `createMemo`**

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

**Batching de Updates**

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

batch(() => {
  setFirst("Grace");
  setLast("Hopper");
});
```

**`untrack`, `on` y Control Explícito de Dependencies**

```tsx
createEffect(on(userId, id => {
  const themeNow = untrack(theme);
  console.log("user changed", id, themeNow);
}));
```

## Components, Props y Control Flow

**Components y JSX**

```tsx
function Badge(props) {
  return <span class="badge">{props.label}</span>;
}

<Badge label="New" />
```

**Props y Acceso Reactivo**

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Avoid eagerly copying a reactive prop into a plain local value.
```

**Children y Helper `children`**

```tsx
import { children } from "solid-js";

function Card(props) {
  const content = children(() => props.children);
  return <section class="card">{content()}</section>;
}
```

**UI Condicional con `Show`, `Switch` y `Match`**

```tsx
<Show when={user()} fallback={<Login />}>
  {current => <Profile user={current()} />}
</Show>

<Switch>
  <Match when={status() === "loading"}>Loading…</Match>
  <Match when={status() === "error"}>Failed</Match>
</Switch>
```

**List Rendering con `For` e `Index`**

```tsx
<For each={users()}>
  {(user, index) => (
    <p>{index() + 1}. {user.name}</p>
  )}
</For>
```

**Dynamic Components y Portals**

```tsx
<Dynamic component={currentView()} user={user()} />

<Portal mount={document.body}>
  <div class="modal">Settings</div>
</Portal>
```

## Stores y Context

**State Anidado con `createStore`**

```tsx
import { createStore } from "solid-js/store";

const [state, setState] = createStore({
  user: { name: "Mina", active: false },
  todos: []
});

setState("user", "active", true);
```

**Store Updates, `produce` y `reconcile`**

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

**`createMutable` y State Mutation-style**

```tsx
const state = createMutable({ count: 0 });

state.count += 1;
```

## Lifecycle, Ownership y DOM

**`onMount` y `onCleanup`**

```tsx
onMount(() => {
  const controller = connect();
  controller.start();

  onCleanup(() => controller.stop());
});
```

**Reactive Owners y `createRoot`**

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

**Events y Event Delegation**

```tsx
function Button() {
  function handleClick(event) {
    console.log(event.currentTarget.name);
  }

  return <button name="save" onClick={handleClick}>Save</button>;
}
```

## Datos Async y Boundaries

**Datos Async con `createResource`**

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

**Transitions y Deferred Values**

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

## Primitives Reactivas Reutilizables

**Primitives Reactivas Personalizadas**

```tsx
function createToggle(initial = false) {
  const [value, setValue] = createSignal(initial);
  const toggle = () => setValue(current => !current);
  return [value, toggle];
}

const [open, toggleOpen] = createToggle();
```

**`mergeProps` y `splitProps`**

```tsx
function Button(props) {
  const merged = mergeProps({ type: "button" }, props);
  const [local, rest] = splitProps(merged, ["variant", "children"]);

  return <button {...rest} class={`btn ${local.variant ?? "default"}`}>
    {local.children}
  </button>;
}
```

**Interop con Observables**

```tsx
const temperature = from(sensorObservable);

createEffect(() => {
  console.log("temperature", temperature());
});
```

**Reactive State Fuera de Components**

```tsx
const [session, setSession] = createSignal(null);

export function currentSession() {
  return session();
}

export function login(user) {
  setSession(user);
}
```

## Routing y SolidStart

**Fundamentos de Solid Router**

```tsx
import { Router, Route, A } from "@solidjs/router";

<Router>
  <nav><A href="/about">About</A></nav>
  <Route path="/" component={Home} />
  <Route path="/about" component={About} />
</Router>
```

**File-based Routing en SolidStart**

```tsx
// src/routes/users/[id].tsx
export default function UserPage() {
  const params = useParams();
  return <h1>User {params.id}</h1>;
}
```

**Queries y Data Loading en SolidStart**

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

**Server Functions y Actions**

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

## SSR, Testing y Producción

**SSR y Hydration**

```tsx
import { renderToString } from "solid-js/web";

const html = renderToString(() => <App />);
```

**Probando Solid Components**

```tsx
render(() => <Counter />);

const button = screen.getByRole("button", { name: /count/i });
await userEvent.click(button);

expect(button).toHaveTextContent("1");
```

**DevTools y Debugging Reactivo**

```tsx
createEffect(() => {
  console.debug({
    query: query(),
    resultCount: filtered().length
  });
});
```

**Accesibilidad y Semántica Nativa del DOM**

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
