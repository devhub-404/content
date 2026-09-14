# JSX y TSX

TypeScript analiza JSX dentro de archivos `.tsx` y comprueba los elementos según el runtime y las declarations del framework. La opción `jsx` controla cómo se preserva o transforma esa sintaxis para el toolchain elegido.

```ts
type ButtonProps = {
  label: string;
  onClick(): void;
};

function Button(props: ButtonProps) {
  return (
    <button onClick={props.onClick}>
      {props.label}
    </button>
  );
}
```

El tipado JSX lo define el framework: React, Solid y otras librerías tienen distintos intrinsic elements, reglas de componentes y transforms. Configura TypeScript según la documentación del framework y deja que sus types definan props y resultados válidos.
