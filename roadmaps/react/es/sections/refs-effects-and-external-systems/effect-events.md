# Effect Events con `useEffectEvent`

`useEffectEvent` permite que un Effect llame lógica que ve los props/state más recientes sin convertir esa lógica en dependency reactiva del propio Effect. Es útil cuando una subscription externa tiene lifecycle estable pero su callback necesita valores actuales.

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

Los Effect Events se llaman desde Effects y no sustituyen handlers de interacción. Úsalos para separar sincronización reactiva de callback non-reactive. No los uses como truco para ocultar dependencies que realmente deberían resincronizar el sistema externo.
