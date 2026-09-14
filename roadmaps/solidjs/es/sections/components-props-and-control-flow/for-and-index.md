# List Rendering con `For` e `Index`

`For` mapea list items por identidad y es la opción normal cuando rows representan objects que pueden moverse/insertarse/eliminarse. El item queda estable y el index es un accessor reactivo. `Index` hace key por posición y vuelve reactivo el value.

```tsx
<For each={users()}>
  {(user, index) => (
    <p>{index() + 1}. {user.name}</p>
  )}
</For>
```

Elige según qué sea estable en los datos. Para records con identidad, `For` suele coincidir con el dominio. Para primitives en posiciones fijas con values cambiantes, `Index` puede evitar recreación. No traduzcas keys de React mecánicamente.
