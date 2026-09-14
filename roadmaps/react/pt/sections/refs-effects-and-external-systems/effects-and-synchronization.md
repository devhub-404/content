# Effects e Sincronização

Effect sincroniza um component renderizado com algo fora do React: subscription, browser API, network connection, imperative library ou outro sistema externo. React roda setup após commit e cleanup antes de ressincronizar ou remover o component.

```jsx
function ChatRoom({ roomId }) {
  useEffect(() => {
    const connection = connect(roomId);
    connection.open();

    return () => connection.close();
  }, [roomId]);

  return <h1>Room {roomId}</h1>;
}
```

Effects não são bucket geral de “depois do render”. Se valor pode ser derivado durante render ou ação vem de um event, use cálculo ou handler. Todo Effect deve ter sistema externo claro e cleanup quando necessário.
