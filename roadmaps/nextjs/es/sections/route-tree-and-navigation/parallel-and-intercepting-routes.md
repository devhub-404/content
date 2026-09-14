# Parallel e Intercepting Routes

Las parallel routes renderizan named slots en el mismo layout; las intercepting routes renderizan otra route dentro del layout actual. Juntas soportan, por ejemplo, un photo modal en client navigation y standalone page en direct load.

```tsx
app/
  @modal/
    (.)photo/[id]/page.tsx
  photo/[id]/page.tsx
  layout.tsx
```

Son conventions potentes pero complejas. Úsalas para multi-pane/modal routing real donde URL/history importen. Si un simple state toggle basta, es más fácil de entender/testear que filesystem routing avanzado.
