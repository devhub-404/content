# Effects and Synchronization

An Effect synchronizes a rendered component with something outside React: a subscription, browser API, network connection, imperative library, or other external system. React runs the setup after commit and runs cleanup before re-synchronizing or removing the component.

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

Effects are not a general “after render” bucket. If a value can be derived during render or an action is caused by one event, use calculation or an event handler instead. Every Effect should have a clear external system and a cleanup story when that system needs one.
