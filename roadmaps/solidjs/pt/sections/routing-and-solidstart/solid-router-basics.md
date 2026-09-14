# Fundamentos do Solid Router

Solid Router mapeia URLs para UI e fornece route state reativo, navigation, links, nested routes, params e data APIs. Routing é package separado do Solid core, mantendo library de UI sem router obrigatório.

```tsx
import { Router, Route, A } from "@solidjs/router";

<Router>
  <nav><A href="/about">About</A></nav>
  <Route path="/" component={Home} />
  <Route path="/about" component={About} />
</Router>
```

Trate URL state como input de primeira classe. Params/search/history devem viver no router em vez de serem copiados para signals sem necessidade. Use links normais para navigation semântica e navigation programática só quando comportamento exigir.
