# Lambdas and Captures

A lambda creates an unnamed closure object with an `operator()` and an explicit capture list. Captures may copy values, bind references, initialize new capture members, or capture `this` according to the chosen syntax.

```cpp
int factor = 3;

auto multiply = [factor](int value) {
    return value * factor;
};

std::ranges::transform(values, out.begin(), multiply);
```

The closure can outlive the scope where it was created, so reference captures must not outlive the referenced objects. Prefer small captures rather than `[&]` or `[=]` in long-lived callbacks where hidden dependencies are easy to miss. Generic lambdas can use `auto` parameters or explicit template parameter lists.
