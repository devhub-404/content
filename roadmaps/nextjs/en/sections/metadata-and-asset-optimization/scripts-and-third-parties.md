# Scripts and Third-party Code

`next/script` provides explicit loading strategies for third-party scripts so analytics, widgets, or external SDKs do not all block the critical page path. Dynamic imports and lazy loading can similarly keep expensive client libraries out of the initial bundle until needed.

```tsx
import Script from "next/script";

<Script
  src={process.env.NEXT_PUBLIC_WIDGET_SRC!}
  strategy="lazyOnload"
/>
```

Third-party JavaScript is often one of the largest performance and security costs on a page. Load it only where needed, choose the latest acceptable timing, apply CSP and consent requirements, and monitor failures because external code can change independently of your deployment.
