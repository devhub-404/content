# Testando Solid Components

Tests de Solid devem verificar comportamento observável no DOM/interações em vez de implementation de signals. Testing libraries renderizam roots e oferecem DOM queries enquanto dispõem reactive ownership corretamente após teste.

```tsx
render(() => <Counter />);

const button = screen.getByRole("button", { name: /count/i });
await userEvent.click(button);

expect(button).toHaveTextContent("1");
```

Use accessible queries quando possível. Para server routes, data loading e hydration, integration/E2E podem oferecer mais confiança que isolar todo component. Alinhe async tests à boundary real exercitada.
