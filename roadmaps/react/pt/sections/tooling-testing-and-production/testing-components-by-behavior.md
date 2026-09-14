# Testando Components por Comportamento

Component tests valem mais quando exercitam comportamento observável: labels acessíveis, buttons, forms enviados, resultados e error states. Testar detalhes internos como state variables torna refactor mais difícil sem aumentar confiança.

```jsx
render(<LoginForm />);

await user.type(screen.getByLabelText(/email/i), 'mina@example.com');
await user.click(screen.getByRole('button', { name: /sign in/i }));

expect(await screen.findByText(/welcome/i)).toBeVisible();
```

Toolchain de tests fica fora do React core, então escolha ferramentas adequadas ao runtime/framework. RSC e features async podem ser melhor cobertos por integration/E2E quando ambiente unit não reproduz a boundary real.
