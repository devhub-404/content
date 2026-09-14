# Function Overloading and Default Arguments

C++ allows functions with the same name when overload resolution can select among distinct parameter lists. Candidate viability, implicit conversions, templates, and ranking rules determine which overload is chosen.

```cpp
void log(int value);
void log(double value);
void log(std::string_view value);

void connect(std::string_view host, int port = 443);
```

Default arguments fill omitted trailing arguments at the call site and are not a separate overload. Avoid overload sets where several choices require surprising conversions. Strong domain types and explicit names can be clearer than a large family of signatures that differ only subtly.
