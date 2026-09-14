# Probando Solid Components

Los tests de Solid deben verificar comportamiento observable en DOM/interacciones en vez de implementation de signals. Testing libraries renderizan roots y ofrecen DOM queries mientras disponen reactive ownership correctamente después de cada test.

```tsx
render(() => <Counter />);

const button = screen.getByRole("button", { name: /count/i });
await userEvent.click(button);

expect(button).toHaveTextContent("1");
```

Usa accessible queries cuando sea posible. Para server routes, data loading e hydration, integration/E2E pueden dar más confianza que aislar cada component. Alinea async tests con la boundary real ejercitada.
