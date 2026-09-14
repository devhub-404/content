# Styles Scoped e Globais

Styles dentro de Astro component são scoped por default, evitando leak para markup não relacionado. Global styles podem ser importados ou marcados explicitamente para tokens, reset, typography e regras site-wide.

```astro
<style>
  h2 { color: rebeccapurple; }
</style>

<style is:global>
  :root { font-family: system-ui, sans-serif; }
</style>

<h2>Scoped heading</h2>
```

Use arquitetura CSS normal em vez de depender de scoping para esconder selectors ruins. Tokens/regras globais ficam shared; layout/presentation específicos podem ficar no component. Specificity/cascade continuam valendo porque output é CSS comum.
