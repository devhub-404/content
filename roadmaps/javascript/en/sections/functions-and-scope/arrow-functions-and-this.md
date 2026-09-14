# Arrow Functions and Lexical `this`

Arrow functions are compact function expressions. A single expression can be returned implicitly; a block body needs `return`. More importantly, arrows do not create their own `this`, `arguments`, `super`, or `new.target` bindings. They capture relevant values from the surrounding lexical context.

```js
const double = value => value * 2;

const counter = {
  value: 0,
  start() {
    setTimeout(() => {
      this.value += 1;
    }, 100);
  },
};
```

That makes arrows excellent for callbacks that should keep the surrounding method's receiver, but often wrong for an object method that needs dynamic `this`. Arrows also cannot be used as constructors with `new`. Choose the syntax for its semantics rather than treating arrows as a universally newer replacement for ordinary functions.
