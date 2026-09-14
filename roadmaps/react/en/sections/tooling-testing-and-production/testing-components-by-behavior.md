# Testing Components by Behavior

Component tests are most valuable when they exercise behavior users can observe: accessible labels, buttons, submitted forms, displayed results, and error states. Testing implementation details such as internal state variables makes refactoring harder without improving confidence.

```jsx
render(<LoginForm />);

await user.type(screen.getByLabelText(/email/i), 'mina@example.com');
await user.click(screen.getByRole('button', { name: /sign in/i }));

expect(await screen.findByText(/welcome/i)).toBeVisible();
```

The testing toolchain is outside core React, so choose tools that support your runtime and framework. React Server Components and async framework features may be better covered by integration or end-to-end tests when a unit environment cannot reproduce the actual server/client boundary.
