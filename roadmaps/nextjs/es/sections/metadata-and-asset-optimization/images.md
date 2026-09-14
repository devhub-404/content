# `next/image`

`next/image` ofrece sizing, responsive sources, lazy loading y optimization según config/deployment. Static imports pueden aportar dimensions; remote images necesitan source config controlada.

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

Usa alt adecuado, `sizes` correcto y priority solo para images críticas above-fold. Optimization no compensa visual enorme/crop malo. Configura remote patterns de forma estrecha para no crear un proxy irrestricto.
