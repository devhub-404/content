# Optional, Rest, and Destructured Parameters

Optional parameters use `?`, default parameters can make an argument effectively optional to callers, and rest parameters model arbitrary additional arguments as an array or tuple. Destructured object parameters are useful for named options, especially as an API grows.

```ts
type Options = {
  retries?: number;
  signal?: AbortSignal;
};

function request(
  url: string,
  { retries = 2, signal }: Options = {}
) {
  // ...
}

function sum(...values: number[]) {
  return values.reduce((a, b) => a + b, 0);
}
```

Keep optionality consistent with runtime behavior. A parameter annotated `x?: T` can receive `undefined`; a default applies when the argument is missing or explicitly undefined. Prefer an options object over many positional booleans or loosely related optional parameters because names document call sites.
