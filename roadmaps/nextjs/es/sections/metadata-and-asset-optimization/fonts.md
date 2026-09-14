# `next/font`

`next/font` integra fonts locales/providers al build, self-hosting files/CSS para evitar runtime request al provider. También ayuda con layout space y loading consistente.

```tsx
import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

export default function RootLayout({ children }) {
  return <html className={inter.className}><body>{children}</body></html>;
}
```

Carga solo families/subsets/styles/weights usados. El framework no vuelve barata una palette excesiva. Define fallbacks, revisa licensing y mide layout/loading real en vez de asumir que la API elimina todo coste.
