# Images y Optimización

El asset pipeline de Astro puede inspeccionar/optimizar imported images, generar dimensions, transformar formats y producir responsive output. Las images en `public` omiten el processing y conservan archivos originales.

```astro
---
import { Image } from "astro:assets";
import hero from "../assets/hero.jpg";
---

<Image src={hero} alt="Mountain at sunrise" width={1200} />
```

Usa alt descriptivo para images significativas y vacío para decorativas. Define dimensions para reducir layout shift, elige source sizes según el layout y evita duplicar optimization cuando un CDN/image service ya controla el pipeline.
