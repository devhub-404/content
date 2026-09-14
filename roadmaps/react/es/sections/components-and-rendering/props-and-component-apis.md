# Props y APIs de Components

Las props son los inputs de un component. Son read-only en ese render y pueden contener strings, números, objects, functions, JSX u otros valores. Una buena API hace explícitas las variaciones importantes en vez de leer estado global oculto.

```jsx
function Avatar({ name, size = 48 }) {
  return <img src={`/avatars/${name}.png`} alt={name} width={size} />;
}

<Avatar name="Mina" size={64} />
```

Los valores default ayudan con props opcionales, mientras las object/callback props necesitan ownership claro. No mutes objects recibidos mediante props. Si el parent necesita un cambio, llama un callback o actualiza el estado compartido en su owner.
