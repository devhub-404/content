# Preserving Hidden UI with `<Activity>`

`<Activity>` can hide a UI subtree while preserving its state so it can become visible again without recreating everything. Hidden activity work is deprioritized and effects are handled according to Activity semantics, making it different from simple CSS hiding.

```jsx
function Tabs({ active }) {
  return (
    <>
      <Activity mode={active === 'feed' ? 'visible' : 'hidden'}>
        <Feed />
      </Activity>
      <Activity mode={active === 'messages' ? 'visible' : 'hidden'}>
        <Messages />
      </Activity>
    </>
  );
}
```

Use Activity when preserving a screen's local state and prepared UI has real value, such as tabs or navigational surfaces. It keeps memory and component state alive, so do not retain large trees indefinitely without considering resource cost and whether remounting would be simpler.
