# Route Groups e Private Folders

Parênteses criam route groups que organizam files ou escolhem layouts sem adicionar URL segment. Private folders com underscore saem do routing e ajudam components/tests/modules colocados dentro de `app`.

```tsx
app/
  (marketing)/
    about/page.tsx
    pricing/page.tsx
  (app)/
    dashboard/page.tsx
  _components/
    Logo.tsx
```

Use groups para layout/organização, não para criar routing invisível complexo. Dois groups não podem resolver à mesma URL. Private folders são opcionais porque file só vira route pelas conventions, mas deixam intenção clara.
