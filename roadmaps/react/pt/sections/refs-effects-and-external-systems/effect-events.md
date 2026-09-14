# Effect Events com `useEffectEvent`

`useEffectEvent` permite que um Effect chame lógica que vê os props/state mais recentes sem transformar essa lógica em dependency reativa do próprio Effect. É útil quando subscription externa tem lifecycle estável, mas callback precisa de valores atuais.

```jsx
function ChatRoom({ roomId, theme }) {
  const onConnected = useEffectEvent(() => {
    showToast('Connected', theme);
  });

  useEffect(() => {
    const connection = connect(roomId);
    connection.on('connected', onConnected);
    return () => connection.disconnect();
  }, [roomId]);
}
```

Effect Events são chamados por Effects e não substituem handlers de interação. Use para separar sincronização reativa de callback non-reactive. Não use como truque para esconder dependencies que realmente deveriam ressincronizar o sistema externo.
