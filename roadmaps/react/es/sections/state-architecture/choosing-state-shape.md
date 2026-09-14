# Eligiendo State Shape y Datos Derivados

Un buen state almacena la mínima información independiente necesaria para describir la UI. Si un valor puede calcularse a partir de props/state durante render, normalmente calcúlalo en vez de guardar otra copia sincronizada. Evita state redundante o contradictorio.

```jsx
const [firstName, setFirstName] = useState('Ada');
const [lastName, setLastName] = useState('Lovelace');

const fullName = `${firstName} ${lastName}`;
```

Normaliza relaciones cuando varios objects representan la misma entidad y evita nesting profundo si los updates se vuelven difíciles. El diseño de state suele importar más que un hook clever: una source of truth clara simplifica updates, debugging, serialization y tests.
