# JSX and TSX

TypeScript parses JSX in `.tsx` files and type-checks elements according to the JSX runtime and type declarations supplied by the framework. The `jsx` compiler option controls how JSX syntax is preserved or transformed for the selected toolchain.

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

JSX typing is framework-driven: React, Solid, and other libraries define different intrinsic elements, component rules, and runtime transforms. Do not treat TSX as a separate universal UI type system. Configure TypeScript according to the framework's current guidance and let its declarations define valid props and JSX results.
