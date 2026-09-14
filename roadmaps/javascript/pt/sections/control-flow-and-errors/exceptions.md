# Exceções

`throw` produz uma conclusão abrupta com um valor. Lançar objeto `Error` é convencional porque ele carrega mensagem, stack e identidade. `try` envolve código que pode falhar, `catch` trata o valor lançado e `finally` executa quando o controle sai da estrutura, inclusive após return ou outro erro.

```js
function parseConfig(text) {
  try {
    return JSON.parse(text);
  } catch (error) {
    throw new Error("Invalid configuration", { cause: error });
  } finally {
    console.log("Parse attempt finished");
  }
}
```

Capture um erro onde seja possível recuperar, adicionar contexto útil, traduzi-lo para erro de domínio ou garantir cleanup. Evite catches que apenas escondem falhas. A opção `cause` preserva erro subjacente ao envolvê-lo. Classes de erro customizadas ajudam callers a distinguir categorias quando essa distinção muda o comportamento.
