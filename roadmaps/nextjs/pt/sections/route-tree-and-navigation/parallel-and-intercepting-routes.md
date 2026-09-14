# Parallel e Intercepting Routes

Parallel routes renderizam named slots no mesmo layout; intercepting routes renderizam outra route dentro do layout atual. Juntas suportam, por exemplo, photo modal em client navigation e standalone page no direct load.

```tsx
app/
  @modal/
    (.)photo/[id]/page.tsx
  photo/[id]/page.tsx
  layout.tsx
```

São conventions poderosas mas complexas. Use para multi-pane/modal routing real onde URL/history importa. Se simples state toggle resolve, ele é mais fácil de entender/testar que filesystem routing avançado.
