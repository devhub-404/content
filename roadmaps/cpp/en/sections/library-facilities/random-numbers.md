# Random Number Facilities

The `<random>` library separates engines, which generate pseudo-random sequences, from distributions, which map engine output to a desired probability distribution. This is much more expressive and controllable than legacy C-style `rand()`.

```cpp
std::random_device rd;
std::mt19937 engine(rd());

std::uniform_int_distribution<int> die(1, 6);

int roll = die(engine);
```

Seed requirements depend on the application. Simulation may need reproducible fixed seeds, while security-sensitive randomness requires a cryptographically suitable source that the standard pseudo-random engines do not promise. Do not confuse statistical convenience with cryptographic security.
