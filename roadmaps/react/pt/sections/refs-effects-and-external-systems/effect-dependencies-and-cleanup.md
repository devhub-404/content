# Dependencies e Cleanup de Effects

A dependency list descreve valores reativos que o Effect lê do scope do component. Não é um scheduler escrito manualmente. Quando dependency muda, React limpa sincronização anterior e roda setup com valores do novo render.

```jsx
useEffect(() => {
  const controller = new AbortController();

  fetch(`/api/users/${userId}`, { signal: controller.signal })
    .then(response => response.json())
    .then(setUser);

  return () => controller.abort();
}, [userId]);
```

Não silencie linter apenas para evitar reruns. Reestruture para o Effect ler exatamente o que pertence à sincronização. Cleanup deve desfazer setup: unsubscribe, abort, disconnect, remover listeners ou liberar a relação externa.
