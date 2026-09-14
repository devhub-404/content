# Styles Scoped y Globales

Los styles dentro de un Astro component están scoped por defecto, evitando leak hacia markup no relacionado. Los global styles pueden importarse o marcarse explícitamente para tokens, reset, typography y reglas site-wide.

```astro
<style>
  h2 { color: rebeccapurple; }
</style>

<style is:global>
  :root { font-family: system-ui, sans-serif; }
</style>

<h2>Scoped heading</h2>
```

Usa arquitectura CSS normal en vez de depender del scoping para ocultar selectors malos. Tokens/reglas globales van compartidos; layout/presentation específicos pueden quedar en el component. Specificity/cascade siguen aplicando porque el output es CSS normal.
