# The `strict` Family

`strict` enables a family of checks such as strict null handling, function variance rules, initialization checks, and implicit-any detection. It is the right baseline for most new projects because the checker can make stronger guarantees about ordinary code.

```ts
{
  "compilerOptions": {
    "strict": true,
    "noImplicitOverride": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true
  }
}
```

Additional options such as `noUncheckedIndexedAccess`, `exactOptionalPropertyTypes`, and `noImplicitOverride` tighten specific areas beyond the core strict family. Enable them intentionally and understand the model they enforce. A strict project may require more careful boundary validation, but that is usually evidence of real uncertainty that existed at runtime anyway.
