# URLs e History

`URL` permite parsear y construir URLs sin concatenar strings manualmente, y `URLSearchParams` lee o modifica la query aplicando reglas de encoding. También puede resolver URLs relativas contra una base.

```js
const url = new URL(location.href);
url.searchParams.set("page", "2");

history.pushState({ page: 2 }, "", url);

addEventListener("popstate", event => {
  console.log(event.state);
});
```

La History API añade o reemplaza entries del mismo documento con `pushState()` y `replaceState()`, y `popstate` informa navegación por esas entries. Cambiar la URL no renderiza automáticamente la aplicación. Conserva URLs compartibles y links normales siempre que sea posible.
