# Lifting e Compartilhamento de State

Quando vários components precisam concordar sobre a mesma informação, mova o state ao owner comum mais próximo e passe values/callbacks para baixo. Isso cria um valor autoritativo em vez de várias cópias que podem divergir.

```jsx
function Accordion() {
  const [openId, setOpenId] = useState(null);

  return items.map(item => (
    <Panel
      key={item.id}
      open={openId === item.id}
      onOpen={() => setOpenId(item.id)}
    />
  ));
}
```

Não levante todo state local para a raiz. State deve viver tão baixo quanto possível, desde que todos os consumers coordenados possam acessá-lo. Isso mantém components reutilizáveis e reduz dependências afetadas por cada update.
