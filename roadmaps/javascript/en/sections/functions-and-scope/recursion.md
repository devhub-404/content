# Recursion

Recursion means a function calls itself directly or indirectly. Correct recursive algorithms need a base case that stops further calls and a recursive step that moves toward that case. Trees, nested structures, parsers, and divide-and-conquer algorithms often have naturally recursive shapes.

```js
function factorial(n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}
```

Ordinary recursive calls consume call-stack space, and practical JavaScript engines do not universally optimize tail calls, so very deep recursion can overflow the stack. Use iteration or an explicit stack when depth may be large or controlled by untrusted input. Choose recursion when it makes the data structure or algorithm easier to understand.
