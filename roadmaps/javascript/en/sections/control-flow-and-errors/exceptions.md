# Exceptions

`throw` performs an abrupt completion with a value. Throwing an `Error` object is conventional because it carries a message, stack information, and error identity. `try` surrounds code that can fail, `catch` handles the thrown value, and `finally` runs as control leaves the construct even after a return or another error.

```js
function parseConfig(text) {
  try {
    return JSON.parse(text);
  } catch (error) {
    throw new Error("Invalid configuration", { cause: error });
  } finally {
    console.log("Parse attempt finished");
  }
}
```

Catch an error where you can recover, add useful context, translate it into a domain error, or guarantee cleanup. Avoid catches that only hide failures. The `cause` option preserves an underlying error when wrapping it. Custom error classes help callers distinguish categories when the distinction changes their behavior.
