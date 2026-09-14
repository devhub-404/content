# `await using` e Disposable Stacks

`await using` gerencia recurso cujo cleanup assíncrono é fornecido por `[Symbol.asyncDispose]()`. O disposal é aguardado quando o escopo termina, então a sintaxe só é permitida onde `await` é permitido. Aquisição e cleanup podem envolver trabalho assíncrono.

```js
async function read(openFile) {
  await using file = await openFile();
  return file.read();
}

{
  using stack = new DisposableStack();
  stack.defer(() => console.log("cleanup"));
}
```

`DisposableStack` e `AsyncDisposableStack` agrupam várias ações de cleanup quando ownership é mais fácil de gerenciar como conjunto. Preservam cleanup em ordem reversa e comportamento definido de erros. O recurso é opt-in: recursos declarados com `const` ou `let` comuns não são descartados automaticamente, então convenções de ownership e registro correto continuam essenciais.
