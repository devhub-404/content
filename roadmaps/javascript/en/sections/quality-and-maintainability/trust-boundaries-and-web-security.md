# Trust Boundaries and Web Security

URL parameters, network responses, storage, messages, and user input are data from trust boundaries, not automatically valid program values. Validate shape and domain constraints before relying on them. In the DOM, use text APIs for text and avoid inserting untrusted strings as HTML.

```js
const item = document.createElement("li");
item.textContent = untrustedName;

const response = await fetch("/api/profile", {
  credentials: "same-origin",
});
```

Browser security concepts such as same-origin policy, CORS, Content Security Policy, cookies, credentials, sandboxing, and Trusted Types shape what JavaScript can safely do. They are platform mechanisms, not ECMAScript syntax. Do not solve a CORS or CSP failure by weakening security globally; identify the intended trust relationship and grant the narrowest necessary permission.
