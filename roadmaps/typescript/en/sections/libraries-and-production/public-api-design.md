# Designing a Public Type API

A library's public types are part of its compatibility contract. Prefer names that express domain concepts, keep generics tied to real relationships, and avoid exposing internal helper types simply because they were convenient during implementation. Export the smallest surface consumers actually need.

```ts
export interface ClientOptions {
  baseUrl: string;
  signal?: AbortSignal;
}

export function createClient(
  options: ClientOptions
): Client;
```

Types that are too narrow make normal use awkward; types that are too broad move errors to runtime. Model callback variance, nullability, mutability, and asynchronous results deliberately. Once published, changing a type can be breaking even when the emitted JavaScript stays identical, because consumer programs may stop type-checking.
