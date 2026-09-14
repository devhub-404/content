# External Stores with `useSyncExternalStore`

`useSyncExternalStore` is the low-level Hook for subscribing React to mutable state that lives outside React. A store provides a subscribe function and a snapshot getter so React can read a consistent value during concurrent rendering.

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

Most applications should consume a library's existing Hook rather than call this API directly. If you build a store integration, snapshots must be stable when the store has not changed, and server rendering may need a server snapshot so hydration begins from matching data.
