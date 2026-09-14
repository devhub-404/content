# Testing Solid Components

Solid component tests should assert behavior visible through the DOM and user interactions instead of internal signal implementation. Testing libraries can render Solid roots and provide familiar DOM queries while disposing reactive ownership correctly after each test.

```tsx
render(() => <Counter />);

const button = screen.getByRole("button", { name: /count/i });
await userEvent.click(button);

expect(button).toHaveTextContent("1");
```

Use accessible queries when possible because they also check that UI semantics are discoverable. For server routes, data loading, and hydration, integration or end-to-end tests may provide more confidence than isolating every component. Keep async tests aligned with the actual boundary being exercised.
