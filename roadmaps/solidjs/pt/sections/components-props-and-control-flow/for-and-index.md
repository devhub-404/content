# List Rendering com `For` e `Index`

`For` mapeia list items por identidade e é escolha comum quando rows representam objects que podem mover/inserir/remover. Item fica estável e index é accessor reativo. `Index` faz key por posição e torna value reativo.

```tsx
<For each={users()}>
  {(user, index) => (
    <p>{index() + 1}. {user.name}</p>
  )}
</For>
```

Escolha conforme o que é estável nos dados. Para records com identidade, `For` normalmente corresponde ao domínio. Para primitives em posições fixas com values mutáveis, `Index` pode evitar recriação. Não traduza keys de React mecanicamente.
