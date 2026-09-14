# Strict Mode

`<StrictMode>` enables extra development checks that expose impure rendering, missing Effect cleanup, deprecated behavior, and other patterns that are likely to break under modern React semantics. Some functions intentionally run extra times in development to reveal problems.

```jsx
createRoot(document.getElementById('root')).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

Do not “fix” Strict Mode by adding flags that hide duplicate setup. Make rendering pure and Effects symmetric instead. Strict Mode checks are development-only and do not mean production literally performs every duplicate call, but code that survives them is usually more resilient.
