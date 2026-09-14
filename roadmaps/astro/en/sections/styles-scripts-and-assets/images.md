# Images and Image Optimization

Astro's asset pipeline can inspect and optimize imported images, generate dimensions, transform formats, and produce responsive output depending on the image API and configuration. Images in `public` bypass this processing and keep their original files.

```astro
---
import { Image } from "astro:assets";
import hero from "../assets/hero.jpg";
---

<Image src={hero} alt="Mountain at sunrise" width={1200} />
```

Use descriptive alt text for meaningful images and empty alt for decorative images. Define dimensions to reduce layout shift, choose responsive source sizes based on actual layout, and avoid optimizing an asset repeatedly when a CDN or external image service already owns the transformation pipeline.
