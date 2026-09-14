# Directives de Client Hydration

Las directives `client:*` indican cuándo un framework component debe hidratarse. `client:load` es inmediato, mientras `client:idle`, `client:visible` y media hydration pueden retrasar JavaScript hasta que la interacción importe.

```astro
<NavMenu client:load />
<Chart client:visible />
<Search client:idle />
<ThemePicker client:media="(max-width: 48rem)" />
```

Elige el timing más tardío que aún cumpla la UX, no `client:load` por costumbre. Un menú inmediato puede cargar pronto; un chart below-fold puede esperar visibility. El timing cambia cuándo la UI se vuelve interactiva, así que prueba con red lenta.
