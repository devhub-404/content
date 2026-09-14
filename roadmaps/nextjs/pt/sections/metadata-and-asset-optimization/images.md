# `next/image`

`next/image` fornece sizing, responsive sources, lazy loading e optimization conforme config/deployment. Static imports podem fornecer dimensions; remote images precisam source config controlada.

```tsx
import Image from "next/image";
import hero from "./hero.jpg";

<Image
  src={hero}
  alt="Mountain sunrise"
  sizes="(max-width: 768px) 100vw, 50vw"
  priority
/>
```

Use alt adequado, `sizes` correto e priority só para images críticas above-fold. Optimization não compensa visual enorme/crop ruim. Configure remote patterns de forma estreita para não criar proxy irrestrito.
