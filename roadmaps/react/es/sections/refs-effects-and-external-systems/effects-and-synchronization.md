# Effects y Sincronización

Un Effect sincroniza un component renderizado con algo fuera de React: subscription, browser API, network connection, imperative library u otro sistema externo. React ejecuta setup después del commit y cleanup antes de resincronizar o quitar el component.

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

Los Effects no son un bucket general de “después del render”. Si un valor puede derivarse durante render o una acción proviene de un event, usa cálculo o handler. Todo Effect debe tener un sistema externo claro y cleanup cuando corresponda.
