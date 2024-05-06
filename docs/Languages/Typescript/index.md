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