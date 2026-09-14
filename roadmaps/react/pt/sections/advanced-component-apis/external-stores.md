# External Stores com `useSyncExternalStore`

`useSyncExternalStore` é Hook low-level para assinar state mutável fora do React. O store fornece subscribe e snapshot getter para React ler valor consistente durante concurrent rendering.

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

A maioria dos apps deve consumir Hook já fornecido pela library. Se criar integração, snapshots precisam ser estáveis quando store não mudou, e SSR pode precisar server snapshot para hydration começar com dados correspondentes.
