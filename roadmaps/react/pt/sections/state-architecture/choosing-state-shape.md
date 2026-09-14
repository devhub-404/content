# Escolhendo State Shape e Dados Derivados

Bom state armazena o mínimo de informação independente necessário para descrever a UI. Se um valor pode ser calculado de props/state durante render, normalmente calcule-o em vez de armazenar outra cópia sincronizada. Evite state redundante ou contraditório.

```jsx
const [firstName, setFirstName] = useState('Ada');
const [lastName, setLastName] = useState('Lovelace');

const fullName = `${firstName} ${lastName}`;
```

Normalize relações quando vários objects representam a mesma entidade e evite nesting profundo se updates ficarem difíceis. Design de state costuma ser mais importante que hook clever: source of truth clara simplifica updates, debugging, serialization e tests.
