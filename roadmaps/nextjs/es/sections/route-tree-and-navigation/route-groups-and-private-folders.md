# Route Groups y Private Folders

Los paréntesis crean route groups que organizan files o seleccionan layouts sin añadir un URL segment. Las private folders con underscore salen del routing y ayudan con components/tests/modules colocados dentro de `app`.

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

Usa groups para layout/organización, no para crear routing invisible complejo. Dos groups no pueden resolver a la misma URL. Las private folders son opcionales porque un file solo se vuelve route mediante conventions, pero hacen explícita la intención.
