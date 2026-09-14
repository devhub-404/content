# Accessibility and DOM Semantics

React renders web platform elements, so semantic HTML and accessibility remain the foundation. Use real buttons for actions, links for navigation, labels for form controls, heading hierarchy, landmarks, and native keyboard behavior before reaching for ARIA.

```jsx
function Menu() {
  return (
    <nav aria-label="Account">
      <ul>
        <li><a href="/profile">Profile</a></li>
        <li><button type="button">Sign out</button></li>
      </ul>
    </nav>
  );
}
```

State-driven UI must also manage focus, announcements, disabled states, and reduced motion when interactions change the page dynamically. React does not automatically make a custom component accessible. Build component APIs that preserve native semantics instead of making callers reconstruct them each time.
