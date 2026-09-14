# Islands Architecture

Astro's island architecture keeps the page as server-rendered HTML and hydrates only selected interactive components. Each client island has its own hydration boundary, so one widget does not require a page-wide JavaScript application runtime.

```astro
---
import Counter from "../components/Counter.jsx";
---

<h1>Mostly static page</h1>
<Counter client:visible />
```

Choose island boundaries around actual interaction, not visual sections. Static headings, article copy, cards, and navigation often need no hydration. Smaller client islands reduce shipped code, but too many tiny framework roots can add overhead and make shared client state harder to coordinate.
