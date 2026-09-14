# Effect Events with `useEffectEvent`

`useEffectEvent` lets an Effect call logic that should see the latest props or state without making that logic a reactive dependency of the Effect itself. It is useful when one external subscription has a stable lifecycle but its callback needs current application values.

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

Effect Events are called from Effects and are not a replacement for ordinary user event handlers. Use them to separate reactive synchronization from non-reactive callback logic. Do not use them as a trick to hide dependencies that should genuinely cause the external system to resynchronize.
