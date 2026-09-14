# Development, Build e Preview

`astro dev` inicia dev server, `astro build` cria output de produção e `astro preview` serve o build completo localmente. `astro check` executa diagnostics Astro/TypeScript sem produzir deployment.

```astro
{
  "scripts": {
    "dev": "astro dev",
    "build": "astro build",
    "preview": "astro preview",
    "check": "astro check"
  }
}
```

Teste production build antes de publicar porque dev e production podem diferir em routing, adapters, minification, asset paths e runtime. Astro 7 adiciona workflows estruturados/background, mas comandos comuns continuam baseline claro para humanos e CI.
