# Entrada del Programa y Top-level Statements

Una aplicación de consola puede usar top-level statements sin declarar `Program.Main`. El compilador sigue creando el entry point y los argumentos están disponibles mediante la variable implícita `args`. `static void Main` o `static Task Main` siguen siendo válidos.

```csharp
string name = args.Length > 0 ? args[0] : "world";
Console.WriteLine($"Hello, {name}");
```

Los top-level statements son cómodos para programas pequeños y ejemplos, pero aplicaciones mayores siguen beneficiándose de tipos y métodos normales. No pongas toda la aplicación en un único archivo solo porque la sintaxis lo permita.
