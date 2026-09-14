# Environment Variables y Secrets

Astro usa env vars estilo Vite en build/server code. Variables marcadas para exposición pública pueden entrar en el client bundle, mientras private server values deben permanecer en paths server-only y secret stores del deployment.

```astro
const publicApi = import.meta.env.PUBLIC_API_BASE;
const privateKey = import.meta.env.SECRET_API_KEY;
```

Estar en `.env` no vuelve secreto un valor si client code lo importa o build lo inlinea en JS enviado. Separa public config de credentials, valida required values temprano y nunca commits production secrets.
