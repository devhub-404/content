# Actualizando Objects y Arrays en State

Los objects y arrays almacenados en state deben tratarse como snapshots inmutables. Para cambiarlos, crea un nuevo object/array reutilizando las partes sin cambios y sustituyendo lo necesario. Spread, `map`, `filter` y otras transformaciones no mutables son herramientas comunes.

```jsx
const [user, setUser] = useState({ name: 'Mina', active: false });

function activate() {
  setUser(current => ({
    ...current,
    active: true
  }));
}
```

La immutability no es una regla moral; forma parte del modelo de snapshots e identidad de React. Updates muy anidados pueden indicar un state shape pobre, necesidad de reducer o una helper library cuando el dominio realmente exige transforms complejos.
