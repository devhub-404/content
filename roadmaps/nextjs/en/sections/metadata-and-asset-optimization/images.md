# `next/image`

`next/image` provides image sizing, responsive sources, lazy loading, and optimization according to project configuration and deployment support. Static imports can provide dimensions automatically, while remote images require controlled source configuration.

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

Use meaningful alt text, correct responsive `sizes`, and priority only for real above-the-fold critical images. Image optimization cannot compensate for sending unnecessarily huge visuals or using the wrong crop. Configure remote patterns narrowly so the optimizer does not become an unrestricted proxy.
