# Solid Router Basics

Solid Router maps URLs to UI and provides reactive route state, navigation, links, nested routes, parameters, and data APIs. Routing is a separate package from Solid core, which keeps the UI library usable without prescribing one application router.

```tsx
import { Router, Route, A } from "@solidjs/router";

<Router>
  <nav><A href="/about">About</A></nav>
  <Route path="/" component={Home} />
  <Route path="/about" component={About} />
</Router>
```

Treat URL state as a first-class application input. Parameters, search values, and navigation history should live in the router rather than being copied into unrelated signals without need. Use normal links for navigation semantics and programmatic navigation only when behavior requires it.
