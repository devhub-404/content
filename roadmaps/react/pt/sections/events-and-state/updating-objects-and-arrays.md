# Atualizando Objects e Arrays no State

Objects e arrays armazenados em state devem ser tratados como snapshots imutáveis. Para alterá-los, crie novo object/array reutilizando partes sem mudança e substituindo o necessário. Spread, `map`, `filter` e outras transformações não mutáveis são ferramentas comuns.

```jsx
const [user, setUser] = useState({ name: 'Mina', active: false });

function activate() {
  setUser(current => ({
    ...current,
    active: true
  }));
}
```

Immutability não é regra moral; é parte do modelo de snapshots e identidade do React. Updates profundamente aninhados podem indicar state shape ruim, necessidade de reducer ou helper library quando o domínio realmente exige transforms complexos.
