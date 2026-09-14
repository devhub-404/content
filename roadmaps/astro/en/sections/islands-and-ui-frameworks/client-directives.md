# Client Hydration Directives

`client:*` directives tell Astro when a framework component should hydrate in the browser. `client:load` is immediate, while `client:idle`, `client:visible`, and media-based hydration can postpone JavaScript until the interaction is likely to matter.

```astro
<NavMenu client:load />
<Chart client:visible />
<Search client:idle />
<ThemePicker client:media="(max-width: 48rem)" />
```

Choose the earliest timing the user experience actually requires, not `client:load` by habit. A menu needed immediately may load eagerly; a below-the-fold chart can wait for visibility. Hydration timing changes when code becomes interactive, so test keyboard and pointer behavior under slow networks.
