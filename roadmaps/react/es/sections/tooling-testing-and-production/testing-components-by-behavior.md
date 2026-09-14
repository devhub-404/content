# Probando Components por Comportamiento

Los component tests valen más cuando ejercitan comportamiento observable: labels accesibles, buttons, forms enviados, resultados y error states. Probar detalles internos como state variables dificulta refactors sin aumentar confianza.

```jsx
render(<LoginForm />);

await user.type(screen.getByLabelText(/email/i), 'mina@example.com');
await user.click(screen.getByRole('button', { name: /sign in/i }));

expect(await screen.findByText(/welcome/i)).toBeVisible();
```

El toolchain de tests está fuera del React core, así que elige herramientas adecuadas al runtime/framework. RSC y features async pueden cubrirse mejor con integration/E2E cuando un entorno unit no reproduce la boundary real.
