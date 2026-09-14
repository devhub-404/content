# Islands Architecture

La islands architecture mantiene la page como HTML server-rendered e hidrata solo components interactivos seleccionados. Cada client island tiene su propia boundary, por lo que un widget no exige runtime JavaScript para toda la page.

```astro
---
import Counter from "../components/Counter.jsx";
---

<h1>Mostly static page</h1>
<Counter client:visible />
```

Elige boundaries según interacción real, no por sección visual. Headings, copy, cards y navigation muchas veces no necesitan hydration. Islands menores reducen JS, pero muchas roots diminutas pueden añadir overhead y dificultar shared client state.
