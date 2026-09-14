# Scripts e Código Third-party

`next/script` fornece loading strategies para third-party scripts não bloquearem critical path. Dynamic imports/lazy loading também mantêm client libraries caras fora do initial bundle até necessidade.

```tsx
import Script from "next/script";

<Script
  src={process.env.NEXT_PUBLIC_WIDGET_SRC!}
  strategy="lazyOnload"
/>
```

Third-party JS costuma ser grande custo de performance/security. Carregue apenas onde necessário, escolha timing mais tardio aceitável, aplique CSP/consent e monitore failures porque código externo muda independente do deployment.
