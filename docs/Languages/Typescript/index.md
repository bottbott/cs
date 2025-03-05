## Why care at all?

Typescript is a superset of Javascript that is ultimately compiled back to Javascript. Typescript isn't consumed natively. The big benefit that we get from using Typescript is the benefit of type-checking. All sorts of problems can occur when we aren't absolutely certain of the types we are using, and by using Typescript to enforce types, we can catch these problems before they become a problem.

## Types

Primitive types.

- number
- string
- boolean
- void
- undefined
- null

Object types.

- Array
- Function
- Classes
- Objects

## Type Annotations

## Type Inference

The Typescript compiler is able to determine a type when the code clearly gives it away. This is possible when a variable declaration and initialization are on the same line. For example:

`const message = 'hello';` - Typescript can infer that `message` is a string.
`const message = 10;` - Typescript can infer that `message` is a number.

We should always use type inference when we can, but there will be times that the type can't be inferred.

- declaring a variable and initializing it later.
- when the variable will be of a type that can't be inferred.
- when the return value is of 'any' type and we need to specify a type.

## Any Type

## Functions

- arguments
- return types
- anonymous functions

## Never Type

# Unsorted

## Bang Symbol

The bang symbol at the end of a variable indicates that the variable will not be null or undefined. This is a way to tell Typescript that we are sure that the variable will have a value. This is from the developers point of view, and if the variable is null or undefined, then the program will throw an error. You would still need to handle it if you need gracefully handle the error.

```typescript
let message: string | null = null;
let messageLength = message!.length;
```

## Nullish Coalescing Operator

The nullish coalescing operator is a way to check if a variable is null or undefined. If it is, then we can use a default value. This is useful when we want to set a default value for a variable.

```typescript
let message: string | null = null;
let messageLength = message ?? "default";
```

## Return Type

We can specify the return type of a function by using a colon after the arguments and specifying the type. If the function doesn't return anything, then we can use the `void` type.

```typescript
function add(a: number, b: number): number {
  return a + b;
}
```
