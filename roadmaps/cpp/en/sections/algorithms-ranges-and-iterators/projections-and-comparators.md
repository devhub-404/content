# Comparators and Projections

Many ranges algorithms accept comparators and projections. A projection transforms each element for comparison without requiring a separate temporary range, which is especially convenient for sorting or searching by one member.

```cpp
std::ranges::sort(users, {}, &user::name);

auto found = std::ranges::find(
    users,
    "Mina",
    &user::name
);
```

Comparators must satisfy the ordering contract required by the algorithm; a broken strict weak ordering can make behavior incorrect or undefined for some algorithms. Prefer standard comparison utilities and simple projections to hand-written comparators that duplicate field extraction.
