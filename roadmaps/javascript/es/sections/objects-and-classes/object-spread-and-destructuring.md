# Object spread y destructuring

Object spread copia propiedades propias enumerables en un nuevo objeto y las propiedades posteriores sobrescriben a las anteriores con la misma clave. La copia es superficial: objetos o arrays anidados siguen siendo las mismas referencias.

```js
const user = { name: "Mina", role: "admin" };
const updated = { ...user, role: "editor" };

const {
  name: displayName,
  role = "guest",
} = updated;
```

Destructuring extrae propiedades a bindings y admite renombre, defaults, rest y patrones anidados. Un default se usa solo cuando el valor extraído es `undefined`. Spread es cómodo para records de datos, pero no conserva automáticamente prototypes ni todos los descriptors de la fuente.
