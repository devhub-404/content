# `Proxy` y `Reflect`

`Proxy` envuelve un objeto o función e intercepta operaciones fundamentales mediante traps, como lectura, escritura, delete, construcción o enumeración. `Reflect` ofrece esas operaciones como funciones y suele ser la forma correcta de delegar al comportamiento normal desde un trap.

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

Los proxies tienen invariantes que impiden resultados imposibles respecto a propiedades no configurables y otras reglas del objeto. Son poderosos para reactividad, validación, membranes y tooling, pero añaden indirección y pueden complicar optimización y debugging. Usa objetos explícitos cuando no necesites interceptación real.
