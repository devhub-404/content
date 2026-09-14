# Directives de Client Hydration

Directives `client:*` dizem quando framework component deve hidratar. `client:load` é imediato, enquanto `client:idle`, `client:visible` e media hydration podem adiar JavaScript até a interação importar.

```astro
<NavMenu client:load />
<Chart client:visible />
<Search client:idle />
<ThemePicker client:media="(max-width: 48rem)" />
```

Escolha o timing mais tardio que ainda atende UX, não `client:load` por hábito. Menu imediato pode carregar cedo; chart below-fold pode esperar visibility. Timing muda quando UI fica interativa, então teste em network lenta.
