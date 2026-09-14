# `next/font`

`next/font` integra fonts locais/providers ao build, self-hosting files/CSS para evitar runtime request ao provider. Também ajuda layout space e loading consistente.

```tsx
import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

export default function RootLayout({ children }) {
  return <html className={inter.className}><body>{children}</body></html>;
}
```

Carregue só families/subsets/styles/weights usados. Framework não torna palette excessiva barata. Defina fallbacks, confira licensing e meça layout/loading real em vez de assumir que API remove todo custo.
