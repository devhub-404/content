# Images e Otimização

Asset pipeline do Astro pode inspecionar/otimizar imported images, gerar dimensions, transformar formats e produzir responsive output. Images em `public` ignoram processing e mantêm arquivos originais.

```astro
---
import { Image } from "astro:assets";
import hero from "../assets/hero.jpg";
---

<Image src={hero} alt="Mountain at sunrise" width={1200} />
```

Use alt descritivo para images significativas e vazio para decorativas. Defina dimensions para reduzir layout shift, escolha source sizes pelo layout e evite duplicar optimization quando CDN/image service já controla pipeline.
