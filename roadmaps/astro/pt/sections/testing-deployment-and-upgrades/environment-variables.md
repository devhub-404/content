# Environment Variables e Secrets

Astro usa env vars estilo Vite em build/server code. Variables marcadas para exposição pública podem entrar no client bundle, enquanto private server values devem permanecer em paths server-only e secret stores do deployment.

```astro
const publicApi = import.meta.env.PUBLIC_API_BASE;
const privateKey = import.meta.env.SECRET_API_KEY;
```

Estar em `.env` não torna valor secreto se client code importa ou build inline no JS enviado. Separe public config de credentials, valide required values cedo e nunca commite production secrets.
