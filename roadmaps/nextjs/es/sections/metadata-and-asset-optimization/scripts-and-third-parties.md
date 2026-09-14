# Scripts y Código Third-party

`next/script` ofrece loading strategies para que third-party scripts no bloqueen critical path. Dynamic imports/lazy loading también mantienen client libraries costosas fuera del initial bundle hasta que se necesiten.

```tsx
import Script from "next/script";

<Script
  src={process.env.NEXT_PUBLIC_WIDGET_SRC!}
  strategy="lazyOnload"
/>
```

Third-party JS suele ser un gran coste de performance/security. Cárgalo solo donde sea necesario, elige el timing más tardío aceptable, aplica CSP/consent y monitoriza failures porque el código externo cambia independientemente del deployment.
