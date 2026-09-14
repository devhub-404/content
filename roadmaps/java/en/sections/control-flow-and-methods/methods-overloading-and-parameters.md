# Methods, Overloading, and Parameters

Methods declare parameter and return types, and Java supports overloads selected from their signatures and conversion rules. Java passes arguments by value: object parameters receive a copied reference value, so methods can mutate the referenced object but cannot rebind the caller variable itself.

```java
static int max(int a, int b) {
    return a >= b ? a : b;
}

static double max(double a, double b) {
    return a >= b ? a : b;
}
```

Keep overload families semantically consistent. Java has no default arguments, so builders, overloads, or option/config objects are common when an API has optional settings.
