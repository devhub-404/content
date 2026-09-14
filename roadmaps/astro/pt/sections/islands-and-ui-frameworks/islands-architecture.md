# Islands Architecture

Island architecture mantém page como HTML server-rendered e hidrata apenas components interativos selecionados. Cada client island possui boundary própria, então um widget não exige runtime JavaScript para page inteira.

```astro
---
import Counter from "../components/Counter.jsx";
---

<h1>Mostly static page</h1>
<Counter client:visible />
```

Escolha boundaries pela interação real, não por seção visual. Headings, copy, cards e navigation muitas vezes não precisam hydration. Islands menores reduzem JS, mas muitas roots minúsculas podem adicionar overhead e dificultar shared client state.
