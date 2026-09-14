# URLs and History

The `URL` class parses and constructs URLs without manual string concatenation, and `URLSearchParams` reads and updates query parameters while applying URL encoding rules. Relative URLs can be resolved against a base URL.

```js
const url = new URL(location.href);
url.searchParams.set("page", "2");

history.pushState({ page: 2 }, "", url);

addEventListener("popstate", event => {
  console.log(event.state);
});
```

The History API can add or replace same-document entries with `pushState()` and `replaceState()`, while `popstate` reports navigation through those entries. Changing history does not render application state automatically. Keep meaningful URLs and normal links where possible so reload, sharing, browser navigation, and accessibility remain robust.
