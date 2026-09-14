# Suspense

`Suspense` coordena UI dependente de async resources. Enquanto data na boundary está pending, Solid mostra fallback e depois revela conteúdo resolvido. Boundaries podem ser aninhadas para partes não relacionadas não esperarem recurso lento.

```tsx
<Suspense fallback={<p>Loading user…</p>}>
  <UserProfile user={user} />
</Suspense>
```

Coloque boundaries em regiões de loading significativas, não em cada text node. Suspense coordena rendering; não decide caching/request policy sozinho. Preserve conteúdo útil quando isso é melhor que trocar área inteira por spinner.
