# JSX e TSX

TypeScript faz parse de JSX em arquivos `.tsx` e verifica elementos conforme runtime JSX e declarations fornecidas pelo framework. A opção `jsx` controla como a sintaxe é preservada ou transformada para o toolchain escolhido.

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

Tipagem JSX é dirigida pelo framework: React, Solid e outras bibliotecas definem intrinsic elements, regras de componentes e transforms de runtime diferentes. Não trate TSX como sistema universal de UI. Configure TypeScript conforme documentação atual do framework e deixe suas declarations definirem props e resultados JSX válidos.
