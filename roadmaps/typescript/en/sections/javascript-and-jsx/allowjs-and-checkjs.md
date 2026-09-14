# `allowJs` and `checkJs`

TypeScript can include JavaScript files in a project with `allowJs` and can type-check them with `checkJs`. This makes gradual adoption possible without converting every file to `.ts` at once. Type information can be inferred from JavaScript syntax, JSDoc, declaration files, and imported libraries.

```ts
{
  "compilerOptions": {
    "allowJs": true,
    "checkJs": true,
    "noEmit": true
  }
}
```

JavaScript checking is intentionally looser in some areas because ordinary JS patterns must remain usable. Treat migration as a boundary-by-boundary process: enable checking, annotate important APIs, fix real errors, and convert files where TypeScript syntax provides value. Avoid mass-renaming files before the project actually type-checks.
