---
locale: es
status: published
title: "React"
slug: react
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de React."
tags:
  - react
  - cheatsheet
  - quick-reference
references:
  - label: "MDN: Accessibility"
    url: https://developer.mozilla.org/en-US/docs/Web/Accessibility
  - label: "React: Quick Start"
    url: https://react.dev/learn
  - label: "React: Writing Markup with JSX"
    url: https://react.dev/learn/writing-markup-with-jsx
---

# React

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Components y Rendering

**Components, JSX y Expressions**

```jsx
function Greeting({ name }) {
  const message = `Hello, ${name}`;
  return <h1 className="greeting">{message}</h1>;
}
```

**Props y APIs de Components**

```jsx
function Avatar({ name, size = 48 }) {
  return <img src={`/avatars/${name}.png`} alt={name} width={size} />;
}

<Avatar name="Mina" size={64} />
```

**Children, Fragments y Composition**

```jsx
function Card({ title, children }) {
  return (
    <section className="card">
      <h2>{title}</h2>
      {children}
    </section>
  );
}
```

**Conditional Rendering y Lists**

```jsx
function TodoList({ todos }) {
  if (todos.length === 0) return <p>No tasks.</p>;

  return (
    <ul>
      {todos.map(todo => <li key={todo.id}>{todo.title}</li>)}
    </ul>
  );
}
```

**Rendering Puro y Commit Phase**

```jsx
function Price({ amount }) {
  const formatted = new Intl.NumberFormat('en', {
    style: 'currency',
    currency: 'USD'
  }).format(amount);

  return <span>{formatted}</span>;
}
```

## Events y State

**Event Handlers**

```jsx
function SaveButton({ onSave }) {
  function handleClick(event) {
    event.preventDefault();
    onSave();
  }

  return <button onClick={handleClick}>Save</button>;
}
```

**State como Snapshot**

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

**State Updates, Batching y Updater Functions**

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  function addThree() {
    setCount(c => c + 1);
    setCount(c => c + 1);
    setCount(c => c + 1);
  }

  return <button onClick={addThree}>{count}</button>;
}
```

**Actualizando Objects y Arrays en State**

```jsx
const [user, setUser] = useState({ name: 'Mina', active: false });

function activate() {
  setUser(current => ({
    ...current,
    active: true
  }));
}
```

**Inputs Controlados y Forms**

```jsx
function SearchBox() {
  const [query, setQuery] = useState('');

  return (
    <label>
      Search
      <input value={query} onChange={e => setQuery(e.target.value)} />
    </label>
  );
}
```

## Arquitectura de State

**Lifting y Compartir State**

```jsx
function Accordion() {
  const [openId, setOpenId] = useState(null);

  return items.map(item => (
    <Panel
      key={item.id}
      open={openId === item.id}
      onOpen={() => setOpenId(item.id)}
    />
  ));
}
```

**Eligiendo State Shape y Datos Derivados**

```jsx
const [firstName, setFirstName] = useState('Ada');
const [lastName, setLastName] = useState('Lovelace');

const fullName = `${firstName} ${lastName}`;
```

**Reducers para Transiciones Complejas de State**

```jsx
function reducer(state, action) {
  switch (action.type) {
    case 'added':
      return [...state, action.todo];
    case 'removed':
      return state.filter(todo => todo.id !== action.id);
    default:
      return state;
  }
}

const [todos, dispatch] = useReducer(reducer, []);
```

**Context para Valores Transversales**

```jsx
const ThemeContext = createContext('light');

function App() {
  return (
    <ThemeContext value="dark">
      <Toolbar />
    </ThemeContext>
  );
}

function Button() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Save</button>;
}
```

**Reducers con Context**

```jsx
const TodosContext = createContext(null);
const TodosDispatchContext = createContext(null);

function TodosProvider({ children }) {
  const [todos, dispatch] = useReducer(todosReducer, []);
  return (
    <TodosContext value={todos}>
      <TodosDispatchContext value={dispatch}>{children}</TodosDispatchContext>
    </TodosContext>
  );
}
```

## Refs, Effects y Sistemas Externos

**Refs como Memoria de Instancia**

```jsx
function Stopwatch() {
  const intervalRef = useRef(null);

  function start() {
    intervalRef.current = setInterval(() => {}, 1000);
  }

  function stop() {
    clearInterval(intervalRef.current);
  }

  return <button onClick={start}>Start</button>;
}
```

**DOM Refs y Acciones Imperativas**

```jsx
function Search() {
  const inputRef = useRef(null);

  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current?.focus()}>
        Focus
      </button>
    </>
  );
}
```

**Effects y Sincronización**

```jsx
function ChatRoom({ roomId }) {
  useEffect(() => {
    const connection = connect(roomId);
    connection.open();

    return () => connection.close();
  }, [roomId]);

  return <h1>Room {roomId}</h1>;
}
```

**Dependencies y Cleanup de Effects**

```jsx
useEffect(() => {
  const controller = new AbortController();

  fetch(`/api/users/${userId}`, { signal: controller.signal })
    .then(response => response.json())
    .then(setUser);

  return () => controller.abort();
}, [userId]);
```

**Effect Events con `useEffectEvent`**

```jsx
function ChatRoom({ roomId, theme }) {
  const onConnected = useEffectEvent(() => {
    showToast('Connected', theme);
  });

  useEffect(() => {
    const connection = connect(roomId);
    connection.on('connected', onConnected);
    return () => connection.disconnect();
  }, [roomId]);
}
```

**Custom Hooks y Lógica Stateful Reutilizable**

```jsx
function useOnlineStatus() {
  const [online, setOnline] = useState(navigator.onLine);

  useEffect(() => {
    const update = () => setOnline(navigator.onLine);
    window.addEventListener('online', update);
    window.addEventListener('offline', update);
    return () => {
      window.removeEventListener('online', update);
      window.removeEventListener('offline', update);
    };
  }, []);

  return online;
}
```

## Concurrencia y Performance

**Memoization con `memo`, `useMemo` y `useCallback`**

```jsx
const FilteredList = memo(function FilteredList({ items, query }) {
  const visible = useMemo(
    () => items.filter(item => item.name.includes(query)),
    [items, query]
  );

  return visible.map(item => <p key={item.id}>{item.name}</p>);
});
```

**Transitions con `useTransition`**

```jsx
function SearchPage() {
  const [query, setQuery] = useState('');
  const [filter, setFilter] = useState('');
  const [isPending, startTransition] = useTransition();

  function update(value) {
    setQuery(value);
    startTransition(() => setFilter(value));
  }
}
```

**Deferred Values**

```jsx
function Results({ query }) {
  const deferredQuery = useDeferredValue(query);
  const stale = query !== deferredQuery;

  return <SearchResults query={deferredQuery} dimmed={stale} />;
}
```

**Suspense y Lazy Loading**

```jsx
const Settings = lazy(() => import('./Settings.jsx'));

function App() {
  return (
    <Suspense fallback={<p>Loading settings…</p>}>
      <Settings />
    </Suspense>
  );
}
```

**Preservando UI Oculta con `<Activity>`**

```jsx
function Tabs({ active }) {
  return (
    <>
      <Activity mode={active === 'feed' ? 'visible' : 'hidden'}>
        <Feed />
      </Activity>
      <Activity mode={active === 'messages' ? 'visible' : 'hidden'}>
        <Messages />
      </Activity>
    </>
  );
}
```

**React View Transitions**

```jsx
function Profile({ user }) {
  return (
    <ViewTransition name={`avatar-${user.id}`}>
      <img src={user.avatar} alt="" />
    </ViewTransition>
  );
}
```

## Forms y Actions

**Form Actions**

```jsx
async function saveProfile(formData) {
  const name = formData.get('name');
  await updateProfile({ name });
}

function ProfileForm() {
  return (
    <form action={saveProfile}>
      <input name="name" />
      <button>Save</button>
    </form>
  );
}
```

**Action State con `useActionState`**

```jsx
function Signup() {
  const [state, submit, pending] = useActionState(registerUser, { error: null });

  return (
    <form action={submit}>
      <input name="email" type="email" />
      <button disabled={pending}>Create account</button>
      {state.error && <p>{state.error}</p>}
    </form>
  );
}
```

**UI de Submission con `useFormStatus`**

```jsx
function SubmitButton() {
  const { pending } = useFormStatus();
  return <button disabled={pending}>{pending ? 'Saving…' : 'Save'}</button>;
}

function Form() {
  return <form action={save}><SubmitButton /></form>;
}
```

**State Optimista con `useOptimistic`**

```jsx
const [optimisticTodos, addOptimisticTodo] = useOptimistic(
  todos,
  (current, title) => [...current, { id: 'pending', title }]
);

async function addTodo(formData) {
  const title = formData.get('title');
  addOptimisticTodo(title);
  await createTodo(title);
}
```

## APIs Avanzadas de Components

**Portals**

```jsx
function Modal({ children }) {
  return createPortal(
    <div role="dialog" aria-modal="true">{children}</div>,
    document.body
  );
}
```

**Error Boundaries**

```jsx
class ErrorBoundary extends React.Component {
  state = { failed: false };

  static getDerivedStateFromError() {
    return { failed: true };
  }

  render() {
    return this.state.failed ? <p>Something went wrong.</p> : this.props.children;
  }
}
```

**Fragment Refs**

```jsx
function Toolbar() {
  const fragmentRef = useRef(null);

  return (
    <Fragment ref={fragmentRef}>
      <button>Cut</button>
      <button>Copy</button>
      <button>Paste</button>
    </Fragment>
  );
}
```

**External Stores con `useSyncExternalStore`**

```jsx
function useOnlineStatus() {
  return useSyncExternalStore(
    callback => {
      window.addEventListener('online', callback);
      window.addEventListener('offline', callback);
      return () => {
        window.removeEventListener('online', callback);
        window.removeEventListener('offline', callback);
      };
    },
    () => navigator.onLine
  );
}
```

## Server Rendering y React Server Components

**Client Roots y Hydration**

```jsx
import { createRoot } from 'react-dom/client';
import App from './App.jsx';

createRoot(document.getElementById('root')).render(<App />);
```

**Server Rendering con Streaming**

```jsx
const stream = await renderToReadableStream(
  <App />,
  { onError(error) { console.error(error); } }
);

return new Response(stream, {
  headers: { 'Content-Type': 'text/html' }
});
```

**React Server Components**

```jsx
async function Note({ id }) {
  const note = await db.notes.get(id);
  return <article>{note.body}</article>;
}
```

**Boundaries entre Server y Client Components**

```jsx
// Counter.jsx
'use client';

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

**Server Functions**

```jsx
// actions.js
'use server';

export async function renameUser(formData) {
  const name = formData.get('name');
  await db.users.rename(name);
}
```

## Tooling, Testing y Producción

**Strict Mode**

```jsx
createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

**React DevTools y Profiling**

```jsx
<Profiler id="SearchResults" onRender={onRender}>
  <SearchResults query={query} />
</Profiler>
```

**Probando Components por Comportamiento**

```jsx
render(<LoginForm />);

await user.type(screen.getByLabelText(/email/i), 'mina@example.com');
await user.click(screen.getByRole('button', { name: /sign in/i }));

expect(await screen.findByText(/welcome/i)).toBeVisible();
```

**Accesibilidad y Semántica del DOM**

```jsx
function Menu() {
  return (
    <nav aria-label="Account">
      <ul>
        <li><a href="/profile">Profile</a></li>
        <li><button type="button">Sign out</button></li>
      </ul>
    </nav>
  );
}
```

**React Compiler y Memoization Automática**

```jsx
// Ordinary component code; the compiler can optimize supported patterns.
function ProductList({ products, query }) {
  const visible = products.filter(product => product.name.includes(query));
  return visible.map(product => <Product key={product.id} product={product} />);
}
```
