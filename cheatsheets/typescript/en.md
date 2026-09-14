---
locale: en
status: published
title: "TypeScript"
slug: typescript
description: "A task-oriented quick reference for everyday TypeScript syntax, APIs, and workflows."
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

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## TypeScript Foundations

**Inference and Type Annotations**

```ts
const count = 3;           // inferred as 3
let total = 0;             // inferred as number

function add(a: number, b: number) {
  return a + b;            // return type inferred as number
}
```

**Type Erasure and Runtime Values**

```ts
type UserId = string;

interface User {
  id: UserId;
  name: string;
}

const user: User = { id: "u1", name: "Mina" };
console.log(user.name);
```

**Type Checking, Emission, and `noEmit`**

```ts
{
  "compilerOptions": {
    "strict": true,
    "noEmit": true
  }
}
```

## Everyday Types

**Primitive and Array Types**

```ts
let name: string = "Mina";
let count: number = 3;
let active: boolean = true;

const ids: string[] = ["a", "b"];
const scores: Array<number> = [10, 20];
```

**`any`, `unknown`, and `never`**

```ts
function parse(value: string): unknown {
  return JSON.parse(value);
}

function fail(message: string): never {
  throw new Error(message);
}
```

**Literal Types and Unions**

```ts
type Theme = "light" | "dark" | "system";
type Id = string | number;

function setTheme(theme: Theme) {
  // ...
}
```

**Type Aliases and Interfaces**

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

**Optional, Readonly, and Index Signatures**

```ts
interface Settings {
  readonly id: string;
  theme?: "light" | "dark";
  [key: `plugin:${string}`]: unknown;
}
```

**Tuples and Readonly Tuples**

```ts
type Coordinate = readonly [x: number, y: number];

const point: Coordinate = [10, 20];

function range(): [start: number, end: number] {
  return [0, 100];
}
```

**Null, Undefined, and Strict Null Checking**

```ts
function findUser(id: string): User | undefined {
  return users.find(user => user.id === id);
}

const user = findUser("u1");
if (user) {
  console.log(user.name);
}
```

## Narrowing & Control Flow

**`typeof` and Truthiness Narrowing**

```ts
function format(value: string | number | null) {
  if (value === null) return "none";

  if (typeof value === "number") {
    return value.toFixed(2);
  }

  return value.toUpperCase();
}
```

**`instanceof`, `in`, and Equality Narrowing**

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

**Discriminated Unions**

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

**Type Predicates and Assertion Functions**

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

**Exhaustiveness with `never`**

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

## Function Types

**Function Type Expressions and Call Signatures**

```ts
type Formatter = (value: number) => string;

type Describable = {
  description: string;
  (value: number): string;
};
```

**Optional, Rest, and Destructured Parameters**

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

**Function Overloads**

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

**Typing `this` Parameters**

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

**Generic Functions**

```ts
function first<T>(items: readonly T[]): T | undefined {
  return items[0];
}

const name = first(["Mina", "Ada"]);
const number = first([10, 20]);
```

## Object Modeling

**Structural Typing**

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

**Excess Property Checks**

```ts
interface User {
  name: string;
}

const user: User = {
  name: "Mina",
  // role: "admin", // excess property in this fresh literal
};
```

**Intersection Types**

```ts
type Timestamped = {
  createdAt: Date;
};

type Entity = {
  id: string;
};

type StoredEntity = Entity & Timestamped;
```

**Interface Extension and Object Composition**

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

**`as const` and `satisfies`**

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

## Generics & Type Operators

**Generic Constraints**

```ts
function getLength<T extends { length: number }>(value: T) {
  return value.length;
}

getLength("hello");
getLength([1, 2, 3]);
```

**`keyof` and Indexed Access Types**

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

**`typeof` in Type Positions**

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

**Conditional Types and `infer`**

```ts
type ElementType<T> =
  T extends readonly (infer U)[]
    ? U
    : T;

type A = ElementType<string[]>; // string
type B = ElementType<number>;   // number
```

**Mapped Types**

```ts
type Flags<T> = {
  [K in keyof T]: boolean;
};

type Mutable<T> = {
  -readonly [K in keyof T]-?: T[K];
};
```

**Template Literal Types**

```ts
type EventName<T extends string> = `${T}Changed`;

type Field = "name" | "email";
type FieldEvent = EventName<Field>;
// "nameChanged" | "emailChanged"
```

**Standard Utility Types**

```ts
type UserPatch = Partial<User>;
type SavedUser = Required<UserDraft>;
type PublicUser = Pick<User, "id" | "name">;
type WithoutSecret = Omit<User, "passwordHash">;
type UserById = Record<string, User>;
```

**Const Type Parameters**

```ts
function defineRoutes<const T extends readonly string[]>(routes: T) {
  return routes;
}

const routes = defineRoutes(["/", "/users"]);
// inferred as readonly ["/", "/users"]
```

## Classes in TypeScript

**Class Fields and Constructor Types**

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

**`public`, `protected`, and `private`**

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

**`implements` and Abstract Classes**

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

**Generic Classes**

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

**Parameter Properties and `override`**

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

## Modules & Packages

**Type-only Imports and Exports**

```ts
import type { User } from "./types.js";
import { createUser, type UserOptions } from "./users.js";

export type { User };
export { createUser };
```

**Module Resolution**

```ts
// source
import { parse } from "./parse.js";
import type { Config } from "my-package";

// tsconfig.json varies by runtime/bundler:
// module + moduleResolution must match the environment.
```

**Declaration Files (`.d.ts`)**

```ts
// index.d.ts
export interface User {
  id: string;
  name: string;
}

export function loadUser(id: string): Promise<User>;
```

**Ambient Declarations and Module Augmentation**

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

**Declaration Merging and Namespaces**

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

## JavaScript Interop & JSX

**`allowJs` and `checkJs`**

```ts
{
  "compilerOptions": {
    "allowJs": true,
    "checkJs": true,
    "noEmit": true
  }
}
```

**TypeScript Types in JSDoc**

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

**JSX and TSX**

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

**Standard Decorators**

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

## Compiler Configuration

**`tsconfig.json` Basics**

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

**The `strict` Family**

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

**`target`, `lib`, and Downleveling**

```ts
{
  "compilerOptions": {
    "target": "ES2024",
    "lib": ["ES2024", "DOM"]
  }
}
```

**Module Settings in TypeScript 6.0**

```ts
{
  "compilerOptions": {
    "module": "nodenext",
    "moduleResolution": "nodenext",
    "verbatimModuleSyntax": true
  }
}
```

**Ambient Type Packages and `types`**

```ts
{
  "compilerOptions": {
    "types": ["node", "vitest/globals"]
  }
}
```

**Project References**

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

## Libraries & Production Types

**Designing a Public Type API**

```ts
export interface ClientOptions {
  baseUrl: string;
  signal?: AbortSignal;
}

export function createClient(
  options: ClientOptions
): Client;
```

**Declaration Emission**

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

**Package Types and Export Maps**

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

**Testing Types and Preventing Regressions**

```ts
type Equal<A, B> =
  (<T>() => T extends A ? 1 : 2) extends
  (<T>() => T extends B ? 1 : 2)
    ? true
    : false;

type Expect<T extends true> = T;

type Test = Expect<Equal<ReturnType<typeof createUser>, User>>;
```
