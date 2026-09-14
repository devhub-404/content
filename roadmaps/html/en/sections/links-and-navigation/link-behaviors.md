# New Tabs, Downloads, Email, and Phone Links

Links can request behaviors beyond ordinary navigation. `download` suggests downloading a same-origin resource; `mailto:` hands an address to the user's email handler; `tel:` can hand a number to calling software. These behaviors depend on browser, origin policy, device capability, and user configuration.

```html
<a href="/report.pdf" download>Download report</a>
<a href="mailto:support@example.com">Email support</a>
<a href="tel:+15551234567">Call support</a>
<a href="/help" target="_blank" rel="noopener">Open help in a new tab</a>
```

`target="_blank"` requests a new browsing context, usually a new tab. Opening tabs unexpectedly can be disorienting, so use it only when the task benefits from preserving the current page. Modern browsers protect new tabs from many opener risks, but `rel` values still communicate relationship and security intent. Visible text should tell users what the destination or file is.
