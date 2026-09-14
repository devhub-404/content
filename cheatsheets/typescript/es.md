---
locale: es
status: published
title: "TypeScript"
slug: typescript
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de TypeScript."
tags:
  - typescript
  - cheatsheet
  - quick-reference
references:
  - label: "TypeScript Handbook: The Basics"
    url: https://www.typescriptlang.org/docs/handbook/2/basic-types.html
  - label: "TypeScript Handbook: Everyday Types"
    url: https://www.typescriptlang.org/docs/handbook/2/everyday-types.html
  - label: "TypeScript: What is a tsconfig.json"
    url: https://www.typescriptlang.org/docs/handbook/tsconfig-json.html
---

# TypeScript

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Fundamentos de TypeScript

**Inferencia y anotaciones de tipo**

```ts
const count = 3;           // inferred as 3
let total = 0;             // inferred as number

function add(a: number, b: number) {
  return a + b;            // return type inferred as number
}
```

**Type erasure y valores de runtime**

```ts
type UserId = string;

interface User {
  id: UserId;
  name: string;
}

const user: User = { id: "u1", name: "Mina" };
console.log(user.name);
```

**Type checking, emisión y `noEmit`**

```ts
{
  "compilerOptions": {
    "strict": true,
    "noEmit": true
  }
}
```

## Tipos del día a día

**Tipos primitivos y arrays**

```ts
let name: string = "Mina";
let count: number = 3;
let active: boolean = true;

const ids: string[] = ["a", "b"];
const scores: Array<number> = [10, 20];
```

**`any`, `unknown` y `never`**

```ts
function parse(value: string): unknown {
  return JSON.parse(value);
}

function fail(message: string): never {
  throw new Error(message);
}
```

**Literal types y unions**

```ts
type Theme = "light" | "dark" | "system";
type Id = string | number;

function setTheme(theme: Theme) {
  // ...
}
```

**Type aliases e interfaces**

```ts
type Point = {
  x: number;
  y: number;
};

interface User {
  id: string;
  name: string;
}
```

**Optional, readonly e index signatures**

```ts
interface Settings {
  readonly id: string;
  theme?: "light" | "dark";
  [key: `plugin:${string}`]: unknown;
}
```

**Tuples y readonly tuples**

```ts
type Coordinate = readonly [x: number, y: number];

const point: Coordinate = [10, 20];

function range(): [start: number, end: number] {
  return [0, 100];
}
```

**Null, undefined y strict null checking**

```ts
function findUser(id: string): User | undefined {
  return users.find(user => user.id === id);
}

const user = findUser("u1");
if (user) {
  console.log(user.name);
}
```

## Narrowing y flujo de control

**Narrowing con `typeof` y truthiness**

```ts
function format(value: string | number | null) {
  if (value === null) return "none";

  if (typeof value === "number") {
    return value.toFixed(2);
  }

  return value.toUpperCase();
}
```

**Narrowing con `instanceof`, `in` e igualdad**

```ts
function read(value: Date | { text: string }) {
  if (value instanceof Date) {
    return value.toISOString();
  }

  if ("text" in value) {
    return value.text;
  }

  return "";
}
```

**Discriminated unions**

```ts
type Result =
  | { status: "ok"; value: string }
  | { status: "error"; error: Error };

function show(result: Result) {
  if (result.status === "ok") {
    return result.value;
  }

  return result.error.message;
}
```

**Type predicates y assertion functions**

```ts
function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "id" in value &&
    "name" in value
  );
}

function assertUser(value: unknown): asserts value is User {
  if (!isUser(value)) throw new Error("Invalid user");
}
```

**Exhaustividad con `never`**

```ts
type Action =
  | { type: "save" }
  | { type: "delete"; id: string };

function handle(action: Action) {
  switch (action.type) {
    case "save":
      return save();
    case "delete":
      return remove(action.id);
    default: {
      const exhaustive: never = action;
      return exhaustive;
    }
  }
}
```

## Tipos de función

**Function type expressions y call signatures**

```ts
type Formatter = (value: number) => string;

type Describable = {
  description: string;
  (value: number): string;
};
```

**Parámetros optional, rest y destructured**

```ts
type Options = {
  retries?: number;
  signal?: AbortSignal;
};

function request(
  url: string,
  { retries = 2, signal }: Options = {}
) {
  // ...
}

function sum(...values: number[]) {
  return values.reduce((a, b) => a + b, 0);
}
```

**Function overloads**

```ts
function parse(value: string): string[];
function parse(value: Uint8Array): string[];
function parse(value: string | Uint8Array): string[] {
  const text =
    typeof value === "string"
      ? value
      : new TextDecoder().decode(value);

  return text.split(",");
}
```

**Tipar parámetros `this`**

```ts
interface User {
  name: string;
}

function greet(this: User, message: string) {
  return `${message}, ${this.name}`;
}

const user = { name: "Mina", greet };
user.greet("Hello");
```

**Funciones genéricas**

```ts
function first<T>(items: readonly T[]): T | undefined {
  return items[0];
}

const name = first(["Mina", "Ada"]);
const number = first([10, 20]);
```

## Modelado de objetos

**Tipado estructural**

```ts
interface Named {
  name: string;
}

const value = {
  name: "Mina",
  role: "admin",
};

const named: Named = value;
```

**Excess property checks**

```ts
interface User {
  name: string;
}

const user: User = {
  name: "Mina",
  // role: "admin", // excess property in this fresh literal
};
```

**Intersection types**

```ts
type Timestamped = {
  createdAt: Date;
};

type Entity = {
  id: string;
};

type StoredEntity = Entity & Timestamped;
```

**Extensión de interfaces y composición de objetos**

```ts
interface Entity {
  id: string;
}

interface User extends Entity {
  name: string;
}

interface Admin extends User {
  permissions: string[];
}
```

**`as const` y `satisfies`**

```ts
const routes = {
  home: "/",
  users: "/users",
} as const;

const palette = {
  primary: "#2457d6",
  danger: "#b42318",
} satisfies Record<string, `#${string}`>;
```

## Generics y operadores de tipo

**Generic constraints**

```ts
function getLength<T extends { length: number }>(value: T) {
  return value.length;
}

getLength("hello");
getLength([1, 2, 3]);
```

**`keyof` e indexed access types**

```ts
type User = {
  id: string;
  name: string;
  active: boolean;
};

type UserKey = keyof User;       // "id" | "name" | "active"
type UserName = User["name"];    // string

function get<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
```

**`typeof` en posiciones de tipo**

```ts
const defaults = {
  retries: 3,
  mode: "safe" as const,
};

type Defaults = typeof defaults;

function configure(options: Partial<Defaults>) {
  // ...
}
```

**Conditional types e `infer`**

```ts
type ElementType<T> =
  T extends readonly (infer U)[]
    ? U
    : T;

type A = ElementType<string[]>; // string
type B = ElementType<number>;   // number
```

**Mapped types**

```ts
type Flags<T> = {
  [K in keyof T]: boolean;
};

type Mutable<T> = {
  -readonly [K in keyof T]-?: T[K];
};
```

**Template literal types**

```ts
type EventName<T extends string> = `${T}Changed`;

type Field = "name" | "email";
type FieldEvent = EventName<Field>;
// "nameChanged" | "emailChanged"
```

**Utility types estándar**

```ts
type UserPatch = Partial<User>;
type SavedUser = Required<UserDraft>;
type PublicUser = Pick<User, "id" | "name">;
type WithoutSecret = Omit<User, "passwordHash">;
type UserById = Record<string, User>;
```

**Const type parameters**

```ts
function defineRoutes<const T extends readonly string[]>(routes: T) {
  return routes;
}

const routes = defineRoutes(["/", "/users"]);
// inferred as readonly ["/", "/users"]
```

## Classes en TypeScript

**Fields de clase y tipos de constructor**

```ts
class User {
  id: string;
  name: string;

  constructor(id: string, name: string) {
    this.id = id;
    this.name = name;
  }
}
```

**`public`, `protected` y `private`**

```ts
class Account {
  public owner: string;
  protected balance = 0;
  private auditCode = "internal";

  constructor(owner: string) {
    this.owner = owner;
  }
}
```

**`implements` y clases abstractas**

```ts
interface Repository<T> {
  get(id: string): Promise<T | undefined>;
}

abstract class BaseRepository<T> implements Repository<T> {
  abstract get(id: string): Promise<T | undefined>;

  protected log(message: string) {
    console.log(message);
  }
}
```

**Clases genéricas**

```ts
class Store<T> {
  #items = new Map<string, T>();

  set(id: string, value: T) {
    this.#items.set(id, value);
  }

  get(id: string): T | undefined {
    return this.#items.get(id);
  }
}
```

**Parameter properties y `override`**

```ts
class User {
  constructor(
    public readonly id: string,
    public name: string
  ) {}
}

class Admin extends User {
  override toString() {
    return `Admin(${this.id})`;
  }
}
```

## Módulos y paquetes

**Imports y exports solo de tipo**

```ts
import type { User } from "./types.js";
import { createUser, type UserOptions } from "./users.js";

export type { User };
export { createUser };
```

**Resolución de módulos**

```ts
// source
import { parse } from "./parse.js";
import type { Config } from "my-package";

// tsconfig.json varies by runtime/bundler:
// module + moduleResolution must match the environment.
```

**Declaration files (`.d.ts`)**

```ts
// index.d.ts
export interface User {
  id: string;
  name: string;
}

export function loadUser(id: string): Promise<User>;
```

**Ambient declarations y module augmentation**

```ts
declare global {
  interface Window {
    appVersion: string;
  }
}

declare module "some-library" {
  interface Options {
    traceId?: string;
  }
}

export {};
```

**Declaration merging y namespaces**

```ts
interface Box {
  width: number;
}

interface Box {
  height: number;
}

const box: Box = {
  width: 10,
  height: 20,
};
```

## Interop con JavaScript y JSX

**`allowJs` y `checkJs`**

```ts
{
  "compilerOptions": {
    "allowJs": true,
    "checkJs": true,
    "noEmit": true
  }
}
```

**Tipos TypeScript en JSDoc**

```ts
/**
 * @template T
 * @param {T[]} items
 * @returns {T | undefined}
 */
export function first(items) {
  return items[0];
}
```

**JSX y TSX**

```ts
type ButtonProps = {
  label: string;
  onClick(): void;
};

function Button(props: ButtonProps) {
  return (
    <button onClick={props.onClick}>
      {props.label}
    </button>
  );
}
```

**Decorators estándar**

```ts
function logged(
  original: (this: any, ...args: any[]) => any,
  context: ClassMethodDecoratorContext
) {
  return function (this: any, ...args: any[]) {
    console.log(`calling ${String(context.name)}`);
    return original.call(this, ...args);
  };
}

class Service {
  @logged
  run() {}
}
```

## Configuración del compilador

**Fundamentos de `tsconfig.json`**

```ts
{
  "compilerOptions": {
    "strict": true,
    "target": "ES2024",
    "module": "nodenext",
    "moduleResolution": "nodenext",
    "noEmit": true
  },
  "include": ["src"]
}
```

**La familia `strict`**

```ts
{
  "compilerOptions": {
    "strict": true,
    "noImplicitOverride": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true
  }
}
```

**`target`, `lib` y downleveling**

```ts
{
  "compilerOptions": {
    "target": "ES2024",
    "lib": ["ES2024", "DOM"]
  }
}
```

**Configuración de módulos en TypeScript 6.0**

```ts
{
  "compilerOptions": {
    "module": "nodenext",
    "moduleResolution": "nodenext",
    "verbatimModuleSyntax": true
  }
}
```

**Paquetes de tipos ambient y `types`**

```ts
{
  "compilerOptions": {
    "types": ["node", "vitest/globals"]
  }
}
```

**Project references**

```ts
// packages/core/tsconfig.json
{
  "compilerOptions": {
    "composite": true,
    "declaration": true
  }
}

// root tsconfig.json
{
  "files": [],
  "references": [
    { "path": "./packages/core" },
    { "path": "./apps/web" }
  ]
}
```

## Librerías y tipos en producción

**Diseñar una API pública de tipos**

```ts
export interface ClientOptions {
  baseUrl: string;
  signal?: AbortSignal;
}

export function createClient(
  options: ClientOptions
): Client;
```

**Emisión de declarations**

```ts
{
  "compilerOptions": {
    "declaration": true,
    "declarationMap": true,
    "emitDeclarationOnly": true,
    "outDir": "./dist"
  }
}
```

**Tipos de paquete y export maps**

```ts
{
  "name": "example-lib",
  "type": "module",
  "exports": {
    ".": {
      "types": "./dist/index.d.ts",
      "import": "./dist/index.js"
    }
  }
}
```

**Probar tipos y evitar regresiones**

```ts
type Equal<A, B> =
  (<T>() => T extends A ? 1 : 2) extends
  (<T>() => T extends B ? 1 : 2)
    ? true
    : false;

type Expect<T extends true> = T;

type Test = Expect<Equal<ReturnType<typeof createUser>, User>>;
```
