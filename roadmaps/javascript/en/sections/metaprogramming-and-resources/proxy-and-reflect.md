# `Proxy` and `Reflect`

`Proxy` wraps an object or callable target and intercepts fundamental operations through traps such as property access, assignment, deletion, construction, and enumeration. `Reflect` exposes corresponding operations as functions and is often the safest way for a trap to delegate to the language's normal behavior.

```js
const target = { count: 1 };

const observed = new Proxy(target, {
  set(object, key, value, receiver) {
    console.log("set", key, value);
    return Reflect.set(object, key, value, receiver);
  },
});

observed.count = 2;
```

Proxy invariants prevent traps from reporting impossible results about non-configurable properties and other fixed facts. Proxies are useful for reactive systems, validation layers, membranes, and tooling, but they make ordinary operations indirect and can complicate optimization and debugging. Prefer explicit objects or functions when interception is not truly part of the abstraction.
