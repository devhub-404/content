# Props e APIs de Components

Props são os inputs de um component. Elas são read-only naquele render e podem conter strings, números, objects, functions, JSX ou outros valores. Uma boa API torna variações importantes explícitas em vez de ler estado global escondido.

```jsx
function Avatar({ name, size = 48 }) {
  return <img src={`/avatars/${name}.png`} alt={name} width={size} />;
}

<Avatar name="Mina" size={64} />
```

Valores default ajudam em props opcionais, enquanto object/callback props precisam de ownership claro. Não mute objects recebidos via props. Se o parent precisa de mudança, chame callback ou atualize o estado compartilhado no owner.
