# Suspense

`Suspense` coordina UI dependiente de async resources. Mientras los datos dentro de la boundary están pending, Solid muestra fallback y luego revela contenido resuelto. Los boundaries pueden anidarse para que partes no relacionadas no esperen un recurso lento.

```tsx
<Suspense fallback={<p>Loading user…</p>}>
  <UserProfile user={user} />
</Suspense>
```

Coloca boundaries en regiones de loading significativas, no en cada text node. Suspense coordina rendering; no decide caching/request policy por sí solo. Conserva contenido útil cuando sea mejor que reemplazar toda una zona por spinner.
