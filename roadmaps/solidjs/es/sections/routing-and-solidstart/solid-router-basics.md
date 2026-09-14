# Fundamentos de Solid Router

Solid Router mapea URLs a UI y ofrece route state reactivo, navigation, links, nested routes, params y data APIs. Routing es un package separado de Solid core, manteniendo la UI library sin imponer un router.

```tsx
import { Router, Route, A } from "@solidjs/router";

<Router>
  <nav><A href="/about">About</A></nav>
  <Route path="/" component={Home} />
  <Route path="/about" component={About} />
</Router>
```

Trata URL state como input de primera clase. Params/search/history deben vivir en el router en vez de copiarse a signals sin necesidad. Usa links normales para navigation semántica y navigation programática solo cuando el comportamiento lo requiera.
