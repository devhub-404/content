# Preservando UI Oculta com `<Activity>`

`<Activity>` pode esconder subtree preservando seu state para voltar visível sem recriar tudo. Trabalho hidden recebe prioridade menor e Effects seguem semântica de Activity, portanto é diferente de esconder apenas com CSS.

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

Use quando preservar local state e UI preparada tem valor real, como tabs ou surfaces de navegação. Isso mantém memória/state vivos, então não retenha trees grandes indefinidamente sem avaliar custo e se remount seria mais simples.
