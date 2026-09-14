# External Stores con `useSyncExternalStore`

`useSyncExternalStore` es el Hook low-level para suscribir React a state mutable fuera de React. El store proporciona subscribe y snapshot getter para que React lea un valor consistente durante concurrent rendering.

```jsx
function useOnlineStatus() {
  return useSyncExternalStore(
    callback => {
      window.addEventListener('online', callback);
      window.addEventListener('offline', callback);
      return () => {
        window.removeEventListener('online', callback);
        window.removeEventListener('offline', callback);
      };
    },
    () => navigator.onLine
  );
}
```

La mayoría de apps debería consumir un Hook ya ofrecido por la library. Si creas integración, los snapshots deben ser estables cuando el store no cambió, y SSR puede necesitar server snapshot para que hydration empiece con datos coincidentes.
