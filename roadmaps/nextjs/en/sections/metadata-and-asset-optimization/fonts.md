# `next/font`

`next/font` integrates local and provider fonts into the build, self-hosting generated font files and CSS so the browser does not need a runtime request to the external font provider. It also helps reserve layout space and manage font loading consistently.

```tsx
import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

export default function RootLayout({ children }) {
  return <html className={inter.className}><body>{children}</body></html>;
}
```

Load only families, subsets, styles, and weights the design uses. A framework cannot make an excessive font palette cheap. Define sensible system fallbacks, verify licensing for local files, and measure real layout and loading behavior instead of assuming a font optimization API removes all typography cost.
